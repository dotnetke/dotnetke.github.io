# .NET Kenya Community Website
The .NET Kenya Community Website (dotnetke.github.io) is a GitHub Pages organization site for the .NET Kenya developer community. The repository is currently minimal but can be developed as a Jekyll static site, plain HTML/CSS/JS site, or modern Node.js-based static site.

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

## Working Effectively

### Environment Setup
The build environment has both Ruby and Node.js available:
- Ruby 3.2.3 is pre-installed at `/usr/bin/ruby`
- Node.js v20.19.5 is pre-installed at `/usr/local/bin/node`
- npm 10.8.2 is available

### Jekyll Development (Recommended for GitHub Pages)

#### Initial Setup
- Install Jekyll and Bundler (required for GitHub Pages compatibility):
  ```bash
  gem install --user-install jekyll bundler
  export PATH="$PATH:/home/runner/.local/share/gem/ruby/3.2.0/bin"
  ```
  - NEVER CANCEL: Gem installation takes 2-4 minutes. Set timeout to 5+ minutes.

#### Create New Jekyll Site
- Create a new Jekyll site (use --force if directory is not empty):
  ```bash
  jekyll new . --skip-bundle --force
  ```
  - Takes 10-15 seconds to complete
  - Use --force flag when directory contains existing files (README.md, .github/, etc.)

#### Install Dependencies
- Install gems locally to avoid permission issues:
  ```bash
  bundle config set --local path 'vendor/bundle'
  bundle install
  ```
  - NEVER CANCEL: Bundle installation takes 3-5 minutes. Set timeout to 10+ minutes.
  - This installs gems to `vendor/bundle` to avoid system permission issues

#### Development Server
- Run Jekyll development server:
  ```bash
  export PATH="$PATH:/home/runner/.local/share/gem/ruby/3.2.0/bin"
  bundle exec jekyll serve --host=0.0.0.0 --port=4000
  ```
  - Site builds in 0.3-1 seconds
  - Server runs on http://localhost:4000
  - Auto-regeneration enabled for live development
  - Expect Sass deprecation warnings (normal and non-breaking)

#### Production Build
- Build site for production:
  ```bash
  export PATH="$PATH:/home/runner/.local/share/gem/ruby/3.2.0/bin"
  bundle exec jekyll build
  ```
  - Build completes in 0.5-1 second
  - Output goes to `_site/` directory

### Node.js Development (Alternative Approach)

#### Initial Setup
- Initialize Node.js project:
  ```bash
  npm init -y
  ```
  - Completes in 1-2 seconds

#### Static Site Serving
- For simple static HTML sites, install and use serve:
  ```bash
  npm install --save-dev serve
  echo '<h1>Test Page</h1>' > index.html
  npx serve .
  ```
  - NEVER CANCEL: npm install takes 30-60 seconds. Set timeout to 2+ minutes.
  - Site serves immediately on http://localhost:3000 (default port)

### Static HTML Development (Simplest Approach)
- For plain HTML/CSS/JS sites, no build process required
- Serve directly with Python or any web server:
  ```bash
  python3 -m http.server 4000
  ```
  - Starts immediately

## Validation

