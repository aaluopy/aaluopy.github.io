# Personal Blog

A clean, minimal static blog built with Jekyll and hosted on GitHub Pages. Features a navigation-focused homepage and automatic deployment via GitHub Actions.

## ✨ Features

- **Clean Design**: Minimal, responsive design focused on readability
- **Navigation-Focused Homepage**: Homepage provides navigation rather than displaying posts
- **Table of Contents**: Automatic TOC generation for blog posts
- **Search Functionality**: Built-in search for posts and pages
- **Category & Tag Organization**: Easy content discovery
- **GitHub Actions Deployment**: Automatic build and deployment to GitHub Pages
- **SEO Optimized**: Built-in SEO tags and sitemap generation
- **RSS Feed**: Keep readers updated with new content

## 🚀 Quick Start

### Prerequisites

- Ruby 3.1 or higher
- Bundler gem
- Git

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/aaluopy/aaluopy.github.io.git
   cd aaluopy.github.io
   ```

2. **Install dependencies**
   ```bash
   bundle install
   ```

3. **Start the development server**
   ```bash
   bundle exec jekyll serve
   ```

4. **Open your browser**
   Navigate to `http://localhost:4000`

### GitHub Pages Deployment

1. **Fork or clone this repository**

2. **Enable GitHub Pages**
   - Go to repository Settings
   - Navigate to Pages section
   - Set Source to "GitHub Actions"

3. **Configure the site**
   - Edit `_config.yml` with your information
   - Update author details, site URL, and social links

4. **Push to main branch**
   - GitHub Actions will automatically build and deploy your site

## 📁 Project Structure

```
.
├── _config.yml          # Site configuration
├── _layouts/             # Page layouts
│   ├── default.html      # Base layout
│   ├── home.html         # Homepage layout
│   └── post.html         # Blog post layout
├── _includes/            # Reusable components
│   ├── head.html         # HTML head section
│   ├── header.html       # Site header with navigation
│   ├── footer.html       # Site footer
│   ├── social.html       # Social media links
│   └── toc.html          # Table of contents generator
├── _posts/               # Blog posts
├── _sass/                # Sass stylesheets
├── assets/               # Static assets
├── .github/workflows/    # GitHub Actions
│   └── jekyll.yml        # Build and deploy workflow
├── about.md              # About page
├── posts.md              # All posts page
├── categories.md         # Categories page
├── tags.md               # Tags page
├── collections.md        # Collections page
├── index.md              # Homepage
├── Gemfile               # Ruby dependencies
└── README.md             # This file
```

## ✍️ Writing Posts

### Creating a New Post

1. **Create a new file** in `_posts/` directory with the format:
   ```
   YYYY-MM-DD-title-of-post.md
   ```

2. **Add front matter** at the beginning:
   ```yaml
   ---
   layout: post
   title: "Your Post Title"
   date: 2024-01-20 14:30:00 +0800
   categories: [category1, category2]
   tags: [tag1, tag2, tag3]
   author: aaluopy
   ---
   ```

3. **Write your content** using Markdown

### Post Features

- **Automatic TOC**: Table of contents is generated automatically for h2 and h3 headings
- **Syntax Highlighting**: Code blocks with language-specific highlighting
- **Categories & Tags**: Organize content with categories and tags
- **SEO**: Automatic meta tags and structured data

## 🎨 Customization

### Site Configuration

Edit `_config.yml` to customize:

```yaml
# Site settings
title: "Your Blog Title"
subtitle: "Your Subtitle"
description: "Your blog description"
url: "https://yourusername.github.io"

# Author settings
author:
  name: "Your Name"
  email: "your-email@example.com"
  github: "yourusername"
  gitlab: "yourusername"
```

### Navigation Menu

Customize the navigation menu in `_config.yml`:

```yaml
navigation:
  - title: "Posts"
    url: "/posts/"
  - title: "Categories"
    url: "/categories/"
  - title: "Tags"
    url: "/tags/"
  - title: "Collections"
    url: "/collections/"
  - title: "About"
    url: "/about/"
```

### Styling

- Custom CSS can be added to `_includes/head.html`
- Sass files can be created in `_sass/` directory
- Override default styles by creating `assets/main.scss`

## 🔧 Advanced Configuration

### Adding Google Analytics

1. Add your tracking ID to `_config.yml`:
   ```yaml
   google_analytics: UA-XXXXXXXX-X
   ```

2. Create `_includes/google-analytics.html` with your tracking code

### Custom Domain

1. Add a `CNAME` file to the repository root:
   ```
   yourdomain.com
   ```

2. Configure DNS settings with your domain provider

### Comments

To add comments, integrate with services like:
- Disqus
- Utterances (GitHub-based)
- Giscus (GitHub Discussions-based)

## 📱 Responsive Design

The blog is fully responsive and optimized for:
- Desktop computers
- Tablets
- Mobile phones
- Various screen sizes and orientations

## 🔍 SEO Features

- Automatic sitemap generation
- SEO-friendly URLs
- Meta tags and Open Graph tags
- Structured data markup
- RSS feed
- Fast loading times

## 🤝 贡献

欢迎提交 Issues 和 Pull Requests！

## 📄 许可

本项目采用 MIT 许可证。

## 🙏 致谢

感谢 Jekyll 和 GitHub Pages 提供的优秀服务。

## 📞 支持

如有问题，请通过以下方式联系：

- **GitHub**: [github.com/aaluopy](https://github.com/aaluopy)
- **GitLab**: [gitlab.com/aaluopy](https://gitlab.com/aaluopy)

---

**Happy blogging!** 🎉