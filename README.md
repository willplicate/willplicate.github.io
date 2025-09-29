# Wedding RSVP Website

Wedding invitation and RSVP website for Will & Jucas - Barcelona 2026

## Setup Instructions

### 1. Add Your Photos

You need to add the following photos to this directory:

- `couple-photo.png` - Photo of you and Jucas for the main page
- `pizza1.jpg` through `pizza9.jpg` - Nine pizza photos for the thank you page

### 2. Run the Database Migration

Run the SQL migration in Supabase:
```bash
# Navigate to personal-crm directory
cd ../personal-crm

# Run this SQL in your Supabase SQL Editor
cat create-wedding-guests-table.sql
```

Or manually execute the contents of `create-wedding-guests-table.sql` in your Supabase dashboard.

### 3. Deploy to GitHub Pages

1. Create a new GitHub repository for the wedding website
2. Push this directory to the repository:

```bash
cd wedding-rsvp
git init
git add .
git commit -m "Initial wedding website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/wedding-rsvp.git
git push -u origin main
```

3. Enable GitHub Pages:
   - Go to repository Settings > Pages
   - Source: Deploy from branch
   - Branch: main / (root)
   - Save

4. Configure custom domain (allyouneedisalightjacket.com):
   - In GitHub Pages settings, add custom domain: `allyouneedisalightjacket.com`
   - In your domain registrar (where you bought the domain), add DNS records:
     - Type: CNAME
     - Name: www
     - Value: YOUR-USERNAME.github.io
     - Type: A (add 4 records for apex domain)
     - Name: @
     - Values:
       - 185.199.108.153
       - 185.199.109.153
       - 185.199.110.153
       - 185.199.111.153

### 4. Test Locally

You can test the website locally by opening `index.html` in a browser, or use a simple HTTP server:

```bash
# Python 3
python3 -m http.server 8000

# Then visit http://localhost:8000
```

## Files

- `index.html` - Main RSVP page
- `thankyou.html` - Thank you page after RSVP submission
- `styles.css` - Stylesheet matching your design
- `script.js` - Form handling and Supabase integration

## Font

Uses "Sorts Mill Goudy" from Google Fonts, loaded automatically.