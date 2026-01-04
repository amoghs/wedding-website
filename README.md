# Amogh & Helene's Wedding Website

A beautiful, personalized wedding invitation website with watercolor aesthetics and organic vibes.

## Features

- Watercolor-inspired design with organic shapes and gentle animations
- Personalized invitations with guest names
- Three different invitation types (all events, 2 events, or 1 event)
- Responsive mobile-first design
- Photo gallery with scroll animations
- Direct WhatsApp RSVP integration

## Setup Instructions

### 1. Add Your Photos

Add 8-10 photos to the `photos/` directory with the following names:
- `01.jpg`
- `02.jpg`
- `03.jpg`
- etc.

The website will automatically load and display them in the gallery section.

**Recommended photo specs:**
- Aspect ratio: 4:5 (portrait orientation works best)
- Resolution: At least 800x1000px
- Format: JPG
- File size: Under 500KB each for faster loading

### 2. Update WhatsApp Number

In `index.html`, find this line (around line 579):

```html
<a href="https://wa.me/YOUR_PHONE_NUMBER?text=Hi%20Amogh%20and%20Helene!%20" class="whatsapp-button" id="whatsappButton">
```

Replace `YOUR_PHONE_NUMBER` with your WhatsApp number in international format (no + or spaces):
- Example: For +61 412 345 678, use: `61412345678`

### 3. Customize Invitation Links

Create three different invitation links for different guest groups:

**VIP - All 3 events (Haldi + Western + Indian):**
```
vip?name=Guest%20Name
```

**Friends - 2 events (Western + Indian only):**
```
friends?name=Guest%20Name
```

**Wedding - 1 event (Indian ceremony only):**
```
wedding?name=Guest%20Name
```

Replace `Guest%20Name` with the actual guest's name (use `%20` for spaces).

**Examples:**
- `vip?name=Sarah%20and%20John`
- `friends?name=The%20Smiths`
- `wedding?name=Priya`

**Note:** If someone accesses the base URL without a specific invitation path, they'll see a message asking them to use their personalized link.

## Deployment Options

### Option 1: Netlify (Recommended - Free & Easy)

1. Create a free account at [netlify.com](https://www.netlify.com)
2. Drag and drop your `wedding-website` folder into Netlify
3. Your site will be live at `your-site-name.netlify.app`
4. Optional: Connect a custom domain (like `amoghhelene.com`)

### Option 2: GitHub Pages (Free)

1. Create a GitHub repository
2. Push your code to the repository
3. Go to Settings > Pages
4. Select your main branch and save
5. Your site will be live at `username.github.io/repository-name`

### Option 3: Vercel (Free)

1. Create account at [vercel.com](https://vercel.com)
2. Import your GitHub repository or upload files
3. Deploy with one click
4. Your site will be live at `your-site.vercel.app`

## Testing Locally

To test the website on your computer, you'll need to run a local web server (paths won't work with file:// protocol):

**Option 1 - Python:**
```bash
python3 -m http.server 8000
```
Then visit:
- `http://localhost:8000/vip?name=Test`
- `http://localhost:8000/friends?name=Test`
- `http://localhost:8000/wedding?name=Test`

**Option 2 - Node.js:**
```bash
npx serve
```
Then visit the URLs shown in terminal with `/vip`, `/friends`, or `/wedding` paths.

## Customization

### Colors

The color palette can be customized in the `:root` CSS variables at the top of `index.html`:

```css
:root {
    --sage: #8B9D83;      /* Sage green (plants) */
    --ocean: #5B8A9D;     /* Ocean blue (surfing) */
    --coral: #E8926F;     /* Coral accent */
    --terracotta: #C97557; /* Terracotta */
    --cream: #FAF7F2;     /* Background cream */
    --sand: #E8DFD3;      /* Sand color */
    --deep-teal: #3D6B7D; /* Deep teal */
    --text-dark: #2C3E3F; /* Dark text */
    --text-light: #6B7F7E; /* Light text */
}
```

### Typography

The site uses two beautiful fonts from Google Fonts:
- **Cormorant Garamond** - Elegant serif for headings
- **Montserrat** - Clean sans-serif for body text

### Event Details

Event information is defined in the JavaScript section (around line 742). You can update dates, times, or locations there if needed.

## Structure

```
wedding-website/
├── index.html          # Main website file
├── photos/            # Your wedding photos (add 01.jpg, 02.jpg, etc.)
│   └── .gitkeep
└── README.md          # This file
```

## Browser Support

Works on all modern browsers:
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers

## Tips

1. **Send personalized links**: Each guest gets a unique URL with their name
2. **Test on mobile**: Most guests will view on phones, so test there first
3. **Optimize photos**: Compress images to keep the site fast
4. **Share early**: Give guests time to see the invite and RSVP

## Support

If you need to make changes or have questions, the website is a single HTML file with inline CSS and JavaScript, making it easy to edit in any text editor.

Enjoy your wedding! 🎉
