# GitHub Pages Deployment Troubleshooting

## Workflow Status
Check the Actions tab in your GitHub repository to see the workflow status.

## Common Issues and Solutions

### 1. Workflow Not Running
**Symptoms**: No workflow runs appear in Actions tab

**Solutions**:
- Ensure you've pushed to `main` or `claude/check-status-c7g27` branch
- Check that the YAML file is valid (check for indentation errors)
- Go to Settings → Actions → General → Allow all actions and workflows

### 2. Build Fails with "No files found"
**Symptoms**: Upload artifact step fails

**Solutions**:
- Check that `yasuda_toshiki_uiux.html` exists in the repo
- Verify all HTML and CSS files are committed
- Ensure `.github/workflows/deploy-pages.yml` is properly formatted

### 3. Pages Not Accessible
**Symptoms**: Deployed URL returns 404

**Solutions**:
1. Go to Settings → Pages
2. Verify "GitHub Actions" is selected as Source
3. Wait 1-2 minutes for deployment to complete
4. Check URL format: `https://username.github.io/repo-name/yasuda_toshiki_uiux.html`

### 4. Workflow Gets Stuck
**Symptoms**: Workflow appears to hang

**Solutions**:
- GitHub Actions can take 1-5 minutes to complete
- Check the "Deployments" tab to see progress
- Try the "workflow_dispatch" button to manually trigger

## Manual Trigger

If the workflow doesn't run automatically, you can manually trigger it:

1. Go to "Actions" tab in your repository
2. Select "Deploy to GitHub Pages" workflow
3. Click "Run workflow"
4. Select the branch and click "Run workflow"

## Verification Steps

After successful deployment:

1. ✅ Workflow shows "All jobs completed successfully"
2. ✅ Deployments tab shows a successful deployment
3. ✅ Pages Settings shows deployment URL
4. ✅ Can access the HTML file at the generated URL

## File Checklist

Required files for deployment:
- [ ] `yasuda_toshiki_uiux.html` - Main HTML file
- [ ] `.github/workflows/deploy-pages.yml` - Workflow definition
- [ ] `.nojekyll` - Disables Jekyll processing
- [ ] `_config.yml` - GitHub Pages configuration
- [ ] `README.md` - Repository documentation

## Debug Information

If issues persist, provide:
- Workflow run logs (Actions tab)
- Build output errors
- Repository Settings → Pages status
- Branch information (main vs feature branch)

---

For more help: https://docs.github.com/en/pages
