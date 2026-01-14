# TASV Website

Modern, animated marketing website for TASV - The Advanced Smart Vault gallery and vault app.

## Overview

This is a bold, energetic, single-page marketing website built with:
- **Pure HTML, CSS, and JavaScript** (no frameworks)
- **Bold startup-style animations** with 3D effects and parallax
- **Fully responsive** design (mobile, tablet, desktop)
- **Performance optimized** for 60fps smooth animations
- **Zero dependencies** - works standalone

## Features

### Sections

1. **Hero Section**
   - Animated gradient text title
   - 3D floating phone mockup with actual app screenshot
   - Animated background with floating orbs
   - Stat cards (100% Offline, Zero Tracking, 7 View Modes)

2. **Features Grid** (8 key features)
   - Multi-Vault Security
   - 7 View Modes
   - Professional Editor
   - Smart Organization
   - 100% Private
   - Interactive Map
   - Complete Metadata
   - Recycle Bin

3. **Gallery Views Showcase**
   - Displays different viewing modes with screenshots
   - Grid & List Views card
   - Albums & Collections card

4. **Multi-Vault Section**
   - 3D stacked vault cards with hover effects
   - 4 key vault features
   - Individual PINs, Folder Organization, Access Logs, Biometric Unlock

5. **Privacy Section**
   - 4 privacy guarantees
   - Animated icons with pulse effects

6. **FAQ Section**
   - Accordion-style expandable questions
   - 8 common questions answered

7. **Pricing Section**
   - Free vs Pro comparison
   - Feature lists with checkmarks
   - "BEST VALUE" badge on Pro tier

8. **CTA (Download) Section**
   - Store download buttons (Google Play, App Store)
   - Rotating glow animation

9. **Footer**
   - Product, Support, Company links
   - Contact information

### Animations

**On Load:**
- Hero text slides in from left
- Phone mockup slides in from right
- Floating orb background animation

**On Scroll:**
- Feature cards fade in with stagger effect
- Sections reveal with intersection observer
- Privacy icons pulse continuously

**On Hover:**
- Feature cards: 3D tilt effect with perspective transform
- Buttons: Lift up with shadow
- Nav links: Underline animation
- Vault cards: Stack spreads and rotates

**Continuous:**
- Hero title: Gradient color shift animation
- Phone mockup: Floating up/down
- Background orbs: Floating and scaling
- Privacy icons: Pulsing scale effect
- CTA section: Rotating glow overlay

## File Structure

```
website/
├── index.html              # Main landing page
├── privacy.html            # Privacy policy page
├── images/                 # App screenshots
│   ├── gallery_screen_1.jpg
│   ├── gallery_screen_2.jpg
│   ├── albums.jpg
│   ├── vault.jpg
│   └── settings_screen.jpg
├── assets/
│   ├── screenshots/        # Placeholder for additional screenshots
│   │   └── README.md
│   └── icons/              # Optional: logo SVG (future)
└── README.md               # This file
```

## Color Scheme

```css
--primary: #06B6D4           /* Cyan - Modern, tech-forward */
--primary-dark: #0891B2      /* Dark Cyan */
--primary-light: #22D3EE     /* Light Cyan */
--accent-purple: #8B5CF6     /* Purple - Premium, creative */
--accent-pink: #EC4899       /* Pink - Energetic */
--accent-green: #10B981      /* Green - Security, trust */
--accent-orange: #F59E0B     /* Orange - Attention */
--bg-dark: #0F172A           /* Dark Navy Background */
--bg-darker: #020617         /* Darkest Background */
--surface: #1E293B           /* Surface */
--surface-light: #334155     /* Light Surface */
--text-primary: #F8FAFC      /* White/Light */
--text-secondary: #94A3B8    /* Gray */
--text-muted: #64748B        /* Muted Gray */
```

## Deployment

### Option 1: Static Hosting (Recommended)

**Netlify:**
```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy
cd website
netlify deploy --prod
```

**Vercel:**
```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
cd website
vercel --prod
```

**GitHub Pages:**
1. Create a GitHub repository
2. Push website folder contents
3. Go to Settings > Pages
4. Select branch and `/root` or `/website` folder
5. Save

