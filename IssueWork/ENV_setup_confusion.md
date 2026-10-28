# Paul Dal Pozzo

**Student ID:** s214527809  
**Email:** s214527809@deakin.edu.au  
**Intern Position:** Usability Tester & Bug Hunter  
**Focus Bear Account:** paul_dal_pozzo@hotmail.com  
**Markdown Location:** https://github.com/pdalpozzo/paul-dalpozzo-focusbear-intern-repo/blob/main/IssueWork/ENV_setup_confusion.md

# Issue 16
## Understanding the issue
>**Description:**  
>
>While working on the repository duplication step, I faced multiple errors related to the .env file configuration. The script was throwing an error saying "undefined is not valid JSON", which made it difficult to understand what exactly was going wrong at first.

This issue is feedback about the repository duplication step. The user is claiming to have multiple errors related to the `.env` file. The error they received was `undefined is not a valid JSON`.
I agree. That error message is not doing a good job of describing the issue. What is `undefined` in this case?

>**What I noticed**
>- The script is expecting DEST_REPOS, but in some places it is mentioned as DEST_REPO
>- The value for DEST_REPOS needs to be in a JSON array format like ["username/repo"], but this was not clearly explained
>- Even small mistakes in the .env file (like extra characters or wrong format) caused the script to fail without clear guidance

Here we have more details. The user mentions `DEST_REPOS` and `DEST_REPO`. Both are variables that provide a destination (in this case) for a repository to be duplicated to.
- `DEST_REPO` is singular. It expects a plain text string that represents a URI of a repository. Eg `DEST_REPO=<username>/<repository>`. No other syntax is needed.
- `DEST_REPOS` is plural. It expects a JSON format array (one or more URI). Eg `DEST_REPOS=["<username1>/<repository1>", "<username2>/<repository2>"]`. The syntax of the JSON array is needed, even if there is only one entry.

I checked the `duplicate-repo.js`, `.env.sample` and `README.md`; they only contain `DEST_REPOS`. I am not sure where the user was seeing `DEST_REPO`.

>**Suggestions:**
>
>It would be helpful if:
>- The correct variable name is clearly mentioned everywhere
>- A proper example of the .env file is provided
>- The expected format for DEST_REPOS is explained more clearly

README.md screenshot
![README.md screenshot](16_variablename.png)  

**1. The correct variable name is clearly mentioned everywhere**  
Above is a screenshot of the `README.md`. `DEST_REPOS` is the only one ever mentioned.

**2. A proper example of the .env file is provided**  
There is a sample provided in the `.env.sample` file. Here are two screenshots from the GitHub Repository.

![](16_samplefile.png)  
This clearly shows the `.env.sample` file.

![](16_samplecontent.png)  
This clearly shows the contents of the sample file. While it does not match the instructions in the `README.md` word for word, it seems clear to me that `DEST_REPOS=["your-username-intern-repo"]` and `DEST_REPOS=["YOUR_USERNAME/focus-bear-generic-onboarding"]` are in the same location and are the same variable. You can also see that the example is already in the format that is expected.

**3. The expected format for DEST_REPOS is explained more clearly**  
In the above screenshot of the `README.md`, the `DEST_REPOS` formatting is clearly explained and visible. The exact line is
>Replace `your-username-intern-repo` with your **new repository name**. Make sure it is enclosed in [" and "]  

Only way it could be more clear is to highlight the syntax in the same way the repository name. Eg `["` and `"]` then give the full example of `["your-username-intern-repo"]`

## Key Issues to address
There are two main issues here; the error message and the JSON formatting. While the files (`README.md`, `duplicate-repo.js`, and `.env.sample`) are technically correct, there still seems to be a steep learning curve for beginners.
- **Poor Error Message:** `undefined is not valid JSON` gives no actionable feedback and provides no details for the user to even start troubleshooting.
- **JSON Formatting:** Using `DEST_REPOS` requires specific syntax (`["` and `"]`) and can cause confusion with beginners that maybe have never seen this variable before. It becomes another point of failure. Using a JSON array for variables is also uncommon pattern in development workflows, decreasing the chance that the user has encounter this specific way of doing things before. 

Both of these issues bring the usability into question. While technically everything is correct and in place to help a beginner, there are still too many points of failure with no good feedback. This can cause a user to become frustrated or even panic, resulting in even less chances of them solving the problem on their own.

### Suggestions
- **Provide better error messaging:** Include error messages for each variable in the `.env`. This ay require more work initially, but it will save time later by allowing new onboarding users to figure out the issue themselves.
- **Clear up "Singular vs Plural" confusion:** Provide some details in the `README.md` that explains the difference between the two variables and why it is set up to use `DEST_REPOS`.
- **Syntax Formatting:** Make the example in the `README.md` stand out; use a bright colour and other techniques. Explain that the syntax formatting in the example is important and will cause errors if not strictly followed.
- **Handle both `DEST_REPOS` and `DEST_REPO`:** This might be more complicated to do, but it would remove any point of failure. If the `DEST_REPOS` is really important to keep and understand, then provide warning messages while accepting the `DEST_REPO` variable. There is no reason for the whole set up to fail.


