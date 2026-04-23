# Student Portfolio Website

A responsive static portfolio website built with HTML, CSS, and JavaScript. Ready to deploy on GitHub Pages and AWS S3/CloudFront.

## Features

- **Responsive Design**: Works on desktop, tablet, and mobile devices
- **Modern UI**: Clean, professional layout with smooth animations
- **Fast Loading**: Static site optimized for performance
- **SEO Friendly**: Semantic HTML structure
- **Easy to Customize**: Simple file structure for quick edits

## Project Structure

```
static-website/
│
├── index.html          # Main page
├── styles.css          # Styling
├── script.js           # JavaScript interactivity
├── README.md           # This file
├── .gitignore          # Git ignore rules
└── .github/
    └── workflows/
        └── deploy.yml  # GitHub Actions for AWS deployment
```

## Getting Started Locally

1. **Clone the repository**:
   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
   cd YOUR_REPO
   ```

2. **Open in a browser**:
   - Double-click `index.html` to open locally, OR
   - Use Live Server extension in VS Code (right-click → Open with Live Server)

3. **Edit content**:
   - Modify `index.html` for structure and content
   - Update `styles.css` for styling
   - Add interactivity in `script.js`

## Deployment Options

### Option 1: GitHub Pages (Free & Easy)

1. Push code to GitHub repository named `USERNAME.github.io`
2. Go to **Repository Settings** → **Pages**
3. Set source to `main` branch
4. Site goes live at `https://USERNAME.github.io`

**Pros**: Free, easy, instant updates on push  
**Cons**: Limited to GitHub domain (unless custom domain)

### Option 2: AWS S3 + CloudFront (Scalable)

1. **Create S3 Bucket**:
   - AWS Console → S3 → Create bucket (`my-student-site`)
   - Enable "Static website hosting"
   - Upload files (index.html, styles.css, script.js)

2. **Create CloudFront Distribution**:
   - Select S3 bucket as origin
   - Create distribution
   - Get distribution domain (e.g., `d111111abcdef8.cloudfront.net`)

3. **Optional: Custom Domain**:
   - Use Route 53 or external DNS registrar
   - Point domain to CloudFront distribution

4. **Auto-Deploy with GitHub Actions**:
   - Add AWS credentials to GitHub Secrets
   - Use `.github/workflows/deploy.yml` for automation

**Pros**: Professional, scalable, fast CDN, custom domain  
**Cons**: Small monthly cost (~$1-5 for low traffic)

## Customization Tips

### Update Portfolio Content
- Change name in `index.html` hero section
- Add your projects in the Projects section
- Update social media links in Contact section

### Customize Colors
- Main color: `#667eea` (purple-blue) - search & replace in `styles.css`
- Secondary: `#764ba2` (darker purple) - customizable

### Add Pages
- Create new `.html` files
- Link them in navbar
- Follow same styling with `<div class="container">`

## SEO Optimization

- Add meta description in `<head>`:
  ```html
  <meta name="description" content="My student portfolio...">
  ```
- Update title in `<title>` tag
- Add Open Graph tags for social sharing

## Performance Tips

- Optimize images: use TinyPNG or ImageOptim
- Minify CSS/JS in production
- Use lazy loading for images
- Enable gzip compression on AWS

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Site won't load on GitHub | Ensure branch is set to `main` in Pages settings |
| AWS S3 shows 403 Forbidden | Enable public read access in S3 bucket policy |
| DNS not working | Wait 24-48 hours for propagation |
| CloudFront not updating | Create invalidation for `/index.html` |

## Learning Resources

- [GitHub Pages Docs](https://pages.github.com)
- [AWS S3 Static Hosting](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)
- [MDN Web Docs](https://developer.mozilla.org)
- [CloudFront Docs](https://docs.aws.amazon.com/cloudfront/)

## Next Steps

1. ✅ Set up Git repository
2. ✅ Customize portfolio content
3. ✅ Deploy to GitHub Pages
4. ✅ Add custom domain (optional)
5. ✅ Scale to AWS (optional)
6. ✅ Share with potential employers!

## License

This project is open source. Feel free to use as a template for your portfolio.

---

**Happy Coding! 🚀**  
Built for students learning web development.
