# Paul Dal Pozzo

**Student ID:** s214527809  
**Email:** s214527809@deakin.edu.au  
**Intern Position:** Usability Tester & Bug Hunter  
**Focus Bear Account:** paul_dal_pozzo@hotmail.com  
**Markdown Location:** https://github.com/pdalpozzo/paul-dalpozzo-focusbear-intern-repo/blob/main/IssueWork/ENV_setup_confusion.md

# Issue 16
## Root Cause
Upon looking into the error handling message I found the root cause of the issue. The script attempts to immediately execute `JSON.parse(process.env.DEST_REPOS)` without a `try/catch` block or preliminary presence checks. If `DEST_REPOS` is empty, missing, or improperly formatted in the `.env` file, the script crashes instantly and throws a generic, unhelpful `SyntaxError: undefined is not valid JSON`.

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

## What is Valid in the Current Docs
The documentation is technically accurate. The `README.md` explicitly lists `DEST_REPOS` (plural) and instructs users to enclose the string inside `["` and `"]`. Additionally, `.env.sample` properly contains the bracketed layout example.

## What is Still Confusing for Beginners
- **Cryptic Error Message:** The unhandled JSON crash gives no contextual hint on how to fix the `.env` configuration.
- **Non-Standard Workflow Pattern:** Passing environment variables as raw JSON arrays is an uncommon pattern in development workflows that exposes beginners to strict formatting bugs (e.g., mixing up single vs. double quotes).
- **Documentation Visibility:** The formatting rules are buried in generic text steps rather than visually emphasized at the point of configuration.

While everything is technically correct and in place to help a beginner, there are still too many points of failure with no clear feedback loops. This can cause a user to become frustrated or panic, resulting in fewer chances of them solving the problem on their own.

### Suggestions
- **Provide better error messaging:** Include specific error messages for each variable in the `.env` configuration. This may require more initial work, but saves troubleshooting time for new users.
- **Clear up naming confusion:** Explicitly document expectations for `DEST_REPOS`.
- **Syntax Formatting:** Improve `README.md` documentation visibility and markdown styling.
- **Handle both `DEST_REPOS` and `DEST_REPO`:** Provide backward compatibility or dynamic fallbacks for `DEST_REPO` where feasible.

## Recommended Fix List (Priority Order)
### 1. Improve Error Handling
This code has a single line for parsing `DEST_REPOS`. It does not allow for any handling of errors. As a general rule/standard, variables that are parsed should be placed in a `try/catch`. This standard exists to prevent this exact issue. That way we can handle failed parses correctly.

#### Solution
<details>
  <summary>
    <b>Step 1:</b> We need to place the parsing into a 
    <span style="color: #BEAD7A; background-color: #353535; padding: 1px 2px;">try/catch</span>
    . Here we can provide an error message that specifies it is a parsing error.
  </summary>

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
  
</details><br>

<details>
  <summary><b>Step 2:</b> Remove parsing on a single line</summary>

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

</details><br>

<details>
  <summary><b>Step 3:</b> Check each variable individually and provide better error messages.</summary>

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

</details><br>


<details>
  <summary>
    <b>Step 4:</b> Add a check on the 
    <span style="color: #BEAD7A; background-color: #353535; padding: 1px 2px;">DEST_REPOS</span> 
    to ensure it is an array and not empty
  </summary>

  ```js
  if (!Array.isArray(DEST_REPOS) || DEST_REPOS.length === 0) {
    console.error('❌ Error: DEST_REPOS must be a non-empty array.');
    console.error('Example: DEST_REPOS=["username/repo-one", "username/repo-two"]');
    process.exit(1);
  }
  ```

</details><br>



<details>
  <summary>
  <b>Step 5 (Optional):</b> Add handling for 
    <span style="color: #BEAD7A; background-color: #353535; padding: 1px 2px;">DEST_REPO</span> 
    and provide a warning message. This should be placed after the 
    <span style="color: #BEAD7A; background-color: #353535; padding: 1px 2px;">SOURCE_REPO</span> 
    check and before the 
    <span style="color: #BEAD7A; background-color: #353535; padding: 1px 2px;">DEST_REPO</span> 
    check. 
  </summary>

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

</details><br>

---

### 2. Use Comments in `.env`
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
### 3. Improve Troubleshooting Section
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
>If you have encountered issues, check the common solutions below.
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