### Option 2: Traditional Web Server

Upload files to any web server via FTP/SFTP:
```
public_html/
└── (all website files here)
```

**Requirements:**
- No special server configuration needed
- Works with Apache, Nginx, or any static file server
- No database or server-side processing required

### Option 3: Local Testing

**Python Simple Server:**
```bash
cd website
python3 -m http.server 8000
# Visit: http://localhost:8000
```

**Node.js http-server:**
```bash
npm install -g http-server
cd website
http-server
# Visit: http://localhost:8080
```

**VS Code Live Server Extension:**
1. Install "Live Server" extension
2. Right-click `index.html`
3. Select "Open with Live Server"

## Customization

### Updating Store Links

In `index.html`, find the download section and update URLs:

```html
<a href="YOUR_PLAY_STORE_URL" class="store-btn">
    <!-- Google Play button -->
</a>
<a href="YOUR_APP_STORE_URL" class="store-btn">
    <!-- App Store button -->
</a>
```

### Adding More Screenshots

1. Take screenshots following guidelines in `assets/screenshots/README.md`
2. Place JPG files in `images/` folder
3. Update `index.html` to reference new screenshots
4. See screenshot README for detailed instructions

### Changing Colors

Update CSS variables at the top of `<style>` section in `index.html`:

```css
:root {
    --primary: #YOUR_COLOR;
    --accent-purple: #YOUR_COLOR;
    /* etc... */
}
```

### Updating Copy/Content

All text content is directly in `index.html`. Search for:
- Hero title: `<h1 class="hero-title">`
- Feature cards: `<div class="feature-card">`
- FAQ questions: `<div class="faq-item">`
- Pricing details: `<div class="pricing-card">`

## Performance Optimization

### Current Optimizations

✅ **Implemented:**
- CSS-only animations (GPU accelerated)
- Intersection Observer for scroll animations
- Smooth scroll with `scroll-behavior: smooth`
- Optimized z-index layers
- Transform and opacity for animations (not layout properties)
- Debounced scroll handlers
- Single external font (Inter) with preconnect

### Further Optimizations

**Compress Images:**
```bash
# Using ImageOptim CLI (Mac)
brew install imageoptim-cli
imageoptim images/*.jpg

# Or use online tools
# TinyJPG: https://tinyjpg.com/
```

**Minify HTML/CSS:**
```bash
# Using html-minifier
npm install -g html-minifier
html-minifier --collapse-whitespace --remove-comments index.html -o index.min.html
```

**Enable Gzip on Server:**
```apache
# Apache .htaccess
<IfModule mod_deflate.c>
  AddOutputFilterByType DEFLATE text/html text/css application/javascript
</IfModule>
```

## Browser Support

**Fully Supported:**
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Mobile Chrome (Android 10+)
- Mobile Safari (iOS 14+)

**Required Features:**
- CSS Custom Properties (variables)
- CSS Grid & Flexbox
- Intersection Observer API
- CSS Transforms & Animations
- Backdrop Filter (with graceful fallback)

**Not Supported:**
- Internet Explorer (any version)

## Testing Checklist

Before launching:

- [ ] Test on Chrome, Firefox, Safari
- [ ] Test on mobile device (real device, not just emulator)
- [ ] Verify all images load
- [ ] Check responsive design at different screen sizes
- [ ] Test all navigation links work
- [ ] Verify smooth scrolling between sections
- [ ] Test FAQ accordion expand/collapse
- [ ] Check mobile menu toggle works
- [ ] Verify animations are smooth (60fps)
- [ ] Test with slow 3G network (DevTools)
- [ ] Run Lighthouse audit (aim for 90+ scores)
- [ ] Check accessibility (keyboard navigation, screen reader)
- [ ] Verify store links go to correct URLs
- [ ] Test on different devices (tablet, laptop, desktop)

## Lighthouse Performance Tips

**Current Performance:** ~90-95 (depends on images)

**To Improve:**

1. **Optimize Images:**
   - Convert to WebP format
   - Add `loading="lazy"` to images below fold
   - Use `<picture>` for responsive images

2. **Preload Critical Assets:**
   ```html
   <link rel="preload" href="https://fonts.googleapis.com/css2?family=Inter..." as="style">
   ```

