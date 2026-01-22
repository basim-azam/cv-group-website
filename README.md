# Computer Vision Group - University of Melbourne

Academic website for the Computer Vision Group at The University of Melbourne, led by Dr. Naveed Akhtar.

**Live Site**: [https://unimelb-cv-group.github.io/](https://unimelb-cv-group.github.io/) (after deployment)

## Features

- Clean, academic-style design inspired by Stanford NLP and Oxford VGG research group websites
- University of Melbourne brand colors and styling
- Fully responsive (mobile-first design)
- Easy content management via Markdown and YAML files
- Automatic deployment to GitHub Pages
- Publication filtering and search
- Team member profiles with research interests

## Tech Stack

- **Static Site Generator**: [Hugo](https://gohugo.io/)
- **Hosting**: GitHub Pages
- **Styling**: Custom CSS with CSS Variables
- **Fonts**: Inter, JetBrains Mono (Google Fonts)
- **Icons**: Font Awesome 6

## Quick Start

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (v0.128.0 or later)
- Git

### Local Development

```bash
# Clone the repository
git clone https://github.com/YOUR-USERNAME/cv-group-website.git
cd cv-group-website

# Start development server
hugo server -D

# Build for production
hugo --minify
```

The site will be available at `http://localhost:1313/`

## Project Structure

```
cv-group-website/
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions deployment
├── content/
│   ├── _index.md               # Homepage
│   ├── about.md                # About page
│   ├── contact.md              # Contact page
│   ├── join.md                 # Join Us page
│   ├── news/                   # News posts
│   │   ├── _index.md
│   │   └── YYYY-MM-DD-title.md
│   ├── people/
│   │   └── _index.md           # People page (uses data/people.yaml)
│   ├── publications/
│   │   └── _index.md           # Publications page (uses data/publications.yaml)
│   └── research/
│       ├── _index.md           # Research overview
│       └── areas/              # Individual research area pages
├── data/
│   ├── people.yaml             # Team member data
│   ├── publications.yaml       # Publication data
│   └── research_themes.yaml    # Research area data
├── layouts/
│   ├── _default/               # Default templates
│   ├── partials/               # Reusable template parts
│   ├── news/                   # News-specific templates
│   ├── people/                 # People page template
│   ├── publications/           # Publications page template
│   ├── research/               # Research page templates
│   └── index.html              # Homepage template
├── static/
│   ├── css/
│   │   └── main.css            # Main stylesheet
│   ├── js/
│   │   └── main.js             # JavaScript
│   └── images/
│       ├── people/             # Team member photos
│       └── research/           # Research area images
├── config.yaml                 # Hugo configuration
└── README.md
```

## Content Management Guide

### Adding News

1. Create a new file in `content/news/` with naming convention: `YYYY-MM-DD-slug.md`

2. Add frontmatter and content:

```markdown
---
title: "Your News Title"
date: 2025-01-15
tags: ["Publications", "Awards"]  # Options: Publications, Awards, Team, Service, Events
---

Your news content here in Markdown format.
```

3. Commit and push to main branch

### Adding/Updating Publications

Edit `data/publications.yaml`:

```yaml
- title: "Paper Title"
  authors:
    - "Author One"
    - "Naveed Akhtar"  # Will be bold in display
    - "Author Three"
  venue: "CVPR"
  venue_full: "IEEE/CVF Conference on Computer Vision and Pattern Recognition"
  year: 2025
  type: "conference"  # or "journal"
  paper_url: "https://arxiv.org/abs/..."
  code_url: "https://github.com/..."  # optional
  project_url: ""  # optional
  bibtex: |
    @inproceedings{...}
```

### Adding Team Members

Edit `data/people.yaml`:

#### For PhD Students:
```yaml
phd_students:
  - name: "Student Name"
    degree: "PhD Student"
    year: "Year 1"
    email: "email@student.unimelb.edu.au"
    photo: "/images/people/student-name.jpg"
    bio: "Brief bio describing research focus."
    research_interests:
      - "Area 1"
      - "Area 2"
    website: "https://personal-website.com"  # or "#" if none
    google_scholar: "https://scholar.google.com/..."  # or "#" if none
```

#### For Masters Students:
```yaml
masters_students:
  - name: "Student Name"
    degree: "Masters Student"
    year: "Year 1"
    # ... same structure as PhD students
```

#### For Alumni:
```yaml
alumni:
  - name: "Former Student Name"
    degree: "PhD"
    graduation_year: 2024
    thesis_title: "Thesis Title"
    current_position: "Researcher at Company"
    photo: "/images/people/alumni-name.jpg"
```

### Adding Research Areas

1. Add entry to `data/research_themes.yaml`:

```yaml
- id: "new-area"
  name: "New Research Area"
  icon: "icon-name"  # Font Awesome icon name
  short_description: "Brief description for cards"
  description: |
    Full description in Markdown format.
  key_topics:
    - "Topic 1"
    - "Topic 2"
  featured_publications:
    - "Publication title 1"
  image: "/images/research/new-area.jpg"
```

2. Create content page `content/research/areas/new-area.md`:

```markdown
---
title: "New Research Area"
description: "SEO description"
theme_id: "new-area"
---

Additional content here (optional).
```

### Updating Site Statistics

Edit `config.yaml`:

```yaml
params:
  stats:
    publications: "150+"
    citations: "10,693+"
    team_members: "15+"
    research_areas: "6"
```

## Adding Images

### Team Member Photos
- **Location**: `static/images/people/`
- **Format**: JPG or PNG
- **Size**: 400x400px (square)
- **Naming**: `firstname-lastname.jpg`

### Research Area Images
- **Location**: `static/images/research/`
- **Format**: JPG or PNG
- **Size**: 800x600px

### University Logo
- Replace `static/images/unimelb-logo.svg` with official logo from [UniMelb Brand Hub](https://brand.unimelb.edu.au/)

## Deployment

### Automatic Deployment (GitHub Actions)

The site automatically deploys to GitHub Pages when you push to the `main` branch.

### Setup for New Repository

1. Push code to GitHub repository
2. Go to repository Settings → Pages
3. Under "Build and deployment", select "GitHub Actions"
4. Push a commit to trigger the first deployment

### Custom Domain Setup

1. Add your custom domain in repository Settings → Pages → Custom domain
2. Create a `CNAME` file in the `static/` folder with your domain
3. Configure DNS:

**For apex domain (example.com):**
```
A     @     185.199.108.153
A     @     185.199.109.153
A     @     185.199.110.153
A     @     185.199.111.153
```

**For subdomain (www.example.com or cv.example.com):**
```
CNAME  www   YOUR-USERNAME.github.io.
```

4. Enable "Enforce HTTPS" in GitHub Pages settings

## Customization

### Colors

Edit CSS variables in `static/css/main.css`:

```css
:root {
  --primary-blue: #003366;      /* UniMelb Blue */
  --light-blue: #0055A4;        /* Accent */
  --dark-blue: #001A33;         /* Headings */
  /* ... */
}
```

### Typography

The site uses Google Fonts (Inter, JetBrains Mono). To change fonts:

1. Update the Google Fonts link in `layouts/partials/head.html`
2. Update font variables in `static/css/main.css`

### Site Configuration

Edit `config.yaml` to change:
- Site title and description
- Navigation menu
- Contact information
- Social links
- Site statistics

## Troubleshooting

### Hugo Server Not Starting
- Ensure you have Hugo Extended (not standard Hugo)
- Check for syntax errors in YAML files
- Run `hugo --verbose` for detailed error messages

### Styles Not Updating
- Clear browser cache
- Run `hugo --gc` to clean generated files

### Images Not Showing
- Check file paths are correct (must start with `/`)
- Ensure images are in `static/` folder
- Check file extensions match exactly

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This website template is available for academic use. Please maintain attribution to the original authors.

## Contact

For questions about the website, contact the group administrator.

For research inquiries, contact Dr. Naveed Akhtar at naveed.akhtar1@unimelb.edu.au
