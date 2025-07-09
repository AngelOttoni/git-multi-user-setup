# **Git Multi-User Configuration Guide**

This guide explains how to configure Git to automatically switch between personal and work identities based on the folder where each project is located.

---

## 💼 Example directory structure

> You can rename these folders as you prefer.

- Personal projects: `~/personal_projects/`
- Work projects: `~/work_projects/`

---

## 🧠 About `~` in file paths

In this guide, we use `~` to represent your **home directory**.

- On Linux/macOS/WSL: `~` expands to something like `/home/your-username/` or `/Users/your-username/`
- On Windows (without WSL), replace `~` with:
  - `%USERPROFILE%` in Command Prompt
  - `$HOME` or `$env:USERPROFILE` in PowerShell

> 💡 If you're using Git Bash or WSL, `~` works just like in Unix systems.

---

## 🌐 Global configuration (personal user)

File: `~/.gitconfig`

```ini
[user]
    name = your_personal_username
    email = your.personal.email@example.com

[includeIf "gitdir:~/work_projects/"]
    path = ~/.config/git/gitconfig_work
````

---

## 🧩 Conditional configuration (work user)

File: `~/.config/git/gitconfig_work`

```ini
[user]
    name = your_work_username
    email = your.work.email@example.com
```

---

## ✅ Verifying the setup

Inside a **personal** project folder:

```bash
git config user.name  # Expected: your_personal_username
```

Inside a **work** project folder:

```bash
git config user.name  # Expected: your_work_username
```

---

## 🪜 Step-by-step setup

1. Create the config directory (if needed):

   ```bash
   mkdir -p ~/.config/git
   ```

2. Create the work identity config file:

   ```bash
   nano ~/.config/git/gitconfig_work
   ```

   Example content:

   ```ini
   [user]
       name = your_work_username
       email = your.work.email@example.com
   ```

3. Edit your global Git config:

   ```bash
   nano ~/.gitconfig
   ```

   Add:

   ```ini
   [user]
       name = your_personal_username
       email = your.personal.email@example.com

   [includeIf "gitdir:~/work_projects/"]
       path = ~/.config/git/gitconfig_work
   ```

---

Once complete, Git will automatically apply the correct identity depending on which folder you're working in — no need to manually switch settings every time ✅

---