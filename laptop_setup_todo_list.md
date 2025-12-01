# Laptop Setup TODO (Manual Steps + Post-Install Checks)

Everything below represents the **required manual actions** that cannot or should not be automated.
All OS-level configuration, developer tooling, VS Code setup, Homebrew installs, and macOS defaults
are already handled by the `./mac` script.

---

## 1. SSH Keys (required for GitHub)

1. Generate a new SSH key:
   https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key
2. Add the key to your GitHub account:
   https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

---

## 2. Logitech M510 Mouse Setup

1. Download Logi Options+:
   https://www.logitech.com/software/logi-options-plus.html
2. Configure:
   - Back/forward buttons
   - App-specific shortcuts
   - Pointer speed

---

## 3. System Settings (manual items)

These cannot be reliably scripted across macOS releases.

### Desktop & Screen Saver

- Choose wallpaper
- Set screen saver if desired

### Date & Time

- Enable “Show date”

### Sharing

- Set Computer Name (example: `robert-mpa-m4`)

### Battery Icon

- Enable “Show Percentage”

### Dock Icons

- Remove unwanted apps
- Pin frequently used apps (VS Code, Terminal, Chrome, Slack, etc.)

---

## 4. Browser Setup (Chrome)

1. Open Chrome
2. Set as default browser
3. Sign into your Google account
4. Sync extensions & settings

---

## 5. Password Manager

1. Open your password manager
2. Sign in and unlock vault

---

## 6. Cloud Storage

1. Open **Google Drive for Desktop**
2. Sign in
3. Confirm folder syncing preferences

---

## 7. VS Code

Your settings + keybindings are already installed by the script.

Remaining manual steps:

1. Install recommended extensions:

   - Ruby LSP (ruby-lsp.ruby-lsp)
   - Prettier (esbenp.prettier-vscode)
   - GitLens (eamodio.gitlens)
   - Docker (ms-azuretools.vscode-docker)
   - PostgreSQL (ms-ossdata.vscode-postgresql)
   - endwise
   - vscode-run-rspec-file
   - Any Bark-specific extensions

2. Log into:
   - GitHub inside VS Code
   - Settings Sync (optional)

---

## 8. App Logins (manual by design)

- Slack
- Zoom
- Notion
- Work onboarding accounts
- Any personal/work SaaS

---

## 9. Final System Touches

- Adjust display resolution if needed
- Arrange monitor layout (if external display)
- Verify screenshot folder is working: `~/Documents/Screenshots`
- Verify Dock + Trackpad behavior feels correct

---

# Post-Install Checks (Fast Verification)

These checks confirm the `./mac` script completed correctly
and your development environment is ready.

---

## 1. Homebrew

```sh
brew doctor
brew --version
```

You should NOT see errors (warnings are fine).

---

## 2. Ruby (rbenv)

```sh
rbenv -v
rbenv versions
```

#### or to install new ruby versions

```
rbenv install -s 3.4.x
rbenv global 3.4.x
rbenv rehash
ruby -v
```

---

## 3. Node (nvm)

```sh
nvm ls
node -v
npm -v
```

#### or to install new node versions

```
nvm install node
node -v
```

---

## 4. PostgreSQL & Redis

```sh
brew services list
```

You should see:

- `postgresql` → started
- `redis` → started

---

## 5. Docker

- Whale icon appears in the menu bar
- `docker info` runs without failure once Docker finishes initializing

---

## 6. VS Code Configuration

- Open VS Code
- Confirm settings.json is applied
- Confirm keybindings.json is functional (test shortcuts)

---

## 7. Screenshot Folder

Verify a screenshot (Cmd+Shift+5) lands in:

```
~/Documents/Screenshots
```

---

## 8. Trackpad / Mission Control / Dock

Verify the script’s automated settings:

- Tap-to-click works
- Spaces are not rearranging
- Dock auto-hides
- No “Recent Apps” section

---

## 9. Git Identity

```sh
git config --global user.name
git config --global user.email
```

---

## 10. SSH Key Test

```sh
ssh -T git@github.com
```

You should see successful authentication.

---

## 11. Avatar

Confirm the file exists:

```
~/Documents/avatar.jpg
```

---

## 12. Brewfile Completeness

Optional:

```sh
brew bundle cleanup --file=~/Workspace/laptop/Brewfile
```

---

# Completed Setup

When all checklist items and post-install checks pass,
your laptop is fully ready for Bark development and personal work.
