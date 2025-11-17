# GitHub Pages Deployment Guide

This guide will help you deploy the JSON Editor to GitHub Pages.

## 📋 Prerequisites

- A GitHub account
- Git installed on your computer
- This jsoneditor directory

## 🚀 Deployment Steps

### Option 1: Deploy as Subdirectory

**Best if you have other content in your repository**

1. **Push to GitHub**
   ```bash
   cd /path/to/your/website-MR901.CO.IN
   git add jsoneditor/
   git commit -m "Add JSON Editor tool"
   git push origin main
   ```

2. **Enable GitHub Pages**
   - Go to your repository on GitHub
   - Click **Settings** → **Pages**
   - Under **Source**, select:
     - Branch: `main`
     - Folder: `/` (root)
   - Click **Save**

3. **Access Your Editor**
   - URL: `https://yourusername.github.io/repository-name/jsoneditor/`
   - Wait 1-2 minutes for deployment

### Option 2: Deploy to Repository Root

**Best for a standalone JSON Editor site**

1. **Create New Repository**
   ```bash
   # On GitHub, create a new repository called 'json-editor'
   
   # Clone it locally
   git clone https://github.com/yourusername/json-editor.git
   cd json-editor
   ```

2. **Copy Files**
   ```bash
   # Copy all files from jsoneditor/ to the root
   cp -r /path/to/jsoneditor/* .
   ```

3. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Initial commit: JSON Editor"
   git push origin main
   ```

4. **Enable GitHub Pages**
   - Repository **Settings** → **Pages**
   - Source: `main` branch, `/` (root)
   - Save

5. **Access Your Editor**
   - URL: `https://yourusername.github.io/json-editor/`

### Option 3: Custom Domain

**Use your own domain name**

1. **Deploy using Option 1 or 2**

2. **Add CNAME file**
   ```bash
   echo "yourdomain.com" > CNAME
   git add CNAME
   git commit -m "Add custom domain"
   git push
   ```

3. **Configure DNS**
   Add these records to your domain DNS:
   ```
   Type: CNAME
   Name: www (or @)
   Value: yourusername.github.io
   ```

4. **Enable in GitHub**
   - Settings → Pages → Custom domain
   - Enter your domain
   - Check "Enforce HTTPS"

## ✅ Verification

After deployment, test these features:

- [ ] Page loads correctly with styling
- [ ] JSON Editor displays
- [ ] Load JSON file works
- [ ] Save JSON file works
- [ ] Format/Compact buttons work
- [ ] Repair JSON works
- [ ] Mode switching (tree/code/text) works
- [ ] Color picker appears on hex values
- [ ] Search functionality works (Ctrl+F)

## 🐛 Troubleshooting

### Issue: 404 Page Not Found

**Solution:**
- Wait 2-3 minutes for GitHub to build your site
- Check the correct URL (include `/jsoneditor/` if subdirectory)
- Verify GitHub Pages is enabled in Settings

### Issue: Styling Not Loading

**Solution:**
- Check that `dist/` folder is committed
- Verify paths in index.html are relative (not absolute)
- Check browser console for 404 errors

### Issue: Features Not Working

**Solution:**
- Ensure all files in `dist/` are present
- Check browser console for JavaScript errors
- Verify FileSaver.js CDN is accessible

### Issue: Icons Missing

**Solution:**
- Ensure `dist/img/jsoneditor-icons.svg` exists
- Check CSS file loaded correctly
- Clear browser cache

## 📱 Mobile Testing

Test on mobile devices:
1. Open the deployed URL on your phone
2. Verify responsive design works
3. Test touch interactions in tree mode
4. Verify buttons are clickable

## 🔒 Security Notes

- This tool runs entirely in the browser
- No data is sent to any server
- Files are loaded/saved locally only
- Safe to use with sensitive JSON data

## 📊 Analytics (Optional)

Add Google Analytics to track usage:

1. **Get tracking ID** from Google Analytics

2. **Add to index.html** before `</head>`:
   ```html
   <!-- Google Analytics -->
   <script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
   <script>
     window.dataLayer = window.dataLayer || [];
     function gtag(){dataLayer.push(arguments);}
     gtag('js', new Date());
     gtag('config', 'GA_MEASUREMENT_ID');
   </script>
   ```

## 🔄 Updates

To update the editor:

1. Edit `index.html` locally
2. Test changes: `python3 -m http.server 8888`
3. Commit and push:
   ```bash
   git add index.html
   git commit -m "Update JSON Editor"
   git push
   ```
4. GitHub Pages will auto-rebuild (1-2 minutes)

## 📞 Support

- **GitHub Pages Issues**: [GitHub Docs](https://docs.github.com/pages)
- **JSON Editor Issues**: Check console errors
- **Custom Questions**: Contact via MR901.CO.IN

---

Happy Deploying! 🎉

