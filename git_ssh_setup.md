# Git Multi-Account Setup Reference

## 1. Per-Repo Remote URL

```bash
# SSH
git remote set-url origin git@github.com:USERNAME/REPO.git

# HTTPS with username (bypasses global creds)
git remote set-url origin https://USERNAME@github.com/USERNAME/REPO.git
git config --local credential.useHttpPath true
```

## 2. Per-Repo Git Identity

```bash
git config user.name "Your Name"
git config user.email "your@email.com"
```

## 3. SSH Key Setup

### Generate a key
```bash
ssh-keygen -t ed25519 -f ~/.ssh/github_personal
```

### Add to SSH agent
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/github_personal
```

### Add public key to GitHub
Settings → SSH and GPG keys → New SSH key

```bash
cat ~/.ssh/github_personal.pub
```

### Test connection
```bash
ssh -T git@github.com
```

## 4. SSH Key Override Strategies

### Option A: Per-repo (in the repo directory)
```bash
git config core.sshCommand "ssh -i ~/.ssh/github_personal"
```

### Option B: Global via `~/.ssh/config`
```
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/github_personal
```

## 5. Verify Settings

```bash
git remote -v
git config user.name
git config user.email
git config --local --list
```

## 6. Undo a Commit

```bash
# Keep changes staged
git reset --soft HEAD~1

# Keep changes unstaged (default)
git reset --mixed HEAD~1

# Discard changes entirely
git reset --hard HEAD~1

# Safe revert (already pushed)
git revert HEAD
```

## 7. Credential Management

Clear cached Windows credentials:
1. Open **Credential Manager**
2. **Windows Credentials** → **Generic Credentials**
3. Remove `git:https://github.com` or `github.com` entries
