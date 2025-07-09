# 🧠 Git Multi-User Setup

> Configure Git to automatically switch between personal and work identities based on the folder where each project lives.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Git Config](https://img.shields.io/badge/git-conditional--include-blue)
![Maintained](https://img.shields.io/badge/status-maintained-brightgreen)

---

Many developers use the same computer for both personal (e.g., GitHub) and work (e.g., GitLab) projects. This can lead to commits being made under the wrong identity.

This repository demonstrates how to configure Git to **automatically use the correct user and email** based on the directory where each project is located.

---

## 💡 Why this matters

- Prevents identity mix-ups between projects.
- Keeps your work history clean and organized.

---

## ⚠️ About `~` and Windows compatibility

In this guide, `~` represents your **home directory**.

- On Linux/macOS/WSL: `~` expands to `/home/your-username/` or `/Users/your-username/`
- On Windows (Command Prompt or PowerShell), use:
  - `%USERPROFILE%` in Command Prompt
  - `$HOME` or `$env:USERPROFILE` in PowerShell

> 💡 If you're using Git Bash or WSL on Windows, `~` works just like in Linux/macOS.

---

## 📦 Files included

- [`setup_git_users.md`](./setup_git_users.md): Step-by-step setup guide.
- [`./.config/git/gitconfig_work`](./.config/git/gitconfig_work): Example config for work-related projects.

---

## 📁 Recommended directory structure

You can rename these folders to suit your workflow:

```bash

~/personal_projects/   # Personal projects (e.g., GitHub)
~/work_projects/       # Work or team projects (e.g., GitLab)

```

---

## 🛠️ How it works

Git is configured to:

- Use your **personal identity globally**
- Switch to your **work identity automatically** when inside a designated folder

---

## 📜 License

MIT License. Free to use and adapt.

---

## ✨ Contributing

Spotted something useful to add? Feel free to open a PR or fork the repo.

---