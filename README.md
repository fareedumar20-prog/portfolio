# Umar Fareed — Personal Portfolio

Premium personal portfolio website built with Next.js 15, TypeScript, Tailwind CSS, and Framer Motion. Design inspired by Apple × Linear × Stripe aesthetics.

## ✨ Features

- **Apple × Linear × Stripe** design language
- Glassmorphism navbar with blur + transparency
- Cursor-reactive gradient mesh background
- Smooth scroll animations (Framer Motion)
- Loading screen with animated progress bar
- Hero with live stats, animated badge, scroll indicator
- About with interest cards and floating info badge
- Skills with animated progress bars
- Projects with 6 detailed project cards
- GitHub contribution graph (visual)
- Certifications with status badges (Earned / In Progress / Planned)
- Contact form with validation + social links
- Back-to-top button
- Custom 404 page
- SEO + Open Graph metadata
- Fully responsive (320px → 1920px)
- Dark theme
- Static export ready (GitHub Pages + Vercel)

## 🛠 Tech Stack

- **Framework:** Next.js 15 (App Router)
- **Language:** TypeScript
- **Styling:** Tailwind CSS + custom CSS variables
- **Animations:** Framer Motion
- **Fonts:** Syne (display) + Inter (body) + JetBrains Mono (code)
- **Icons:** Inline SVG (zero dependencies)

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- npm or yarn

### Installation

```bash
# Clone or unzip the project
cd umar-portfolio

# Install dependencies
npm install

# Start development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000)

### Build for Production

```bash
npm run build
```

Output is in the `out/` directory (static HTML/CSS/JS).

## 🌐 Deployment

### Vercel (Recommended — 1 click)

1. Push this folder to a GitHub repository
2. Go to [vercel.com](https://vercel.com) → New Project
3. Import your GitHub repo
4. Vercel auto-detects Next.js — click **Deploy**
5. Done! Live at `your-name.vercel.app`

### GitHub Pages

1. Push to GitHub repo named `umarfareed21.github.io` (or any repo)
2. In `next.config.ts`, add if using a sub-path:
   ```ts
   basePath: '/repo-name',
   ```
3. Run `npm run build` — this generates the `out/` folder
4. In GitHub repo settings → Pages → Source: **GitHub Actions**
5. Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages
on:
  push:
    branches: [main]
jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 20 }
      - run: npm install
      - run: npm run build
      - uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./out
```

## 🎨 Customization

### Update Personal Info

- **Email:** `app/sections/Contact.tsx` → `socials` array
- **LinkedIn/GitHub:** Same file — update `href` values
- **GitHub username:** `app/sections/GitHub.tsx`
- **Projects:** `app/sections/Projects.tsx` → `projects` array
- **Skills:** `app/sections/Skills.tsx` → `skills` array
- **Certifications:** `app/sections/Certifications.tsx` → `certs` array

### Colors & Theme

All design tokens are in `app/globals.css` under `:root`. Change `--accent-indigo` and `--accent-violet` to rebrand the entire site.

## 📁 Project Structure

```
umar-portfolio/
├── app/
│   ├── components/
│   │   ├── Navbar.tsx         # Sticky glassmorphism nav
│   │   ├── LoadingScreen.tsx  # Animated loading screen
│   │   ├── BackToTop.tsx      # Back-to-top button
│   │   └── GradientBackground.tsx  # Cursor-reactive orbs
│   ├── sections/
│   │   ├── Hero.tsx
│   │   ├── About.tsx
│   │   ├── Skills.tsx
│   │   ├── Projects.tsx
│   │   ├── GitHub.tsx
│   │   ├── Certifications.tsx
│   │   └── Contact.tsx
│   ├── globals.css            # Design system & CSS variables
│   ├── layout.tsx             # Root layout + SEO metadata
│   ├── page.tsx               # Main page assembly
│   └── not-found.tsx          # Custom 404 page
├── public/
├── next.config.ts
├── tailwind.config.ts
└── package.json
```