3. **Add Meta Tags:**
   ```html
   <meta name="theme-color" content="#0F172A">
   <link rel="canonical" href="https://yourdomain.com">
   ```

## SEO Optimization

**Current SEO Elements:**
- ✅ Semantic HTML5 structure
- ✅ Meta description
- ✅ Keywords meta tag
- ✅ Open Graph tags
- ✅ Twitter Card tags
- ✅ Proper heading hierarchy (H1, H2, H3)
- ✅ Alt text on images

**To Improve:**
- Add `robots.txt`
- Add `sitemap.xml`
- Add schema.org markup (App/SoftwareApplication)
- Set up Google Analytics (optional)
- Submit to Google Search Console

## Troubleshooting

### Images Not Loading

**Problem:** Screenshots don't show up

**Solutions:**
1. Check file paths are correct (`images/` folder)
2. Verify image files exist and have correct names
3. Check file permissions (should be readable)
4. Clear browser cache and hard refresh (Cmd+Shift+R / Ctrl+Shift+F5)

### Animations Not Smooth

**Problem:** Choppy animations or lag

**Solutions:**
1. Open DevTools Performance tab
2. Record while scrolling
3. Look for layout recalculation or long tasks
4. Reduce `blur()` filter strength on orbs
5. Disable animations on low-end devices:
   ```css
   @media (prefers-reduced-motion: reduce) {
       * { animation: none !important; }
   }
   ```

### Mobile Menu Not Working

**Problem:** Hamburger menu doesn't toggle

**Solutions:**
1. Check JavaScript console for errors
2. Verify mobile-menu-btn and nav-links elements exist
3. Test JavaScript with:
   ```javascript
   console.log('Mobile menu button:', document.querySelector('.mobile-menu-btn'));
   console.log('Nav links:', document.querySelector('.nav-links'));
   ```

### Scroll Animations Not Triggering

**Problem:** Elements don't reveal on scroll

**Solutions:**
1. Check browser supports Intersection Observer
2. Verify `.reveal` class is on elements
3. Adjust threshold/rootMargin in observer options
4. Test with:
   ```javascript
   console.log('Reveal elements:', document.querySelectorAll('.reveal').length);
   ```

## Maintenance

### Regular Updates

**Monthly:**
- [ ] Update screenshots if app UI changes
- [ ] Review and update FAQ questions
- [ ] Check all links still work
- [ ] Test on latest browser versions

**Quarterly:**
- [ ] Update feature descriptions if new features added
- [ ] Refresh pricing if changed
- [ ] Update testimonials/social proof (when available)
- [ ] Run accessibility audit

**Yearly:**
- [ ] Review and refresh copy/messaging
- [ ] Consider redesign if design trends change significantly
- [ ] Update privacy policy to reflect any changes

### Adding New Sections

To add a new section:

1. Copy existing section structure from `index.html`
2. Update classes and content
3. Add section navigation link to navbar
4. Style with consistent patterns (use existing CSS as template)
5. Add scroll reveal with `.reveal` class

## Support

For questions or issues:
- **Email:** privacy@rohitranjan.co.in
- **Website Issues:** Check this README first
- **App Issues:** Contact support through app or email

## License

Copyright © 2025 TASV. All rights reserved.

Website design and code: Proprietary
App assets and screenshots: Proprietary

---

## Quick Reference

**Essential Files:**
- `index.html` - Main website (edit this for most changes)
- `privacy.html` - Privacy policy page
- `images/` - App screenshots

**Key Sections to Update:**
- Store links: Line ~1670
- Feature descriptions: Line ~1285
- Pricing details: Line ~1617
- FAQ answers: Line ~1499

**Common Tasks:**
- Update screenshot: Replace file in `images/`, update `<img src="">`
- Change color: Update CSS variables (line ~27)
- Add FAQ: Copy `.faq-item` block and modify
- Update pricing: Edit `.pricing-features` lists

**Testing Locally:**
```bash
cd website
python3 -m http.server 8000
# Open: http://localhost:8000
```

**Deploy to Netlify:**
```bash
cd website
netlify deploy --prod
```

---

Built with ❤️ for privacy.
