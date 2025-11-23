# Quick Deployment Guide

## Option 1: Deploy to Vercel (Recommended)

### Step 1: Push to GitHub

```bash
git init
git add .
git commit -m "Initial documentation"
git branch -M main
git remote add origin https://github.com/yourusername/your-repo.git
git push -u origin main
```

### Step 2: Deploy to Vercel

1. Go to [vercel.com](https://vercel.com) and sign in
2. Click "New Project"
3. Import your GitHub repository
4. Vercel will auto-detect the configuration
5. Click "Deploy"

That's it! Your docs will be live in ~2 minutes.

### Step 3: Custom Domain (Optional)

1. In Vercel project settings, go to "Domains"
2. Add your domain (e.g., `docs.yourdomain.com`)
3. Update your DNS settings as shown
4. Wait for DNS propagation (~5-30 minutes)

---

## Option 2: Use Mintlify Hosting

### Step 1: Sign up at Mintlify

1. Go to [mintlify.com](https://mintlify.com)
2. Sign up with GitHub
3. Click "New Documentation"

### Step 2: Connect Repository

1. Select your GitHub repository
2. Mintlify will auto-deploy on every push
3. Get a `yourproject.mintlify.app` subdomain

### Step 3: Configure (Optional)

- Add custom domain in Mintlify settings
- Configure analytics
- Set up team permissions

---

## Option 3: Manual Deployment

### Local Build

```bash
# Install Mintlify globally
npm install -g mintlify

# Build the docs
mintlify build
```

### Deploy Build Output

The built files will be in `.mintlify/` directory. You can deploy this to:

- **Netlify**: Drag and drop `.mintlify` folder
- **Cloudflare Pages**: Connect to repository, set build dir to `.mintlify`
- **AWS S3**: Upload `.mintlify` contents to S3 bucket
- **Any static host**: Upload the `.mintlify` directory

---

## Testing Before Deployment

```bash
# Install Mintlify
npm install -g mintlify

# Run development server
mintlify dev

# Visit http://localhost:3000
```

---

## Environment Variables (if needed)

If your docs need environment variables:

### Vercel
1. Go to Project Settings > Environment Variables
2. Add your variables
3. Redeploy

### Mintlify
1. Go to Settings > Environment Variables
2. Add your variables

---

## Troubleshooting

### Build Fails
- Check `mint.json` for syntax errors
- Ensure all referenced files exist
- Verify all links are valid

### Pages Not Showing
- Check navigation in `mint.json`
- Ensure file names match exactly
- Files must be `.mdx` extension

### Styling Issues
- Clear cache: `rm -rf .mintlify`
- Rebuild: `mintlify build`
- Check for conflicting CSS

---

## Post-Deployment Checklist

- [ ] Verify all pages load correctly
- [ ] Test all internal links
- [ ] Check API examples work
- [ ] Test on mobile devices
- [ ] Set up custom domain (if applicable)
- [ ] Add to README of main project
- [ ] Share with team

---

## Updating Documentation

### On Vercel or Mintlify
Just push to your GitHub repository:

```bash
git add .
git commit -m "Update docs"
git push
```

Automatic deployment will trigger.

### Manual Updates
```bash
mintlify build
# Upload .mintlify/ to your host
```

---

## Support

- Mintlify Docs: https://mintlify.com/docs
- Mintlify Community: https://mintlify.com/community
- Vercel Support: https://vercel.com/support