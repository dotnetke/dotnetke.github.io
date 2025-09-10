# .NET Kenya Community Website
The .NET Kenya Community Website (dotnetke.github.io) is a GitHub Pages organization site for the .NET Kenya developer community built with Docusaurus, a modern static site generator optimized for creating documentation websites.

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

## Working Effectively

### Environment Setup
The build environment has Node.js available:
- Node.js v20.19.5 is pre-installed at `/usr/local/bin/node`
- npm 10.8.2 is available

### Docusaurus Development (Primary Approach)

#### Project Structure
```
/home/runner/work/dotnetke.github.io/dotnetke.github.io/
├── README.md                      # Repository documentation
├── .git/                          # Git repository
├── .github/                       # GitHub configuration
│   └── copilot-instructions.md    # This file
├── .gitignore                     # Git ignore patterns
├── package.json                   # Node.js dependencies and scripts
├── docusaurus.config.js           # Docusaurus configuration
├── sidebars.js                    # Documentation sidebar configuration
├── src/                           # Source files
│   ├── components/                # React components
│   ├── css/                       # Global CSS
│   └── pages/                     # Static pages
├── docs/                          # Documentation content (Markdown)
├── blog/                          # Blog posts (Markdown)
├── static/                        # Static assets (images, fonts, etc.)
└── build/                         # Generated site (git ignored)
```

#### Initial Setup
- Install project dependencies:
  ```bash
  npm install
  ```
  - NEVER CANCEL: npm install takes 30-120 seconds. Set timeout to 3+ minutes.
  - Installs Docusaurus and all required dependencies

#### Development Server
- Run Docusaurus development server:
  ```bash
  npm start
  ```
  - NEVER CANCEL: Initial build takes 10-30 seconds. Set timeout to 1+ minute.
  - Server runs on http://localhost:3000
  - Auto-regeneration enabled for live development
  - Hot reloading for instant preview of changes

#### Production Build
- Build site for production:
  ```bash
  npm run build
  ```
  - Build completes in 10-30 seconds
  - Output goes to `build/` directory
  - Optimized for deployment to GitHub Pages

#### Serving Production Build
- Test production build locally:
  ```bash
  npm run serve
  ```
  - Serves the built site from `build/` directory
  - Runs on http://localhost:3000
  - Use this to test before deploying

### GitHub Pages Deployment

#### Automatic Deployment
- GitHub Pages automatically builds and deploys Docusaurus sites
- Push to main branch triggers automatic deployment
- Site is available at https://dotnetke.github.io

#### Manual Deployment
- Deploy using Docusaurus built-in command:
  ```bash
  npm run deploy
  ```
  - Builds and pushes to gh-pages branch
  - Requires proper Git configuration

## Content Management

### Documentation (docs/)
- All documentation goes in the `docs/` folder
- Use Markdown (.md) files
- Frontmatter controls sidebar position and metadata:
  ```markdown
  ---
  sidebar_position: 1
  title: Page Title
  ---
  ```

### Blog Posts (blog/)
- Blog posts go in the `blog/` folder
- Use date prefix: `YYYY-MM-DD-post-title.md`
- Frontmatter for metadata:
  ```markdown
  ---
  slug: custom-url-slug
  title: Post Title
  authors: [author-name]
  tags: [tag1, tag2]
  ---
  ```

### Static Assets (static/)
- Images, fonts, and other assets go in `static/`
- Referenced as `/img/filename.png` in Markdown
- Favicon and logo files are in `static/img/`

### Pages (src/pages/)
- Custom React pages for special functionality
- Homepage is `src/pages/index.js`
- Additional pages create new routes

### Components (src/components/)
- Reusable React components
- Can be imported in Markdown and other React files
- Homepage features in `src/components/HomepageFeatures/`

## Configuration

### Site Configuration (docusaurus.config.js)
- Main configuration file for the entire site
- Contains site metadata, navigation, footer, and plugin settings
- GitHub Pages specific settings already configured

### Sidebar Configuration (sidebars.js)
- Controls documentation sidebar structure
- Can be auto-generated or manually defined
- Currently set to auto-generate from `docs/` folder structure

