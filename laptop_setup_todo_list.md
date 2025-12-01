# Laptop Setup TODO (2025 Apple Silicon Edition)

A streamlined checklist for setting up a fresh macOS machine for Ruby on Rails development.

---

## 1. Create SSH Keys (GitHub)

1. Generate a new SSH key:  
   https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

2. Add the new SSH public key to GitHub:  
   https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

---

## 2. System Settings Tweaks

### Finder → Settings → Sidebar
- Enable “Home” (`/Users/roberttaraya`)
- Add/remove folders as needed

### Desktop & Dock
- Enable **Show items with clock**
- Hide recent apps
- Auto-hide Dock
- Remove unneeded Dock items

### Trackpad
- Enable **Tap to click**

### Date & Time
- Enable **Show day of week/date**

### General → Sharing
- Set computer name (e.g., “Robert-MBA-Work”)

### Control Center
- Enable **Battery Percentage**

### Screenshots
- Press `Cmd + Shift + 5` → Options  
  Choose **Documents/Screenshots**
- Change default screenshot format:
  ```
  defaults write com.apple.screencapture type jpg
  killall SystemUIServer
  ```

---

## 3. iTerm2 Setup

1. Open iTerm2 once to initialize preferences.
2. Preferences → General → Settings  
   Enable **Load preferences from a custom folder or URL**  
   Set path:  
   `~/Library/Application Support/iTerm2/`
3. Relaunch iTerm2.

---

## 4. Rectangle Setup (Spectacle Replacement)

1. Open Rectangle  
2. Grant Accessibility permissions  
3. Enable **Launch at login**  
4. Verify Spectacle-style shortcuts (Rectangle uses them by default)

---

## 5. Chrome Setup

1. Launch Chrome  
2. Set as default browser  
3. Sign in and enable sync (extensions, bookmarks, history)

---

## 6. Google Drive Setup

1. Open the **Google Drive** app  
2. Sign in  
3. Choose sync preferences

---

## 7. VS Code Setup

### Install Command Line Tool

1. Open VS Code  
2. Press `Cmd + Shift + P`  
3. Type:  
   **Shell Command: Install 'code' command in PATH**

### Recommended Extensions (2025 Rails Workflow)

These replace older, deprecated Ruby extensions and provide the fastest, most accurate Ruby + Rails development experience.

#### **Core Ruby / Rails Extensions**
- **Ruby LSP** (Shopify – modern, official Ruby language server)
- **endwise** (auto-close Ruby blocks)
- **vscode-run-rspec-file** (quickly run current spec)

#### **Backend / Dev Tools**
- **DotENV**
- **PostgreSQL**
- **Docker**
- **Prettier**

#### **Productivity**
- **Scratchpads**
- **Sublime Text Keymap and Settings Importer**

#### **Optional**
- **Go to Spec** (if you prefer quicker spec jumps)
- **GitLens** (highly recommended for git insight)
- **Jest Runner** (only if working in JS-heavy repos)

#### Removed / Deprecated Extensions
These should NOT be installed anymore:
- Solargraph  
- Ruby (Peng Lv)  
- VSCode Ruby  
- ImportJS  
- Any older Ruby language server plugins  

---

## 8. Logitech M510 Mouse Setup

1. Download Logi Options+:  
   https://www.logitech.com/software/logi-options-plus.html  
2. Configure:  
   - Back/forward buttons  
   - App-specific shortcuts  
   - Pointer speed  

---

## 9. Post-Install Checks

### Ruby
```
rbenv install -s 3.3.x
rbenv global 3.3.x
ruby -v
```

### Node
```
nvm install node
node -v
```

### Postgres & Redis
```
brew services list
```

### Docker
```
open -ga Docker
```

---

## 10. Preference Files (Auto-installed by mac script)

- `~/.zshrc`
- `~/.gitconfig`
- `~/.gitignore_global`
- `~/Documents/laptop_setup_todo_list.md`
- `~/Documents/avatar.jpg`

---

## 11. Bark Work Setup (Optional)

- Sign into Bark accounts (Google, Slack, etc.)
- Install Bark internal tools (VPN or internal apps)
- Configure Git remotes for Bark repositories
- Set per-project Ruby/Node versions as needed

---

# End of Checklist
