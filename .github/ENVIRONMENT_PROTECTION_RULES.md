# GitHub Pages Environment Protection Rules

## 🔴 Current Error
```
Branch "claude/check-status-c7g27" is not allowed to deploy to
github-pages due to environment protection rules.
```

## ✅ Solution

GitHub Pages has an environment called `github-pages` with protection rules that limit which branches can deploy. You need to update these rules.

### Step-by-Step Fix

#### Option 1: Allow All Branches (Development)

1. Go to **GitHub Repository Settings**
2. Navigate to **Environments** (in the left sidebar)
3. Click on **github-pages** environment
4. Under "Deployment branches", select **All branches**
5. Click **Save protection rules**

**Screenshot path**: Settings → Environments → github-pages → "Deployment branches"

---

#### Option 2: Allow Specific Branches (Recommended for Production)

If you want to restrict deployments to specific branches:

1. Go to **Settings → Environments → github-pages**
2. Under "Deployment branches", select **Selected branches**
3. Add the branches you want to allow:
   - `main`
   - `claude/check-status-c7g27`
   - (or any other branch)
4. Click **Save protection rules**

---

#### Option 3: Remove Environment Requirement (For Static Sites)

If you don't need the github-pages environment protection:

1. Go to **Settings → Environments → github-pages**
2. Click the **Delete environment** button
3. The workflow will still deploy without the environment check

---

## 📋 What Each Option Does

| Option | Use Case | Security |
|--------|----------|----------|
| **All Branches** | Development, testing | Low - any branch can deploy |
| **Selected Branches** | Mixed workflows | Medium - approved branches only |
| **No Environment** | Simple static sites | Varies - no extra restrictions |

---

## 🔍 Current Workflow Configuration

The workflow is set up to:
- ✅ Build on: `main` and `claude/check-status-c7g27`
- ✅ Deploy to: `github-pages` environment
- ✅ Requires: Branch approval from environment rules

---

## 🚀 After Fixing Environment Rules

1. Go back to **Actions** tab
2. Find the failed **Deploy to GitHub Pages** run
3. Click **Re-run all jobs** button
4. Deployment should now succeed

---

## 📊 Detailed Steps with Screenshots

### Finding the Environments Section

```
GitHub Repository → Settings (gear icon)
↓
Look for "Environments" in the left sidebar
↓
Click "Environments"
↓
You'll see "github-pages" listed
↓
Click "github-pages" to edit
```

### Editing Deployment Branch Rules

```
In the github-pages environment page:
↓
Look for "Deployment branches"
↓
Select "All branches" (for development)
   OR
Select "Selected branches" and add your branches
↓
Click "Save protection rules" button
```

---

## ✅ Verification Checklist

After updating environment rules:

- [ ] Navigated to Settings → Environments
- [ ] Found and clicked "github-pages"
- [ ] Changed "Deployment branches" setting
- [ ] Clicked "Save protection rules"
- [ ] Went back to Actions tab
- [ ] Re-ran the failed workflow
- [ ] Checked for green checkmark in workflow

---

## 🐛 Troubleshooting

### "Still Getting Error After Changing Rules?"

1. Wait 1-2 minutes for GitHub to apply the changes
2. **Re-run all jobs** button in Actions tab
3. Hard refresh your browser (Ctrl+Shift+R or Cmd+Shift+R)
4. Check that you're editing the correct environment

### "Can't Find Environments Section?"

- Make sure you're on **Settings** (not repository home)
- Look in left sidebar for **Environments**
- If missing, it may have been deleted - create a new one

### "See Multiple Environments?"

- Only edit the **github-pages** environment
- Other environments (if any) won't affect GitHub Pages deployment

---

## 🎯 Recommended Configuration for This Project

Since this is a development project with both `main` and feature branches:

**Option**: Select "All branches"
- Allows any branch to deploy
- Useful for testing and development
- Can always change later for production

---

## 📞 Need Help?

- [GitHub Environments Documentation](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- Check the Actions tab logs for detailed error messages

---

**Last Updated**: January 14, 2026
