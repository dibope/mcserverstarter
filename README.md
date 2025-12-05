# Seedloaf MC Server Starter
Selenium script to automatically start/stop your Seedloaf Minecraft server using GitHub Actions

**⏱️ Setup Time:** 5-10 minutes

## ⚠️ Before You Start
If you created your Seedloaf account through Discord (not email), you need to do this first or the automation won't work:
1. Add an email to your Seedloaf account
2. Unlink Discord from your account
3. Change your password in the security tab
4. You can re-link Discord after this

---

## Contents
- [Choose Your Setup Method](#choose-your-setup-method)
  - [🤖 Option A: For the Discord Bot users](#-option-a-for-the-discord-bot-users)
  - [👥 Option B: For Github users](#-option-b-for-github-users)
- [Setup for Discord Bot](#setup-for-discord-bot)
  - [Step 1: Fork This Repository](#step-1-fork-this-repository)
  - [Step 2: Enable GitHub Actions](#step-2-enable-github-actions)
  - [Step 3: Add Your Seedloaf Credentials as Secrets](#step-3-add-your-seedloaf-credentials-as-secrets)
  - [Step 4: Create a Personal Access Token](#step-4-create-a-personal-access-token)
  - [Step 5: Connect the Bot to Your Repository](#step-5-connect-the-bot-to-your-repository)
- [Manual Setup](#manual-setup)
  - [Step 1: Fork This Repository](#step-1-fork-this-repository-1)
  - [Step 2: Enable GitHub Actions](#step-2-enable-github-actions-1)
  - [Step 3: Add Your Seedloaf Credentials as Secrets](#step-3-add-your-seedloaf-credentials-as-secrets-1)
  - [Step 4: Test That It Works](#step-4-test-that-it-works)
  - [Step 5: Add Your Friends as Collaborators](#step-5-add-your-friends-as-collaborators)
  - [Step 6: Protect Your Code from Changes](#step-6-protect-your-code-from-changes)
- [How to Run the Workflow](#how-to-run-the-workflow)
- [Common Problems](#common-problems)
- [How It Works](#how-it-works)

---

## Choose Your Setup Method

This thing can be used in two ways. Choose the setup flow you want:

### 🤖 Option A: For the [Discord Bot](https://discord.com/oauth2/authorize?client_id=1365006964001738993) users 
**->** for people who want to use the discord bot


[**→ Jump to Setup for Discord Bot**](#discord-bot-setup)

---

### 👥 Option B: For Github users
**->** People who want friends to run it directly from GitHub, or don't wanna use Discord bot. They need github account.


[**→ Jump to Setup for Github users**](#manual-setup)

---

## Setup for Discord Bot

The Discord bot triggers this GitHub thing for you.

### Step 1: Fork This Repository
**Fork** means making your own copy of this thing.

Click the **Fork** button in the top right corner:

![image](https://github.com/user-attachments/assets/d48923e8-4281-4cb3-8b5d-aa3f60cad51e)

### Step 2: Enable GitHub Actions
GitHub Actions (the automation) is disabled by default in forked repositories.

Go to the **Actions** tab in your forked repository and enable it

![image](https://github.com/user-attachments/assets/f0f136c6-83b9-4469-b503-1577447a9c15)

### Step 3: Add Your Seedloaf Credentials as Secrets

**Secrets** are hidden that only this github thing can see. Nobody (not even you after saving them) can view them.


![repo_secrets1](https://github.com/dibope/mcserverstarter/blob/main/.github/workflows/Images/repo_secrets1.jpg)

1. Go to **Settings** → **Secrets and variables** → **Actions** → **Repository secrets**
2. Click **New repository secret**
3. Create two secrets like that:
   - Name: `USERNAME` | Value: Your Seedloaf **Email**
   - Name: `PASSWORD` | Value: Your Seedloaf **Password**
4. Try to start server. 
See the [Instructions.md](https://github.com/dibope/mcserverstarter/blob/main/Instructions.md) file for a detailed visual guide.

> **Note:** These credentials are completely private and secure. GitHub encrypts them and they cannot be viewed by anyone after you save them.

### Step 4: Create a Personal Access Token

The Discord bot needs permission to trigger workflows in YOUR forked repository. To give it access, you need to create a special key called a "token".

**Go to your GitHub profile settings** (not repository settings):
1. Click your profile picture → **Settings**
2. Scroll down to **Developer settings** (bottom of left sidebar)
3. Click **Personal access tokens** → **Fine-grained tokens**
4. Click **Generate new token**

**Configure the token:**
- **Expiration:** No expiration (or set a long duration)
- **Repository access:** Select "All repositories" (or just your forked repo)
- **Permissions:** Set these two permissions ONLY:
  - **Actions:** Read and Write
  - **Workflows:** Read and Write
    
>  Copy the token immediately - you can't see it again! (you can reset the token tough)

> [!WARNING]
> Do NOT give **Contents** permission or any other permissions except the mentioned ones! This would let the anyone with token edit your fork. So check if these are the final permissions

![image](https://github.com/user-attachments/assets/763a4470-551a-4489-82cb-a5625eaa36b1)

![PAT1](https://github.com/dibope/workflowtrigger_bot/blob/main/PAT1.jpg)
![PAT2](https://github.com/dibope/workflowtrigger_bot/blob/main/PAT2.jpg)



### Step 5: Connect the Bot to Your Repository

Now you need to give the token to the Discord bot. For instructions on how to do this, use the `/help` command in Discord after inviting the bot.

[**Invite the Discord Bot**](https://discord.com/oauth2/authorize?client_id=1365006964001738993)

✅ **You're done with Github setup Discord Bot!**

---

## Manual Setup

This setup lets you and your friends rin this thing directly from GitHub's Actions tab.

### Step 1: Fork This Repository
**Fork** means making your own copy of this project.

Click the **Fork** button in the top right corner:

![image](https://github.com/user-attachments/assets/d48923e8-4281-4cb3-8b5d-aa3f60cad51e)

### Step 2: Enable GitHub Actions
GitHub Actions (the automation) is disabled by default in forked repositories.

1. Go to the **Actions** tab in your forked repository
2. Click the green button to enable workflows

![image](https://github.com/user-attachments/assets/f0f136c6-83b9-4469-b503-1577447a9c15)

### Step 3: Add Your Seedloaf Credentials as Secrets

**Secrets** are hidden passwords that only the automation can see. Nobody (not even you after saving them) can view them.

1. Go to **Settings** → **Secrets and variables** → **Actions** → **Repository secrets**
2. Click **New repository secret**
3. Create two secrets:
   - Name: `USERNAME` | Value: Your Seedloaf email
   - Name: `PASSWORD` | Value: Your Seedloaf password

![repo_secrets1](https://github.com/dibope/mcserverstarter/blob/main/.github/workflows/Images/repo_secrets1.jpg)

> [!NOTE]
> These credentials are completely private and secure. GitHub encrypts them and they cannot be viewed by anyone after you save them.

### Step 4: Test That It Works

1. Go to the **Actions** tab
2. Click **Run Selenium Script** (in the left sidebar)
3. Click the **Run workflow** button (top right)
4. Click **Run workflow** again in the dropdown
5. Wait 10-15 seconds and refresh the page
6. Click on the workflow run to see the logs and verify it worked

![start_mc](https://github.com/dibope/mcserverstarter/blob/main/.github/workflows/Images/startmc.jpg)

✅ **You're done!** Your server should now be starting.

### Step 5: Add Your Friends as Collaborators

If you want your friends to be able to start/stop the server:

1. Go to **Settings** → **Collaborators** → **Add people**
2. Enter their GitHub username
3. Give them **Write** access (they need this to run workflows)

![collaboraters](https://github.com/dibope/mcserverstarter/blob/main/.github/workflows/Images/collaboraters.jpg)

> **⚠️ Important:** After adding collaborators, proceed to Step 6 to prevent them from accidentally breaking the automation!

### Step 6: Protect Your Code from Changes

**Branch Protection** prevents anyone (including collaborators) from directly editing the main code. They can still run the workflow, just not break it.

1. Go to **Settings** → **Branches** → **Add branch protection rule**
2. In "Branch name pattern" type: `main`
3. Check **"Require status checks to pass before merging"**
4. In the search box, type `fail-job` and select it
5. Click **Create** at the bottom

![fail_job1](https://github.com/dibope/mcserverstarter/blob/main/.github/workflows/Images/fail_job1.jpg)
![fail_job2](https://github.com/dibope/mcserverstarter/blob/main/.github/workflows/Images/fail_job2.jpg)

**What this does:** The `fail-job` workflow always fails, which means no one can merge code changes into your main branch. You can still run the server start/stop workflow normally.

✅ **Setup complete!** Share the [Instructions.md](https://github.com/dibope/mcserverstarter/blob/main/Instructions.md) file with your friends or revome this readme file and rename that file to readme so they know how to run the workflow.

---

## How to Run the Workflow

See the [Instructions.md](https://github.com/dibope/mcserverstarter/blob/main/Instructions.md) file for a detailed visual guide.

**Quick version:**
1. Go to **Actions** tab
2. Click **Run Selenium Script**
3. Click **Run workflow** → **Run workflow** again
4. To stop the server: Use the dropdown and change "start or stop" to `false`
5. To store login session : set it to `true'

**⏱️ How long does it take?** The server typically starts within 40-60 seconds after the workflow completes. Faster if you use session (enabled in discord or while runnning the wrokflow from github)

---

## Common Problems

### 1. Workflow doesn't appear in Actions tab
✅ **Fix:** Make sure you enabled workflows in the Actions tab (Step 2 in either setup)

![image](https://github.com/user-attachments/assets/f0f136c6-83b9-4469-b503-1577447a9c15)

### 2. Check logs
✅ **Fix:** Check the workflow logs for error messages:
1. Go to **Actions** tab
2. Click on your failed workflow run
3. Click **"Run Selenium Start/Stop Script"** to expand the logs
4. Look for red error messages

![image](https://github.com/user-attachments/assets/b29081d0-19ab-43d9-8316-5598566a15e1)
![image](https://github.com/user-attachments/assets/d7cc5fcb-01d7-47d7-ac26-f2b2dd96e715)

### 3. Discord Account Login Issue (Important!)
If you created your Seedloaf account through Discord, the automation won't work even if you added a email and password later.

✅ **Fix:**
1. Go to your Seedloaf account settings
2. Add an email address if not yet
3. **Unlink your Discord account**
4. Change your password in the Security tab
5. Now you can re-link Discord if you want

This is required because Seedloaf treats Discord-only accounts differently from email accounts.
### 4. "Password incorrect" or "Username incorrect" error
✅ **Fix:** Check your repository secrets:
1. Go to **Settings** → **Secrets and variables** → **Actions**
2. Delete and recreate the `USERNAME` and `PASSWORD` secrets
3. Make sure there are no extra spaces when pasting

### 5. Workflow shows "Already logged in" but server doesn't start
✅ **Fix:** The session cache might be stale.
1. Run the workflow again or delete the session cache in **Actions** tab



### 6. Using the old selenium file
If nothing else works, try using the older version:
1. Go to `.github/workflows/`
2. Rename `selenium.yml` to `selenium_new.yml`
3. Rename `selenium_working.yml` to `selenium.yml`
4. Commit the changes
- Still stuck? Open an Issue in this repository
- my discord `dibope5834_95850`
---

## How It Works

1. It installs **Chrome browser** and **Python**
2. The **Selenium script** opens Chrome, goes to Seedloaf, logs in with your credentials, optionally saves login session if you enable in discord or github
4. It clicks the Start/Stop button and closes

---
