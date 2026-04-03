# Git Guide — First Steps

Git is a tool for saving and sharing code in an organized way. Think of it as a "history" of your project that multiple people can use at the same time.

---

## 1. Create a GitHub Account
1. Go to [github.com](https://github.com) and click **Sign up**.
2. Create your account using your email and a password.
3. Confirm the verification email you receive.

---

## 2. Choose Your Workflow
Choose the option you prefer—both do the same thing.

* **Option A — GitHub Desktop (Recommended for beginners):** A visual interface that doesn't require typing commands.
* **Option B — Terminal:** More powerful and widely used in the industry. Requires typing commands.

---

## 3. Installation

### Option A — GitHub Desktop
1. Go to [desktop.github.com](https://desktop.github.com).
2. Click **Download for Windows** and install normally.
3. When opened, click **Sign in to GitHub.com** and log in with your account.

### Option B — Terminal
1. Go to [git-scm.com/downloads](https://git-scm.com/downloads).
2. Download and install using the default options.
3. Open the **Command Prompt** (cmd) and verify the installation:
   ```bash
   git --version
   ```
   If it shows something like `git version 2.x.x`, it is working.
4. Configure your name and email (you only need to do this once):
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your@email.com"
   ```

---

## 4. Clone the League Repository
Cloning means downloading the repository to your machine.

### Option A — GitHub Desktop
1. Go to the league's repository page on GitHub.
2. Click the green **Code** button and select **Open with GitHub Desktop**.
3. Choose an easy-to-access folder and click **Clone**.

### Option B — Terminal
1. Open the **Command Prompt**:
   * Press `Windows + R`, type `cmd`, and hit Enter.
   * **Tip:** In Windows Explorer, navigate to the folder where you want to save the repo, click the address bar, type `cmd`, and hit Enter—the terminal will open directly in the correct folder.
2. Run the following command:
   ```bash
   git clone [https://github.com/link-to-repository](https://github.com/link-to-repository)
   ```
   A folder with all the files will be created in your chosen location.

---

## 5. Basic Workflow
Every time you contribute, follow this sequence:

### Step 1 — Download the latest updates before starting
* **GitHub Desktop:** Click **Fetch origin** at the top. If **Pull origin** appears, click it too.
* **Terminal:** `git pull`

### Step 2 — Make your changes
Edit the files as usual. GitHub Desktop detects changes automatically. In the terminal, use `git status` to see what has changed.

### Step 3 — Stage the files you want to save
* **GitHub Desktop:** In the **Changes** tab, check only the files you want to include.
* **Terminal:** `git add .` (The dot means "all changed files." You can replace it with a specific file name: `git add my_file.vhd`).

### Step 4 — Save with a message explaining what you did
* **GitHub Desktop:** In the **Summary** field (bottom left), write your message and click **Commit to main**.
* **Terminal:** `git commit -m "add binary counter tutorial"`

### Step 5 — Send to GitHub
* **GitHub Desktop:** Click **Push origin** at the top of the screen.
* **Terminal:** `git push`

---

## 6. How to Write a Good Commit Message
The message is the record of what was done. Keep it short and clear:

* [CORRECT] `add binary counter tutorial`
* [CORRECT] `fix error in Vivado installation tutorial`
* [CORRECT] `update README in tutorials folder`
* [WRONG] `changes`
* [WRONG] `fixed some stuff`
* [WRONG] `asdfgh`

---

## Common Errors

**"Push origin" button blocked / "Permission denied"**
You need access permissions for the repository. Contact the league board to be added as a collaborator.

**"Pull origin" appeared before you could Push (GitHub Desktop)**
Someone uploaded something before you. Click **Pull origin** first, then try the **Push** again.

**"Please pull before pushing" (Terminal)**
Same situation as above. Run `git pull` first, then `git push`.

**File Conflicts**
This happens when two people edit the same line of the same file at the same time. Contact another member to resolve it together.

---

## References
* GitHub Desktop: [desktop.github.com](https://desktop.github.com)
* Official Git Documentation: [git-scm.com/doc](https://git-scm.com/doc)
* GitHub Docs: [docs.github.com](https://docs.github.com)
```
