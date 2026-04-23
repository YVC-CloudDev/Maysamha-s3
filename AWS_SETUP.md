# AWS Deployment Setup Guide

Complete guide for deploying your student portfolio to AWS S3 + CloudFront with GitHub Actions automation.

## Prerequisites

- AWS Account (create free at aws.amazon.com)
- GitHub Account with this repository
- AWS Access Key ID & Secret Access Key

## Step 1: Create S3 Bucket

1. **Log in to AWS Console**: https://console.aws.amazon.com
2. **Navigate to S3**:
   - Search for "S3" in the search bar
   - Click "Buckets"
3. **Create Bucket**:
   - Click "Create bucket"
   - Bucket name: `my-student-portfolio` (must be unique globally)
   - Region: `us-east-1`
   - **Uncheck** "Block all public access"
   - Click "Create bucket"

4. **Enable Static Website Hosting**:
   - Click your bucket name
   - Go to "Properties" tab
   - Scroll to "Static website hosting"
   - Click "Edit"
   - Enable "Static website hosting"
   - Index document: `index.html`
   - Click "Save changes"

5. **Upload Files**:
   - Go to "Objects" tab
   - Click "Upload"
   - Drag & drop: index.html, styles.css, script.js
   - Click "Upload"

## Step 2: Create S3 Bucket Policy (Make Public)

1. **Go to Bucket Policy**:
   - Click your bucket
   - Go to "Permissions" tab
   - Click "Bucket policy"

2. **Add Policy**:
   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "PublicReadGetObject",
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
       }
     ]
   }
   ```
   - Replace `YOUR-BUCKET-NAME` with your actual bucket name
   - Click "Save"

## Step 3: Create CloudFront Distribution (CDN)

1. **Navigate to CloudFront**:
   - Search for "CloudFront" in AWS Console
   - Click "Distributions"
   - Click "Create distribution"

2. **Configure Distribution**:
   - **Origin domain**: Select your S3 bucket from dropdown
   - **Name**: Leave as default
   - **S3 access**: Select "Yes use OAI"
   - Click "Create OAI" (if needed)
   - **Compress objects automatically**: Yes
   - Leave other settings as default
   - Click "Create distribution"

3. **Get Distribution Domain**:
   - Copy your **Distribution Domain Name** (e.g., `d111111abcdef8.cloudfront.net`)
   - Your site is now live at this URL!

## Step 4: Set Up GitHub Actions Secrets

1. **Create AWS Credentials**:
   - Go to AWS IAM → Users → Add user
   - Username: `github-deploy`
   - Check "Programmatic access"
   - Attach policy: `AmazonS3FullAccess` + `CloudFrontFullAccess`
   - Copy **Access Key ID** and **Secret Access Key**

2. **Add to GitHub Secrets**:
   - Go to your GitHub repo
   - Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Add:
     - `AWS_ACCESS_KEY_ID`: (paste from step 1)
     - `AWS_SECRET_ACCESS_KEY`: (paste from step 1)
     - `AWS_S3_BUCKET_NAME`: `my-student-portfolio`
     - `AWS_CLOUDFRONT_DISTRIBUTION_ID`: (from Step 3)

## Step 5: Test GitHub Actions Deployment

1. **Make a small change**:
   - Edit `index.html` (e.g., change a title)
   - Commit: `git add .` → `git commit -m "Update portfolio"`
   - Push: `git push origin main`

2. **Watch deployment**:
   - Go to GitHub repo
   - Click "Actions" tab
   - Watch workflow run
   - Check S3 bucket afterward

3. **Verify**:
   - Visit your CloudFront domain
   - Should see your updated content in ~30 seconds

## Step 6: Add Custom Domain (Optional)

### Option A: Route 53 (AWS DNS)

1. **Buy domain** in Route 53:
   - AWS Console → Route 53
   - Click "Register domain"
   - Search & purchase domain

2. **Create CloudFront alias**:
   - Go to CloudFront distribution
   - Settings → Edit
   - Add Alternate domain names (CNAME): `yourdomain.com`, `www.yourdomain.com`
   - Request SSL certificate (free)
   - Save

3. **Update DNS**:
   - Route 53 → Hosted zones
   - Create records pointing to CloudFront distribution

### Option B: External Domain Registrar

1. **Update nameservers** to Route 53 ones (if using Route 53)
   - OR manually point CNAME to CloudFront domain

2. **Update CloudFront** with your domain in CNAME

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| 403 Forbidden on S3 | Check bucket policy is set to public read |
| CloudFront shows old content | Create invalidation for `/*` |
| GitHub Actions fails | Check AWS credentials in Secrets |
| Domain not working | Wait 24-48 hours for DNS propagation |

## Cost Estimate (Monthly)

- **S3**: $0.023 per GB (first 50GB free tier)
- **CloudFront**: $0.085 per GB (1TB free tier)
- **Route 53**: $0.50 per hosted zone
- **Domain**: $8-15 (if Route 53)

**Total for small site**: ~$0-5/month (free tier usually covers it!)

## Security Best Practices

✅ Use IAM user (not root account) for GitHub Actions  
✅ Limit IAM permissions to only S3 & CloudFront  
✅ Enable CloudFront HTTPS (automatic)  
✅ Enable S3 versioning for backups  
✅ Use bucket encryption  

## Next Steps

1. ✅ Create S3 bucket
2. ✅ Enable static hosting
3. ✅ Create CloudFront distribution
4. ✅ Set up GitHub Actions secrets
5. ✅ Push code to trigger auto-deployment
6. ✅ Share your live portfolio!

---

**Questions?** Check AWS documentation or contact AWS support.