## Actions to take
### Use Comments in `.env`
This is a great way to provide an example of the correct variable syntax in the place where the variable is being changed. This will help in two ways:

#### Provide a direct sample
Placing a comment with the correct syntax above the variable in the `.env` will allow the user to have a reference point right next to the place of editing. It provides a sample to copy if the user edits the functional line too much. We can also use a comment to explain that the environment expects `DEST_REPOS`, not `DEST_REPO`.

#### Reducing Reference Count
This reduces the back and forth between multiple files and multiple instructions. Right now, there are multiple points of reference (`README.md`, `.env.sample`, `.env`) requiring the user to keep track of which instructions they are following. 

#### Solution 

```properties 
GITHUB_TOKEN=your_github_token_here
SOURCE_REPO=Focus-Bear/onboarding-generic
# This development environment uses DEST_REPOS (NOT DEST_REPO).
# The destination repository must be formatted as a strict JSON array. Full line example below:
# DEST_REPOS=["username/repo"]
DEST_REPOS=["username/repo"]
```

The example above can be shown in the `README.md` as well and clearly shows formatting with colours. It also provides a place to get a fresh copy of the intended code for the `.env`.  
By placing this code in the `.env` directly and providing it in the `README.md`, we can eliminate the `.env.sample` and reduce the references.

---
### Improve Error Handling
The current error handling message for this failure is not even handled by the code and sends a generic error message. This can be more robust and even handle the user using `DEST_REPO` if it is something that is acceptable.

#### The Problematic Code

```js
const GITHUB_TOKEN = process.env.GITHUB_TOKEN;
const SOURCE_REPO = process.env.SOURCE_REPO;
const DEST_REPOS = JSON.parse(process.env.DEST_REPOS);

if (!GITHUB_TOKEN || !SOURCE_REPO || !DEST_REPOS) {
  console.error('❌ Missing required environment variables. Check your .env file.');
  process.exit(1);
}
```
This code has a single line for parsing `DEST_REPOS`. It does not allow for any handling of errors. As a general rule/standard, variables that are parsed should be placed in a `try/catch`. This standard exists to prevent this exact issue. That way we can handle failed parses correctly.

#### Solution
**Step 1:** We need to place the parsing into a `try/catch`. Here we can provide an error message that specifies it is a parsing error.

```js
try {
  DEST_REPOS = JSON.parse(process.env.DEST_REPOS);
} catch (e) {
  console.error('❌ Error: DEST_REPOS is not in the correct JSON array format.');
  console.error(`Current value detected: ${process.env.DEST_REPOS}`);
  console.error('\nTo fix this, make sure it matches this format exactly (including brackets and double quotes):');
  console.error('DEST_REPOS=["username/repository-name"]');
  process.exit(1);
}
```

**Step 2:** Remove parsing on a single line

```js
const GITHUB_TOKEN = process.env.GITHUB_TOKEN;
const SOURCE_REPO = process.env.SOURCE_REPO;
const DEST_REPOS = JSON.parse(process.env.DEST_REPOS);
```

Becomes...

```js
const GITHUB_TOKEN = process.env.GITHUB_TOKEN;
const SOURCE_REPO = process.env.SOURCE_REPO;
let DEST_REPOS;
```

**Step 3:** Check each variable individually and provide better error messages.

```js
if (!GITHUB_TOKEN || !SOURCE_REPO || !DEST_REPOS) {
  console.error('❌ Missing required environment variables. Check your .env file.');
  process.exit(1);
}
```

Becomes...

```js
// Check GITHUB_TOKEN
if (!GITHUB_TOKEN) {
  console.error('❌ Error: GITHUB_TOKEN is missing from your .env file.');
  console.error('Please ensure you have created a .env file containing your GitHub Token.');
  process.exit(1);
}

// Check SOURCE_REPO
if (!SOURCE_REPO) {
  console.error('❌ Error: SOURCE_REPO is missing from your .env file.');
  console.error('Please ensure you have created a .env file containing the source repository.');
  console.error('SOURCE_REPO=Focus-Bear/onboarding-generic');
  process.exit(1);
}

// Check DEST_REPOS
if (!process.env.DEST_REPOS) {
  console.error('❌ Error: DEST_REPOS is missing from your .env file.');
  console.error('Please ensure you have created a .env file containing your destination repository.');
  console.error('Example: DEST_REPOS=["your-username/your-repo"]');
  process.exit(1);
}
```

**Step 4:** Add a check on the `DEST_REPOS` to ensure it is an array and not empty

```js
if (!Array.isArray(DEST_REPOS) || DEST_REPOS.length === 0) {
  console.error('❌ Error: DEST_REPOS must be a non-empty array.');
  console.error('Example: DEST_REPOS=["username/repo-one", "username/repo-two"]');
  process.exit(1);
}
```

