# Quick Start Checklist

Complete this checklist to get your portfolio live!

## Phase 1: Local Development (15 min)

- [ ] Edit `index.html` with your name & info
- [ ] Update projects section with YOUR projects
- [ ] Customize colors in `styles.css` if desired
- [ ] Test locally: open `index.html` in browser
- [ ] Verify all links work

## Phase 2: GitHub Pages (30 min) - RECOMMENDED FOR BEGINNERS

Follow [GITHUB_SETUP.md](GITHUB_SETUP.md):

- [ ] Create GitHub account (if none)
- [ ] Create `username.github.io` repository
- [ ] Clone repository locally
- [ ] Copy your files to cloned folder
- [ ] Run: `git add .`
- [ ] Run: `git commit -m "Initial portfolio"`
- [ ] Run: `git push origin main`
- [ ] Enable GitHub Pages in Settings
- [ ] Visit `https://username.github.io` ✅ LIVE!
- [ ] Share link with friends/employers

## Phase 3: AWS Deployment (1-2 hours) - OPTIONAL UPGRADE

Follow [AWS_SETUP.md](AWS_SETUP.md) for professional hosting:

- [ ] Create AWS account
- [ ] Create S3 bucket
- [ ] Enable static website hosting
- [ ] Upload files to S3
- [ ] Set bucket policy to public
- [ ] Create CloudFront distribution
- [ ] Copy distribution domain URL ✅ LIVE!
- [ ] (Optional) Add custom domain
- [ ] Create GitHub Actions secrets
- [ ] Test auto-deployment on code push

## Phase 4: Custom Domain (30 min) - OPTIONAL

### Option A: GitHub Pages + Free Domain
- [ ] Get free domain: freenom.com or similar
- [ ] Add CNAME file to repository
- [ ] Update GitHub Pages settings with domain
- [ ] Update DNS at domain registrar
- [ ] Test domain (wait 24-48 hours)

### Option B: AWS Route 53 + Custom Domain
- [ ] Purchase domain in Route 53 (or use existing)
- [ ] Update CloudFront with domain in CNAME
- [ ] Create Route 53 DNS records
- [ ] Test domain (wait 24-48 hours)

## Phase 5: Portfolio Optimization - ONGOING

- [ ] Add your photo/avatar
- [ ] Write compelling "About" section
- [ ] Link to GitHub profile
- [ ] Add resume/CV download
- [ ] Include social media links
- [ ] Optimize images (<100KB each)
- [ ] Test on mobile device
- [ ] Get feedback from friends

## Phase 6: Share & Promote - FINAL STEP

- [ ] Update LinkedIn with portfolio link
- [ ] Add to GitHub profile bio
- [ ] Share on social media
- [ ] Send to potential employers/recruiters
- [ ] Add to resume
- [ ] Keep portfolio updated with new projects

---

## Recommended Path for Students

### Start Here (Week 1)
1. Complete Phase 1 (Local Development)
2. Complete Phase 2 (GitHub Pages)
3. Share with friends ✅

### Next (Week 2-3)
4. Add more content & projects
5. Get feedback
6. Make improvements

### Advanced (Later)
7. (Optional) Upgrade to AWS (Phase 3)
8. (Optional) Add custom domain (Phase 4)

---

## File Reference

| File | Purpose |
|------|---------|
| `index.html` | Main page structure (EDIT ME!) |
| `styles.css` | Styling & layout |
| `script.js` | Interactivity & animations |
| `README.md` | Project documentation |
| `GITHUB_SETUP.md` | GitHub Pages setup |
| `AWS_SETUP.md` | AWS S3/CloudFront setup |
| `.gitignore` | Files to ignore in Git |
| `.github/workflows/deploy.yml` | Automated AWS deployment |

## Time Investment

- Local setup: 15 minutes
- GitHub Pages: 30 minutes
- AWS (optional): 1-2 hours
- Content creation: Ongoing
- **Total to go live: ~45 minutes** ✅

## Key Commands Reference

```bash
# Local testing
# Double-click index.html in File Explorer

# Git commands
git init                    # Initialize repository
git add .                   # Stage all changes
git commit -m "message"     # Commit changes
git push origin main        # Push to GitHub
git status                  # Check status
git log --oneline          # View history
```

## Help Resources

- **GitHub Pages**: https://pages.github.com
- **AWS S3**: https://docs.aws.amazon.com/s3/
- **Web Development**: https://developer.mozilla.org
- **Student Discounts**: GitHub Student Pack, AWS Education

---

## Success Indicators ✅

- [ ] Website loads without errors
- [ ] All links work
- [ ] Responsive on mobile
- [ ] Content is accurate
- [ ] Links to your GitHub
- [ ] Shows your projects
- [ ] Professional appearance

---

**Ready? Start with Phase 1 & 2 - you'll have a live portfolio in 45 minutes!** 🚀

Questions? Re-read the setup guides or check the official documentation.
