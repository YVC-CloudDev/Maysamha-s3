# GitHub Setup Guide

Quick start guide for deploying your portfolio to GitHub Pages (free option).

## Step 1: Create GitHub Repository

1. **Go to GitHub.com** and log in
2. **Create new repository**:
   - Click "+" → "New repository"
   - Repository name: `username.github.io` (replace `username` with YOUR GitHub username)
   - Description: "My student portfolio"
   - Make it **Public**
   - Click "Create repository"

> **Note**: If you want a project repo instead, name it anything and enable Pages later. You'll access it at `username.github.io/repo-name`

## Step 2: Initialize Git Locally

```bash
# Navigate to your project folder
cd path/to/Test

# Initialize git
git init

# Add remote (copy from GitHub repository)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git

# Rename branch to main (if needed)
git branch -M main
```

## Step 3: Commit and Push Code

```bash
# Stage all files
git add .

# Commit with message
git commit -m "Initial portfolio upload"

# Push to GitHub
git push -u origin main
```

> First push may ask for authentication. Use **Personal Access Token** (not password):
> - GitHub Settings → Developer settings → Personal access tokens
> - Generate token with `repo` scope
> - Use token as password when prompted

## Step 4: Enable GitHub Pages

1. **Go to your repository** on GitHub
2. **Click Settings** (top menu bar)
3. **Go to Pages** (left sidebar)
4. **Source**:
   - Branch: `main`
   - Folder: `/ (root)`
   - Click "Save"
5. **Wait 1-2 minutes**, then visit: `https://YOUR_USERNAME.github.io/REPO_NAME`

> **For `username.github.io` repo**: Your site is at `https://YOUR_USERNAME.github.io`

## Step 5: Add Custom Domain (Optional)

1. **In Pages settings**, scroll to "Custom domain"
2. **Enter your domain**: `yourdomain.com`
3. **Update DNS** at your domain registrar:
   - Add CNAME record pointing to `username.github.io`
   - Wait 24 hours for propagation
4. **Check "Enforce HTTPS"** (GitHub provides free SSL)

## Making Updates

Every time you update your portfolio:

```bash
# Edit files locally

# Stage changes
git add .

# Commit
git commit -m "Update portfolio content"

# Push to GitHub
git push
```

Your site updates automatically in ~1 minute!

## Common Git Commands

```bash
# Check status
git status

# View commit history
git log --oneline

# Undo last commit (keep changes)
git reset --soft HEAD~1

# See changes before committing
git diff

# Revert to specific commit
git checkout <commit-id> -- filename
```

## Workflow Best Practices

### Using Branches (Optional for Learning)

```bash
# Create feature branch
git checkout -b feature/add-projects

# Make changes & commit

# Push branch
git push -u origin feature/add-projects

# Create Pull Request on GitHub for review
# Merge when ready
```

## Troubleshooting

| Problem | Solution |
|---------|----------|
| "fatal: not a git repository" | Run `git init` in project folder |
| "permission denied" on push | Use Personal Access Token, not password |
| GitHub Pages not updating | Wait 2 minutes after push, clear browser cache |
| 404 on custom domain | Check DNS CNAME record, wait for propagation |
| File permissions issues | Run: `git config core.fileMode false` |

## Performance Tips

- Compress images before uploading
- Minify HTML/CSS/JS (optional for beginners)
- Use asset folders: `assets/images/`, `assets/css/`, `assets/js/`
- Limit large files (ideal: <100MB repo)

## Next: Upgrade to AWS (When Ready)

Once comfortable with GitHub Pages, follow [AWS_SETUP.md](AWS_SETUP.md) for:
- Professional hosting with CDN
- Better performance & scalability
- Custom domain support
- Advanced deployment automation

---

**You're all set! 🚀 Your portfolio is live on GitHub Pages!**
