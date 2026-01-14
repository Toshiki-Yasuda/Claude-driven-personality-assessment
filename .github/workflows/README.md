# GitHub Actions Workflows

## deploy-pages.yml
Automatically deploys the repository to GitHub Pages, making HTML files accessible via a public URL.

### What it does:
- Triggers on push to `main` or `claude/check-status-c7g27` branches
- Uploads all files as GitHub Pages artifact
- Deploys to GitHub Pages
- Provides a public URL to view the HTML

### View the deployed page:
After the action completes, visit: `https://Toshiki-Yasuda.github.io/Claude-driven-personality-assessment/yasuda_toshiki_uiux.html`

### GitHub Pages Setup:
1. Go to Repository Settings → Pages
2. Select "GitHub Actions" as the source
3. The workflow will automatically build and deploy on push
