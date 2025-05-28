# Deployment Guide

Complete guide for deploying the Mullen Consulting Services website.

## 🚀 Quick Deployment Checklist

- [ ] Domain purchased and configured
- [ ] Hosting account set up
- [ ] Files uploaded to hosting
- [ ] Email forwarding configured
- [ ] SSL certificate enabled
- [ ] Website tested and live

## 📋 Detailed Deployment Steps

### Step 1: Domain & Hosting Purchase

**Recommended: Namecheap (Domain + Hosting)**
1. Go to [namecheap.com](https://namecheap.com)
2. Search for your domain: `yourdomain.com`
3. Add Stellar hosting plan to cart
4. Complete purchase (~$28/year total)

**What you'll receive:**
- Domain registration confirmation
- Hosting account details
- cPanel login credentials
- Nameserver information

### Step 2: File Upload Process

**Method 1: cPanel File Manager (Easiest)**
1. Log into cPanel (link provided in hosting email)
2. Click "File Manager"
3. Navigate to `public` folder
4. Delete any default files (index.html, coming_soon.html)
5. Upload your files:
   - `index.html` (main website)
   - `assets/.png` (logo)
6. Extract if uploaded as ZIP file

**Method 2: FTP Upload (Advanced)**
```bash
# Using FileZilla or similar FTP client
Host: ftp.yourdomain.com
Username: [provided by hosting]
Password: [provided by hosting]
Port: 21

# Upload to: /public_html/
```

### Step 3: Domain Configuration

**DNS Propagation:**
- Changes take 24-48 hours to fully propagate
- You can check status at: whatsmydns.net
- Your website will be accessible once propagation completes

### Step 4: Email Setup

**Create Business Email Addresses:**
1. In cPanel → "Email Accounts"
2. Create accounts:
   - `zzz@yourdomain.com`
   - `yyy@yourdomain.com`
   - `xxx@yourdomain.com` (optional)

**Set Up Gmail Forwarding:**
1. In cPanel → "Forwarders"
2. Create forwarders:
   - `xxx@yourdomain.com` → `your-gmail@gmail.com`
   - `yyy@yourdomain.com` → `your-gmail@gmail.com`

**Configure Gmail to Send As:**
1. Gmail Settings → "Accounts and Import"
2. "Send mail as" → "Add another email address"
3. Add: `zzz@yourdomain.com`
4. Use hosting SMTP settings for authentication

### Step 5: SSL Certificate Setup

**Enable SSL (Free with most hosts):**
1. cPanel → "SSL/TLS"
2. Enable "Force HTTPS Redirect"
3. Install free Let's Encrypt certificate
4. Wait 2-4 hours for activation

**Verify SSL:**
- Visit: `https://yourdomain.com`
- Check for green padlock in browser
- Test at: ssllabs.com/ssltest

### Step 6: Testing & Verification

**Pre-Launch Testing:**
- [ ] Website loads properly
- [ ] All navigation links work
- [ ] Contact form submits successfully
- [ ] Email forwarding works
- [ ] Mobile responsiveness verified
- [ ] SSL certificate active

**Performance Testing:**
- Speed test: gtmetrix.com
- Mobile test: Google Mobile-Friendly Test
- SEO check: Basic on-page optimization

## 🔧 Ongoing Maintenance

### Regular Updates
```bash
# Local development workflow
git pull origin main        # Get latest changes
# Make your edits to index.html
git add .
git commit -m "Updated contact info"
git push origin main

# Then upload to hosting via cPanel File Manager
```

### Monthly Checklist
- [ ] Check website loading speed
- [ ] Verify contact form functionality
- [ ] Review and update content as needed
- [ ] Check SSL certificate status
- [ ] Backup website files
- [ ] Monitor email deliverability

### Quarterly Reviews
- [ ] Update service descriptions
- [ ] Refresh testimonials/statistics
- [ ] Review and update pricing
- [ ] Check for broken links
- [ ] Update copyright year if needed

## 🆘 Troubleshooting

### Common Issues

**Website Not Loading:**
- Check DNS propagation status
- Verify files uploaded to correct directory (`public`)
- Confirm domain pointing to correct nameservers

**Email Not Working:**
- Verify email accounts created in cPanel
- Check forwarder configuration
- Test with different email providers
- Confirm SMTP settings if using "Send As"

**SSL Certificate Issues:**
- Wait 24-48 hours after enabling
- Clear browser cache
- Check hosting provider SSL status
- Contact support if persistent issues

**Contact Form Not Working:**
- Form currently uses JavaScript alert (demo only)
- For production, add server-side processing
- Consider using Formspree or Netlify Forms
- Test form submission regularly

## 📞 Support Resources

**Hosting Support:**
- Namecheap: 24/7 live chat
- Documentation: namecheap.com/support
- Video tutorials available

**Domain Issues:**
- Check domain registration status
- Verify payment and renewal dates
- Update nameservers if changing hosts

**Technical Support:**
- GitHub Issues for code problems
- Hosting provider for server issues
- Domain registrar for DNS problems

---

## 🎯 Performance Optimization (Future)

### Speed Improvements
- Image optimization and compression
- CSS/JS minification
- CDN implementation
- Caching setup

### SEO Enhancements
- Meta descriptions and titles
- Schema markup for business
- Google Business Profile setup
- Local SEO optimization

### Analytics Setup
- Google Analytics installation
- Google Search Console setup
- Conversion tracking
- Performance monitoring