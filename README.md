# Computer Vision Group - University of Melbourne

Academic website for the Computer Vision Group at The University of Melbourne, led by Dr. Naveed Akhtar.

**Live Site**: [https://basim-azam.github.io/cv-group-website/](https://basim-azam.github.io/cv-group-website/)

## Features

- Clean, minimal academic design inspired by Oxford VGG research group
- University of Melbourne brand colors (#003366)
- Fully responsive with Bootstrap 5
- Simple static HTML - no build tools required
- Automatic deployment to GitHub Pages

## Tech Stack

- **Framework**: Bootstrap 5
- **Hosting**: GitHub Pages
- **Icons**: Font Awesome 6
- **Fonts**: System fonts (native stack)

## Project Structure

```
cv-group-website/
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions deployment
├── css/
│   └── style.css               # Custom styles with UniMelb branding
├── images/
│   ├── people/                 # Team member photos
│   │   └── default-avatar.svg  # Placeholder avatar
│   └── unimelb-logo.png        # University logo
├── index.html                  # Homepage
├── people.html                 # Team page
├── research.html               # Research areas
├── publications.html           # Publications list
├── news.html                   # News and updates
├── contact.html                # Contact and join us
└── README.md
```

## Local Development

Simply open any HTML file in a web browser, or use a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js (if http-server is installed)
npx http-server
```

Then visit `http://localhost:8000`

## Content Updates

### Updating Team Members

Edit `people.html` directly. Each student card follows this structure:

```html
<div class="student-card">
  <div class="student-photo">
    <img src="images/people/student-name.jpg" alt="Student Name">
  </div>
  <h4>Student Name</h4>
  <p class="student-degree">PhD Student &middot; Since 2024</p>
  <p class="student-thesis">Thesis Title</p>
  <div class="student-interests">
    <span class="interest-tag">Research Area 1</span>
    <span class="interest-tag">Research Area 2</span>
  </div>
  <div class="student-links">
    <a href="mailto:email@student.unimelb.edu.au"><i class="fas fa-envelope"></i></a>
  </div>
</div>
```

### Adding Publications

Edit `publications.html`. Each publication follows this structure:

```html
<div class="publication-entry">
  <span class="pub-title">Paper Title</span>
  <span class="pub-type conference">CVPR</span>
  <span class="pub-authors">Author List</span>
  <span class="pub-venue">Venue Full Name, Year</span>
  <div class="pub-links">
    <a href="paper-url"><i class="fas fa-file-pdf"></i> Paper</a>
  </div>
</div>
```

### Adding News

Edit `news.html`. Each news entry follows:

```html
<div class="news-entry">
  <span class="news-date">Month Year</span>
  <h3>News Title</h3>
  <p>News content...</p>
</div>
```

### Adding Photos

1. Add photos to `images/people/` directory
2. Recommended size: 200x200px (square)
3. Supported formats: JPG, PNG
4. Name files: `firstname-lastname.jpg`

## Deployment

### Automatic (GitHub Actions)

Push to `main` branch and the site automatically deploys.

### Manual Setup

1. Create GitHub repository
2. Push code to the repository
3. Go to Settings → Pages
4. Under "Build and deployment", select "GitHub Actions"
5. The workflow will run automatically

## Customization

### Colors

Edit CSS variables in `css/style.css`:

```css
:root {
  --unimelb-blue: #003366;
  --unimelb-blue-light: #0055A4;
  --unimelb-blue-dark: #001A33;
  /* ... */
}
```

### Logo

Replace `images/unimelb-logo.png` with your logo file.

## Contact

For website questions, contact the group administrator.

For research inquiries, contact Dr. Naveed Akhtar at naveed.akhtar1@unimelb.edu.au
