# 🚀 YVC-CloudDev Academy — GitHub Actions Demo Website

A beautiful, multi-page static website built to **learn and teach GitHub Actions**. This project includes working CI/CD workflows, automated validation, and auto-deployment to GitHub Pages and AWS S3.

🌐 **Live on S3:** [http://githubactions-s3website-demo-hfs736.s3-website-us-east-1.amazonaws.com/](https://githubactions-s3website-demo-hfs736.s3-website-us-east-1.amazonaws.com/)

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=github-actions&logoColor=white)

---

## 📁 Project Structure

```
├── index.html              # Home page — hero, features, testimonials
├── about.html              # About page — mission, timeline, team
├── courses.html            # Courses page — filterable course cards
├── projects.html           # Projects page — portfolio showcase
├── contact.html            # Contact page — form, FAQ, info
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
│       ├── deploy.yml      # 🚀 Auto-deploy to GitHub Pages
│       ├── deploy-s3.yml   # ☁️ Auto-deploy to AWS S3 via OIDC
│       ├── validate.yml    # ✅ HTML/CSS/JS validation on PR & push
│       ├── welcome.yml     # 👋 Welcome new contributors
│       └── link-check.yml  # 🔗 Weekly external link checker
└── README.md
```

## 🎯 GitHub Actions Workflows

This repo includes **5 workflows** for learning:

| Workflow | Trigger | What It Does |
|----------|---------|-------------|
| **Deploy** | Push to `main` | Deploys site to GitHub Pages |
| **Deploy S3** | Push to `main` | Deploys site to AWS S3 using OIDC (no static keys!) |
| **Validate** | Push & PR to `main` | Checks HTML structure, CSS/JS existence, internal links |
| **Welcome** | New issue or PR | Posts a friendly welcome message |
| **Link Check** | Weekly (Monday) | Validates all external URLs aren't broken |

## 🚀 Quick Start

### 1. Fork this repository
Click the **Fork** button at the top right of this page.

### 2. Enable GitHub Pages
1. Go to your fork's **Settings** → **Pages**
2. Under **Source**, select **GitHub Actions**
3. The deploy workflow will run automatically on your next push

### 3. Push a change
Edit any file, commit, and push. Watch the **Actions** tab to see your workflows run!

## 🌟 Features

- **5 Pages** — Home, About, Courses, Projects, Contact
- **Fully Responsive** — Works on mobile, tablet, and desktop
- **Modern Design** — Gradient accents, glass-morphism navbar, smooth animations
- **Interactive JS** — Animated counters, testimonial slider, course filters, form handling, particle effects
- **30+ SVG Images** — Lightweight, scalable, no external dependencies
- **4 GitHub Actions Workflows** — Real CI/CD for learning
- **Zero Dependencies** — Pure HTML, CSS, and JavaScript
- **Accessible** — Semantic HTML, ARIA labels, keyboard navigation

## 🎓 What You'll Learn

By studying this project, you'll understand:

- **Workflow YAML syntax** — `on`, `jobs`, `steps`, `uses`
- **Deployment automation** — Auto-deploy on push to `main`
- **Validation pipelines** — Check code quality on every PR
- **Scheduled workflows** — Cron-based recurring tasks
- **GitHub Script action** — Automate GitHub API interactions
- **Permissions & environments** — Secure deployment configuration
- **Concurrency control** — Prevent duplicate deployments

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

**Built with ❤️ for the GitHub Actions community.**
