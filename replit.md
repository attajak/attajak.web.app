# Attajak Personal Website

## Project Overview
This is a personal blog and portfolio website built with Hugo static site generator using the FixIt theme. The site showcases blog posts, projects, and social links for Attajak Janrak.

## Technology Stack
- **Static Site Generator**: Hugo v0.147.3 (extended version)
- **Theme**: FixIt v0.3.20
- **Language**: Go 1.24.1
- **Build Tool**: Hugo modules
- **Components**: Hugo FixIt theme with various components (projects, translate, caniuse, etc.)

## Project Structure
```
.
├── archetypes/          # Content templates
├── assets/             # CSS, JS, and images
│   ├── css/           # Custom styles
│   └── js/            # Custom JavaScript
├── config/            # Hugo configuration
│   ├── _default/      # Default configuration files
│   ├── development/   # Development environment config
│   └── production/    # Production environment config
├── content/           # Markdown content
│   ├── posts/         # Blog posts
│   ├── projects/      # Projects section
│   └── about.md       # About page
├── data/              # Data files (projects, rewards)
├── layouts/           # Custom Hugo templates
├── static/            # Static assets (favicon, images)
└── themes/            # Hugo themes (managed by modules)
```

## Development Setup in Replit

### Environment
- Hugo server runs on port 5000 (required for Replit)
- Development environment uses relative URLs
- Drafts and future posts are enabled in development

### Running the Site
The site automatically starts when you open the Replit. The Hugo server workflow is configured to:
- Bind to 0.0.0.0 on port 5000
- Enable drafts, future posts, and expired content
- Use relative URLs for proper preview
- Disable fast render for complete rebuilds

### Configuration Notes
1. **Port Configuration**: The site is configured to run on port 5000 for Replit compatibility
2. **Base URL**: Development uses "/" for relative URLs to work with Replit's proxy
3. **Components**: Some FixIt components (flyfish, mdevtools) are disabled due to version compatibility issues
4. **Hugo Modules**: Dependencies are managed through Go modules (go.mod)

## Deployment
The site is configured for autoscale deployment on Replit:
- Build command: `npm run build` (builds production site)
- Run command: Hugo server in production mode
- Static files are generated in the `public/` directory

## Recent Changes (2025-10-28)
1. Installed Hugo and Go 1.24 toolchain
2. Configured Hugo server to run on port 5000
3. Fixed hugo.work file (removed non-existent FixIt directory reference)
4. Updated development configuration for Replit environment
5. Disabled incompatible FixIt components (flyfish, mdevtools) to resolve template errors
6. Configured deployment settings for production

## Content Management
- Posts are written in Markdown in `content/posts/`
- Projects data is managed in `data/projects.yml`
- Use `npm run create` to create new content
- Frontmatter configuration is in `config/_default/frontmatter.toml`

## Theme Customization
- Custom CSS: `assets/css/_custom.scss`
- Custom overrides: `assets/css/_override.scss`
- Custom JavaScript: `assets/js/custom.js`
- Custom partials: `layouts/_partials/custom.html`

## Author Information
- Name: Attajak Janrak
- Email: janrak@gmail.com
- GitHub: https://github.com/attajak
- Repository: https://github.com/attajak/attajak.web.app

## License
This project is licensed under the MIT License.
Content is licensed under CC BY-NC-SA 4.0.
