# ☁️ YVC-CloudDev Academy — AWS S3 & CloudFront Static Website

A beautiful, multi-page static website about **AWS S3 and CloudFront** — demonstrating how to host, secure, and deliver static websites using AWS cloud services. The site is automatically deployed to S3 and the CloudFront cache is invalidated via GitHub Actions using OIDC authentication.

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=github-actions&logoColor=white)
![AWS S3](https://img.shields.io/badge/AWS_S3-569A31?style=flat&logo=amazon-s3&logoColor=white)
![CloudFront](https://img.shields.io/badge/CloudFront-8C4FFF?style=flat&logo=amazon-aws&logoColor=white)

---

## 🏗️ Architecture

```
Developer → git push → GitHub Actions → AWS OIDC Auth → S3 Sync → CloudFront Invalidation
                                                          ↓
                                                     S3 Bucket (origin)
                                                          ↓
                                                  CloudFront CDN (450+ edge locations)
                                                          ↓
                                                  Users (HTTPS, low latency)
```

## 📁 Project Structure

```
├── index.html              # Home page — hero, features, S3+CloudFront workflow demo
├── about.html              # About page — mission, timeline, team
├── courses.html            # Courses page — S3, CloudFront, HTTPS, WAF, optimization
├── projects.html           # Projects page — AWS hosting project showcase
├── contact.html            # Contact page — form, AWS FAQ, info
├── css/
│   └── style.css           # Complete responsive stylesheet
├── js/
│   └── main.js             # Interactive features & animations
├── images/
│   ├── logo.svg            # Site logo
│   ├── favicon.svg         # Browser favicon
│   ├── hero-illustration.svg
│   ├── about-team.svg
│   ├── global-map.svg
│   ├── contribute.svg
│   ├── avatar-*.svg        # Testimonial avatars
│   ├── team-*.svg          # Team member photos
│   ├── course-*.svg        # Course card illustrations
│   ├── project-*.svg       # Project card illustrations
│   ├── icon-*.svg          # Feature & social icons
│   └── ...
├── .github/
│   └── workflows/
│       ├── deploy.yml                # 🚀 Auto-deploy to GitHub Pages
│       ├── deploy-s3.yml             # ☁️ Auto-deploy to AWS S3 via OIDC
│       ├── deploy-s3-CloudFront.yml  # ☁️🔄 Deploy to S3 + CloudFront cache invalidation
│       ├── validate.yml              # ✅ HTML/CSS/JS validation on PR & push
│       ├── welcome.yml               # 👋 Welcome new contributors
│       └── link-check.yml            # 🔗 Weekly external link checker
└── README.md
```

## 🎯 GitHub Actions Workflows

This repo includes **6 workflows**:

| Workflow | Trigger | What It Does |
|----------|---------|-------------|
| **Deploy** | Push to `main` | Deploys site to GitHub Pages |
| **Deploy S3** | Push to `main` | Deploys site to AWS S3 using OIDC |
| **Deploy S3 + CloudFront** | Push to `main` | Deploys to S3 **and** invalidates CloudFront cache |
| **Validate** | Push & PR to `main` | Checks HTML structure, CSS/JS existence, internal links |
| **Welcome** | New issue or PR | Posts a friendly welcome message |
| **Link Check** | Weekly (Monday) | Validates all external URLs aren't broken |

## ☁️ AWS Services Used

| Service | Purpose |
|---------|---------|
| **S3** | Static website hosting — stores HTML, CSS, JS, and image files |
| **CloudFront** | CDN — caches and delivers content from 450+ global edge locations |
| **Certificate Manager (ACM)** | Free SSL/TLS certificates for HTTPS |
| **Shield Standard** | DDoS protection (included at no extra cost) |
| **IAM + OIDC** | Secure authentication from GitHub Actions (no static keys) |

## 🔄 How the CloudFront Deployment Works

1. **Push to `main`** — triggers the `deploy-s3-CloudFront.yml` workflow
2. **OIDC Auth** — GitHub proves its identity to AWS, assumes an IAM role (no secret keys stored)
3. **S3 Sync** — only changed files are uploaded to the S3 bucket
4. **CloudFront Invalidation** — clears cached content at all edge locations so users see updates immediately

### GitHub Secrets Required

| Secret | Description |
|--------|-------------|
| `AWS_ROLE_ARN` | IAM Role ARN with S3 and CloudFront permissions |
| `S3_BUCKET_NAME` | Name of the S3 bucket hosting the website |
| `CLOUDFRONT_DIST_ID` | CloudFront Distribution ID for cache invalidation |

## 🚀 Quick Start

### 1. Fork this repository
Click the **Fork** button at the top right of this page.

### 2. Set up AWS
1. Create an S3 bucket with static website hosting enabled
2. Create a CloudFront distribution pointing to your S3 bucket
3. Set up an IAM role with OIDC trust for your GitHub repo
4. Add the three secrets (`AWS_ROLE_ARN`, `S3_BUCKET_NAME`, `CLOUDFRONT_DIST_ID`) in **Settings** → **Secrets and variables** → **Actions**

### 3. Push a change
Edit any file, commit, and push. Watch the **Actions** tab — your site will be deployed to S3 and the CloudFront cache will be invalidated automatically!

## 🌟 Website Features

- **5 Pages** — Home, About, Courses, Projects, Contact
- **AWS-focused content** — S3 hosting, CloudFront CDN, HTTPS, WAF, Lambda@Edge
- **Fully Responsive** — Works on mobile, tablet, and desktop
- **Modern Design** — Gradient accents, glass-morphism navbar, smooth animations
- **Interactive JS** — Animated counters, testimonial slider, course filters, form handling, particle effects
- **30+ SVG Images** — Lightweight, scalable, no external dependencies
- **Zero Dependencies** — Pure HTML, CSS, and JavaScript
- **Accessible** — Semantic HTML, ARIA labels, keyboard navigation

## 🎓 What You'll Learn

By studying this project, you'll understand:

- **AWS S3 static hosting** — Buckets, policies, and website configuration
- **CloudFront CDN** — Distributions, caching, edge locations, and invalidation
- **HTTPS with ACM** — Free SSL/TLS certificates for custom domains
- **Security** — Origin Access Control, AWS WAF, DDoS protection
- **GitHub Actions + AWS OIDC** — Secure CI/CD without static credentials
- **Cost optimization** — Edge caching to reduce S3 requests and bandwidth

## 🛠️ Local Development

No build tools needed! Just open any `.html` file in your browser, or use a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve .

# Using VS Code
# Install "Live Server" extension, then right-click index.html → "Open with Live Server"
```

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

---

**Built with ❤️ and hosted on AWS S3 + CloudFront.**