**Step 5 (Optional):** Add handling `DEST_REPO` and provide a warning. This should be placed after the `SOURCE_REPO` check and before the `DEST_REPO` check. 

```js
// Check if DEST_REPO is used, provide a warning and add the path to DEST_REPOS
if (process.env.DEST_REPO && !process.env.DEST_REPOS) {
  console.warn('⚠️  Warning: You used DEST_REPO (singular) instead of DEST_REPOS (plural) in your .env file.');
  console.warn('⚠️  Warning: Check your .env file and use DEST_REPOS as soon as possible.');
  console.warn(`Converting your single repository configuration dynamically: ["${process.env.DEST_REPO}"]`);
  
  // Clean up any accidental brackets or quotes the user might have attempted, then wrap as an array
  const cleanRepo = process.env.DEST_REPO.replace(/[\[\]"']/g, '').trim();
  process.env.DEST_REPOS = `["${cleanRepo}"]`;
} 
```

---
### Improve Troubleshooting Section
The troubleshooting section of the `README.md` is very brief and located at the bottom of the file. There is no mention of this issue or how to handle it. The troubleshooting provide in this section is lacking and requires another pass to be more robust.

#### The Current Troubleshooting
>## ❓ Troubleshooting
>- **GitHub API rate limit exceeded?**
>   - Wait a few minutes or generate a new token with higher rate limits.
>- **Issues/labels not appearing?**
>   - Check the script output and ensure `.env` values are correct.
>- **Script not running?**
>   - Run `node -v` to check if Node.js is installed.
>
>📢 If you're still stuck, **reach out in Discord!** 🎯

#### Solution

>## ❓ Troubleshooting
>
>If you encounter issues, check the common solutions below.
>
>### GitHub API Rate Limit Exceeded
>The GitHub API has a strict limit on how many requests can be made in an hour. Unauthenticated requests (no token) are limited to **60 requests per hour**, which this script can quickly exhaust when fetching large amounts of issue or label data. Authenticated requests using a Personal Access Token (PAT) allow up to **5,000 requests per hour**.
>- **Why it happened:** You are likely running the script without a token, or your script is looping heavily and has exhausted your hourly quota.
>- **Fix:** Wait a few minutes for the hourly window to reset, or generate a new GitHub Personal Access Token (PAT) with higher limits and add it to your configuration.
>
>
>### Issues/labels not appearing?
>- **Check for a hidden file extension:** Ensure your file is named exactly `.env` and not `.env.txt` or `.env.sample`.
>- **Verify the variable name:** Confirm the variable is strictly plural (`DEST_REPOS=`), not singular (`DEST_REPO=`).
>- **Check the strict JSON syntax:** Ensure your repository string is wrapped in both square brackets and **double quotes** (e.g., `["username/repo"]`). Single quotes (e.g., `['username/repo']`) or missing brackets will cause the script to fail silently or crash.
>- **Inspect the terminal output:** Look closely at the script logs. If you see an `undefined is not valid JSON` error, it means the script cannot read your `.env` file or the formatting inside it is broken.
>
>### Script Fails to Run
>If the execution command throws an error immediately, your local environment might lack Node.js entirely.
>- **Check your version:** Verify if Node.js is installed by running:
>   ```bash
>   node -v
>   ```
>- **How to Install:** If the command is unrecognized, you need to install Node.js. Download the **LTS (Long Term Support)** version from the official [Node.js Download Page](https://nodejs.org). 
>- **Alternative (NVM):** For easier version management, you can install it via Node Version Manager (NVM):
>   ```bash
>   nvm install --lts
>   ```
>
> ---
> 📢 **Still stuck?** Join the conversation and ask for help in [Discord](https://discord.gg)! 🎯
> 
> ---

At step 2 of **'Create a `.env` File'**, there should be some information about this particular issue. It seems like it would be a common issue and requires a direct notice to the user of it potentially occurring. It can even provide a link to the Troubleshooting section.

>2. Open `.env` and edit the following:  
>    ```properties
>    GITHUB_TOKEN=your_github_token_here
>    SOURCE_REPO=Focus-Bear/onboarding-generic
>    DEST_REPOS=["your-username-intern-repo"]
>    ```
>
>- Replace `your_github_token_here` with your **GitHub Personal Access Token**.
>- Replace `your-username-intern-repo` with your **new repository name**. Make sure it is enclosed in [" and "]  
>- Example .env file:
>
>    ```properties
>    GITHUB_TOKEN=github_pat_11A22B33C_d4e5f6g7h8i9j0k1l2m3n4o5p6q7r8s9t0u1v2w3x4y5z
>    SOURCE_REPO=Focus-Bear/onboarding-generic
>    DEST_REPOS=["amanda-intern-repo"]
>    ```
>
>   *If this step is causing you some issues, check out the [**Troubleshooting**](#-troubleshooting) section below*.

