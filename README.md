# LUSIVE Frontend

Frontend website files for LUSIVE receipt service.

## Files

- `index.html` - Main homepage
- `form.html` - Payment/checkout form
- `config.js` - Backend API configuration

## Setup

1. Update `config.js` with your backend API URL:
```javascript
window.BACKEND_API_URL = 'https://your-backend-url.com';
```

Or add this script tag in your HTML files before other scripts:
```html
<script>
    window.BACKEND_API_URL = 'https://your-backend-url.com';
</script>
```

2. If you don't set `BACKEND_API_URL`, it will automatically use:
   - `http://localhost:3000` for local development
   - Empty string (relative URLs) for production if hosted on same domain

## Deployment

### Recommended Hosting Options:

1. **Netlify** (Easiest for static sites)
   - Go to https://netlify.com
   - Drag and drop the `frontend` folder
   - Or connect GitHub repo and set publish directory to `frontend`
   - Add custom domain (optional)

2. **Vercel**
   - Go to https://vercel.com
   - Import your repository
   - Set root directory to `frontend`
   - Deploy!

3. **GitHub Pages**
   - Push code to GitHub
   - Go to Settings → Pages
   - Select source branch and `/frontend` folder
   - Your site will be at `username.github.io/repo-name`

4. **Cloudflare Pages**
   - Go to https://pages.cloudflare.com
   - Connect repository
   - Set build directory to `frontend`
   - Deploy!

5. **Traditional Web Hosting** (cPanel, etc.)
   - Upload all files from `frontend` folder to `public_html` or `www`
   - Make sure `index.html` is in the root
   - Update `config.js` with your backend URL

## Configuration

Before deploying, make sure to:

1. **Update Backend URL** in `config.js` or add script tag in HTML:
   ```html
   <script>
       window.BACKEND_API_URL = 'https://your-backend-api-url.com';
   </script>
   ```

2. **Update Stripe Publishable Key** in `form.html` (line ~1258):
   ```javascript
   const stripePublishableKey = 'pk_live_your_key_here';
   ```

3. **Test locally**:
   - Open `index.html` in browser
   - Make sure backend is running on `http://localhost:3000`
   - Test the payment flow

## Important Notes

- The frontend needs to communicate with your backend API
- Make sure CORS is configured on your backend to allow your frontend domain
- For production, use HTTPS for both frontend and backend
- Never expose your Stripe secret key in frontend code (only publishable key)