### Styling (src/css/custom.css)
- Global CSS customizations
- Override Infima CSS variables for theming
- Dark/light mode support built-in

## Validation

### Manual Testing Requirements
- ALWAYS test the complete user flow after making changes
- For Docusaurus sites:
  - Verify homepage loads with hero section and features
  - Test navigation menu (Docs, Blog, GitHub links)
  - Check documentation sidebar navigation
  - Verify blog posts display and are accessible
  - Test search functionality (if enabled)
  - Confirm responsive design on different screen sizes
- ALWAYS run through at least one complete end-to-end scenario after making changes
- Take screenshots of any UI changes to verify visual impact
- Expected validation results:
  - Homepage shows community title, tagline, and three feature cards
  - Documentation section has working sidebar and content
  - Blog section displays posts with proper formatting
  - All links functional and properly styled

### Build Validation
- Always run the full build process before committing:
  ```bash
  npm run build
  
  # Check that build directory contains expected files
  ls -la build/
  ```
- Build should complete without errors or warnings
- Generated HTML files should be present in `build/` directory

### Performance Testing
- Check build performance with:
  ```bash
  npm run build -- --analyze
  ```
- Monitor bundle size and loading performance
- Ensure images are optimized

## Common Tasks

### Adding New Documentation
1. Create new `.md` file in `docs/` folder
2. Add frontmatter with `sidebar_position` and `title`
3. Write content in Markdown
4. Test with `npm start`
5. Verify in sidebar navigation

### Creating Blog Posts
1. Create new file in `blog/` with date prefix
2. Add complete frontmatter (title, authors, tags, slug)
3. Write content in Markdown
4. Test with `npm start`
5. Verify on blog listing page

### Customizing Theme
1. Edit `src/css/custom.css` for global styles
2. Modify CSS variables for color scheme
3. Create custom React components in `src/components/`
4. Update `docusaurus.config.js` for navigation/footer changes

### Adding Images
1. Place images in `static/img/` directory
2. Reference as `![Alt text](/img/filename.png)` in Markdown
3. For React components, import: `require('@site/static/img/filename.png').default`

## Troubleshooting

### Build Failures
- Clear cache and rebuild:
  ```bash
  npm run clear
  npm run build
  ```

### Development Server Issues
- Stop server (Ctrl+C) and restart:
  ```bash
  npm start
  ```
- Clear node_modules if needed:
  ```bash
  rm -rf node_modules package-lock.json
  npm install
  ```

### Module Not Found Errors
- Ensure all dependencies are installed:
  ```bash
  npm install
  ```
- Check import paths in React components
- Verify file extensions (.js, .jsx, .md)

### GitHub Pages Deployment Issues
- Verify `docusaurus.config.js` has correct `url` and `baseUrl`
- Check that `organizationName` and `projectName` match GitHub settings
- Ensure build completes successfully before deployment

## Development Workflow
1. Set up environment (npm install)
2. Create or modify content (docs, blog, components)
3. Test locally with development server (npm start)
4. Validate build process (npm run build)
5. Test production build (npm run serve)
6. Verify all functionality manually
7. Push to GitHub (triggers automatic deployment)

## Performance Notes
- npm install: 30-120 seconds
- Development server startup: 10-30 seconds
- Production build: 10-30 seconds
- Hot reload updates: <1 second
- GitHub Pages deployment: 1-3 minutes after push

**CRITICAL**: Always wait for installation and build commands to complete. Set timeouts appropriately and NEVER CANCEL long-running operations.

## Expected Output Examples

### Development Server Start
```
$ npm start
> docusaurus start

Starting the development server...
Docusaurus website is running at: http://localhost:3000/

✔ Client
  Compiled successfully in 2.34s

ℹ ｢wds｣: Project is running at http://localhost:3000/
```

### Production Build
```
$ npm run build
> docusaurus build

Creating an optimized production build...

✔ Client
  Compiled successfully in 12.34s

Success! Generated static files in "build".
```

### Project Dependencies
The site uses these key dependencies:
- @docusaurus/core: Core Docusaurus functionality
- @docusaurus/preset-classic: Standard theme and plugins
- React: UI library (managed by Docusaurus)
- MDX: Enhanced Markdown with React components