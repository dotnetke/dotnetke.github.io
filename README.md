# .NET Kenya Community Website

Welcome to the official website repository for the .NET Kenya community! This website serves as the central hub for our vibrant community of .NET developers in Kenya.

## 🌐 Website

Visit our website at: [https://dotnetke.github.io](https://dotnetke.github.io)

## 🏗️ Built With

- **[Docusaurus](https://docusaurus.io/)** - Modern static site generator
- **React** - Frontend framework  
- **TypeScript** - Type-safe JavaScript
- **GitHub Pages** - Hosting platform

## 📁 Project Structure

```
.
├── .github/workflows/     # GitHub Actions for deployment
├── src/                   # Docusaurus source files
│   ├── blog/             # Blog posts and articles
│   ├── courses/          # Learning content and tutorials
│   ├── src/              # React components and pages
│   ├── static/           # Static assets (images, files)
│   └── docusaurus.config.ts  # Site configuration
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Node.js 18.0 or higher
- npm or yarn

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/dotnetke/dotnetke.github.io.git
   cd dotnetke.github.io
   ```

2. **Install dependencies**
   ```bash
   cd src
   npm install
   ```

3. **Start development server**
   ```bash
   npm start
   ```
   
   This opens the website at `http://localhost:3000`. The site reloads automatically when you make changes.

4. **Build for production**
   ```bash
   npm run build
   ```

## 📝 Contributing

We welcome contributions from the community! Here's how you can help:

### Adding Blog Posts

1. Create a new markdown file in `src/blog/`
2. Follow the naming convention: `YYYY-MM-DD-post-title.md`
3. Add frontmatter with title, authors, and tags
4. Write your content using Markdown

Example:
```markdown
---
slug: my-post-title
title: My Blog Post Title
authors: [your-github-username]
tags: [dotnet, csharp, tutorial]
---

Your blog post content here...
```

### Adding Course Content

1. Create content in `src/courses/`
2. Organize by topic (e.g., `dotnet-fundamentals/`, `aspnet-core/`)
3. Use clear, descriptive filenames
4. Include practical examples relevant to Kenyan developers

### Updating Event Information

1. Edit `src/src/pages/events.md`
2. Add upcoming events, speaker information, and resources
3. Include recording links and presentation materials for past events

## 🎨 Theme & Styling

The website uses a custom theme inspired by .NET brand colors:
- Primary: `#512bd4` (.NET Purple)
- The theme is defined in `src/src/css/custom.css`
- Responsive design for mobile and desktop

## 🔄 Deployment

The website is automatically deployed using GitHub Actions:

- **Trigger**: Push to `main` branch
- **Build**: Runs `npm run build` in the `src/` directory  
- **Deploy**: Uploads to GitHub Pages

The deployment workflow is defined in `.github/workflows/deploy.yml`.

## 🤝 Community Guidelines

- **Inclusive**: Content should be welcoming to developers of all skill levels
- **Local Context**: Include examples relevant to the Kenyan tech ecosystem
- **Quality**: Ensure content is accurate, well-written, and helpful
- **Attribution**: Give proper credit for code examples and resources

## 📞 Support

Need help? Reach out to us:

- **GitHub Issues**: [Report bugs or request features](https://github.com/dotnetke/dotnetke.github.io/issues)
- **Twitter**: [@dotnetke](https://twitter.com/dotnetke)
- **Meetup**: [.NET Kenya Community](https://www.meetup.com/net-kenya-community/)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Thanks to all community members who contribute content and ideas
- Built with ❤️ by the .NET Kenya community
- Special thanks to the Docusaurus team for the excellent documentation platform

---

**Karibu to .NET Kenya!** 🇰🇪 Welcome to our community!
