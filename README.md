# Jackson & Mackenzie Wedding Website

A modern, responsive wedding website for Jackson and Mackenzie's wedding on June 13, 2026.

## 🌿 Features

- **Single Page Application** - All content on one scrollable page
- **Responsive Design** - Mobile-first approach with beautiful layouts on all devices
- **Countdown Timer** - Real-time countdown to the wedding day
- **RSVP Integration** - Embedded Google Form for guest responses
- **Interactive FAQ** - Expandable accordion for common questions
- **Photo Gallery** - Lazy-loaded image grid
- **Bridal Party** - Cards for wedding party members

## 🎨 Design

- **Color Palette**: Sage green, white, and charcoal
- **Typography**: Cormorant Garamond (headings) + Inter (body)
- **Style**: Modern, minimalist, elegant

## 🚀 Tech Stack

- [Astro](https://astro.build) - Static site generator
- [Tailwind CSS v4](https://tailwindcss.com) - Styling
- [Lucide Icons](https://lucide.dev) - Icon library
- [GitHub Pages](https://pages.github.com) - Hosting

## 📁 Project Structure

```
├── src/
│   ├── components/     # Astro components
│   ├── data/           # JSON data files
│   ├── layouts/        # Page layouts
│   ├── pages/          # Page routes
│   └── styles/         # Global CSS
├── public/
│   └── images/         # Static images
├── docs/specs/         # Specification documents
└── .github/workflows/  # CI/CD deployment
```

## 🧞 Commands

| Command           | Action                                 |
| :---------------- | :------------------------------------- |
| `npm install`     | Install dependencies                   |
| `npm run dev`     | Start dev server at `localhost:4321`   |
| `npm run build`   | Build production site to `./dist/`     |
| `npm run preview` | Preview build locally before deploying |

## 📝 Customization

### Update Content

- **Bridal Party**: Edit `src/data/bridalParty.json`
- **FAQ**: Edit `src/data/faq.json`
- **RSVP Form**: Update URL in `src/components/RSVP.astro`
- **Contact Email**: Update in `src/components/Contact.astro`

### Add Photos

1. Add images to `public/images/gallery/` (photo-1.jpg through photo-6.jpg)
2. Add bridal party photos to `public/images/bridal-party/`

## 🚀 Deployment

The site automatically deploys to GitHub Pages when pushing to the `main` branch.

**Live URL**: `https://[username].github.io/jackson-and-mackenzie-website/`

## 📄 License

Made with ❤️ for Jackson & Mackenzie's wedding.
