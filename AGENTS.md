You are onboarding GitCMS for repository attajak/attajak.web.app.

Use create-gitcms to generate `.gitcms` configuration for each real content site in this repo.
Inspect the repo first, then prefer the CLI over hand-writing config.

Preferred commands from repo root:
- Interactive: npm init gitcms@latest
- Agentic: npx create-gitcms@latest --yes [--mode ...] [--site-root ...] [--website-url ...] [--dry-run] [--force]

Flag guidance:
- Prefer auto detection first.
- Use --mode single or --mode monorepo only when the repo structure is clear and you want to lock it in.
- Use repeatable --site-root only to override or narrow monorepo site detection.
- website_url is required for every site. One URL applies to all sites; <siteRoot>=<url> maps per site.
- Use --dry-run to verify detected output paths before writing.
- Use --force only when overwriting existing .gitcms files is intended.

Ask the user only if:
- .gitcms configuration already exists and overwrite is not explicitly requested
- multiple site-root choices are plausible and inspection cannot resolve them safely
- website_url is unclear or cannot be inferred safely

After running the CLI, report the created or updated `.gitcms` paths and any warnings.
