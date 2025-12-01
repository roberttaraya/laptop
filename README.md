# 📘 Laptop Setup Guide (2025)

Automated, idempotent setup script for configuring a new macOS laptop (optimized for Ruby / Rails, VS Code, and modern development defaults).  
This repo installs Homebrew, core development tooling, VS Code config, dotfiles, and your personal baseline preferences.

Everything here is **self-contained** — no external gists or cloud dependencies beyond a few dotfiles.

---

## 🚀 Quick Start

Clone the repo into your Workspace folder:

```bash
mkdir -p ~/Workspace
cd ~/Workspace
git clone git@github.com:roberttaraya/laptop.git
cd laptop
```

Make the script executable:

```bash
chmod +x mac
```

Run setup:

```bash
./mac
```

This script is **idempotent** — you can safely re-run it anytime.

---

## 📦 What Gets Installed

### **Homebrew packages & casks**
Defined in your `Brewfile`:

- Ruby ecosystem (rbenv, openssl, postgres, redis)
- Node ecosystem (nvm)
- Development tools (git, gh, docker, rectangle, tableplus)
- Browsers (Google Chrome)
- VS Code
- Other core utilities

Nothing extra — all distractions removed.

---

## 🛠 What the `mac` Script Configures

### **Shell**
- Installs `.zshrc` (if missing)
- Ensures `brew` shellenv is added
- Configures rbenv + nvm automatically
- Idempotent environment setup

### **Homebrew**
- Instills Homebrew if missing
- `brew update`, `brew upgrade`, `brew cleanup`
- Runs `brew bundle` using repo-local Brewfile

### **Services**
- Starts PostgreSQL
- Starts Redis
- Launches Docker once to finalize setup

### **Dotfiles**
Automatically installs if the file doesn’t already exist:

- `.gitconfig`
- `.gitignore_global`
- `laptop_setup_todo_list.md`

### **VS Code Configuration**  
Pulled from the repo:

```
vscode/settings.json
vscode/keybindings.json
```

These are copied into:

```
~/Library/Application Support/Code/User/
```

### **Personal Files**
- Copies `avatar.jpg` into `~/Documents/avatar.jpg`

---

## 📁 Repo Structure

```
laptop/
  mac
  Brewfile
  avatar.jpg
  vscode/
    settings.json
    keybindings.json
  laptop_setup_todo_list.md
  README.md
```

---

## 📝 After Running the Script

You’ll need to complete a few manual steps:

- Configure VS Code extensions (Ruby LSP, Prettier, GitLens, etc.)
- Log into Chrome
- Adjust system preferences
- Set up your Logitech mouse
- Confirm SSH keys & GitHub auth
- Review the `laptop_setup_todo_list.md` file

---

## ♻️ Idempotency

The script:

- Only installs files if missing  
- Will not overwrite your local dotfiles  
- Can be run safely at any time  
- Can be used on future laptops with zero modification  

---

## 🙋 Need to Verify Your Setup?

```bash
which brew
brew doctor
rbenv --version
nvm --version
code --version
```

All should return valid results.

---

## ✔️ Summary

This repo now represents a **complete, deterministic development environment bootstrap** for a 2025 MacBook Air M4 focused on Ruby on Rails, TypeScript, and VS Code.

You're future-proof.