### Manual Testing Requirements
- ALWAYS test the complete user flow after making changes
- For Jekyll sites: 
  - Verify homepage loads and displays content correctly
  - Test navigation links (About page, post links)
  - Confirm RSS feed link works (http://localhost:4000/feed.xml)
  - Check that posts display properly and are accessible
- For static sites: Verify all pages load and links function properly
- ALWAYS run through at least one complete end-to-end scenario after making changes
- Take screenshots of any UI changes to verify visual impact
- Expected validation results:
  - Homepage should show site title, navigation, posts list, and footer
  - About page should load with content and working navigation
  - All links should be functional and properly styled

### Build Validation
- Always run the full build process before committing:
  ```bash
  # For Jekyll sites
  export PATH="$PATH:/home/runner/.local/share/gem/ruby/3.2.0/bin"
  bundle exec jekyll build
  
  # Check that _site directory contains expected files
  ls -la _site/
  ```

### GitHub Pages Compatibility
- GitHub Pages runs Jekyll automatically for `.github.io` repos
- Ensure `_config.yml` is properly configured
- Test locally first before pushing to verify GitHub Pages compatibility
- GitHub Pages uses specific gem versions - check their documentation for current versions

## Common Tasks

### Repository Structure (Current State)
```
/home/runner/work/dotnetke.github.io/dotnetke.github.io/
├── README.md                    # Original: "# .NET Kenya Community Website"  
├── .git/                        # Git repository
├── .github/                     # GitHub configuration
│   └── copilot-instructions.md  # This file
├── _config.yml                  # Jekyll configuration (after jekyll new)
├── _posts/                      # Blog posts directory (after jekyll new)
├── _site/                       # Generated site (git ignored)
├── Gemfile                      # Ruby dependencies (after jekyll new)
├── Gemfile.lock                 # Locked gem versions (after bundle install)
├── vendor/                      # Local gem installation (git ignored)
├── index.markdown               # Homepage (after jekyll new)
├── about.markdown               # About page (after jekyll new)
└── assets/                      # CSS, JS, images (after jekyll new)
```

### Common File Commands Output

#### Repository Root (After Jekyll Setup)
```
$ ls -la
total 48
drwxr-xr-x 5 runner runner 4096 Sep 10 15:12 .
drwxr-xr-x 3 runner runner 4096 Sep 10 15:02 ..
drwxrwxr-x 7 runner runner 4096 Sep 10 15:10 .git
drwxrwxr-x 2 runner runner 4096 Sep 10 15:11 .github
-rw-r--r-- 1 runner runner   56 Sep 10 15:12 .gitignore
-rw-r--r-- 1 runner runner  416 Sep 10 15:12 404.html
-rw-rw-r-- 1 runner runner 1307 Sep 10 15:12 Gemfile
-rw-rw-r-- 1 runner runner   31 Sep 10 15:03 README.md
-rw-r--r-- 1 runner runner 2079 Sep 10 15:12 _config.yml
drwxrwxr-x 2 runner runner 4096 Sep 10 15:12 _posts
-rw-r--r-- 1 runner runner  539 Sep 10 15:12 about.markdown
-rw-r--r-- 1 runner runner  175 Sep 10 15:12 index.markdown
```

#### Built Site Directory
```
$ ls -la _site/
total 44
drwxrwxr-x 5 runner runner 4096 Sep 10 15:13 .
drwxr-xr-x 9 runner runner 4096 Sep 10 15:13 ..
-rw-rw-r-- 1 runner runner 4819 Sep 10 15:13 404.html
-rw-rw-r-- 1 runner runner   31 Sep 10 15:03 README.md
drwxrwxr-x 2 runner runner 4096 Sep 10 15:13 about
drwxrwxr-x 2 runner runner 4096 Sep 10 15:13 assets
-rw-rw-r-- 1 runner runner 3555 Sep 10 15:13 feed.xml
-rw-rw-r-- 1 runner runner 4681 Sep 10 15:13 index.html
drwxrwxr-x 3 runner runner 4096 Sep 10 15:13 jekyll
```

#### Current README.md Content
```
$ cat README.md
# .NET Kenya Community Website
```

### Troubleshooting

#### Permission Issues with Gems
- If gem installation fails with permission errors, use `--user-install`:
  ```bash
  gem install --user-install jekyll bundler
  export PATH="$PATH:/home/runner/.local/share/gem/ruby/3.2.0/bin"
  ```

#### Bundle Install Failures
- If bundle install fails with permission errors, use local path:
  ```bash
  bundle config set --local path 'vendor/bundle'
  bundle install
  ```

#### Jekyll Not Found
- Always export PATH before using Jekyll commands:
  ```bash
  export PATH="$PATH:/home/runner/.local/share/gem/ruby/3.2.0/bin"
  ```

### Development Workflow
1. Set up environment (Ruby gems or Node.js packages)
2. Create or modify site content
3. Test locally with development server
4. Validate build process
5. Verify all functionality manually
6. Push to GitHub (triggers GitHub Pages build automatically)

### Performance Notes
- Ruby gem installation: 2-4 minutes
- Bundle install: 3-5 minutes  
- Jekyll build: 0.5-1 second
- Jekyll serve startup: 0.3-1 second
- npm package installation: 30-60 seconds
- Static site serving: Immediate

**CRITICAL**: Always wait for installation and build commands to complete. Set timeouts appropriately and NEVER CANCEL long-running operations.