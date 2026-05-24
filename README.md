# ☁️ Cloud Cafe

A modern, elegant coffee shop website built with **Svelte**, **SvelteKit**, and **TailwindCSS**. Featuring smooth animations, responsive design, and a beautiful hand-drawn aesthetic.

![Cloud Cafe Preview](src/lib/assets/img/cloudcafe.svg)

## ✨ Features

- **Hero Section** - Full-screen landing with smooth scroll-to-menu functionality
- **Interactive Menu** - Complete food and drinks menu with categorized items (Main Course, Dessert, Coffee, Non-Coffee)
- **Story Section** - About us page with company journey timeline
- **Contact Section** - Contact form with business information
- **Responsive Navbar** - Sticky navigation with mobile hamburger menu
- **Background Pattern** - Decorative food icons using Lucide icons
- **Smooth Animations** - Motion library powered transitions and reveal effects

## 🛠️ Tech Stack

- **Framework**: [SvelteKit](https://kit.svelte.dev/) v2
- **Styling**: [TailwindCSS](https://tailwindcss.com/) v4
- **Icons**: [Lucide Svelte](https://lucide.dev/)
- **Animations**: [Motion](https://motion.dev/)
- **Language**: TypeScript
- **Build Tool**: Vite v7

## 📁 Project Structure

```
src/
├── lib/
│   ├── assets/
│   │   └── img/
│   │       └── cloudcafe.svg          # Logo
│   └── components/
│       ├── layouts/
│       │   ├── navbar.svelte          # Navigation bar
│       │   └── footer.svelte          # Footer
│       ├── ui/
│       │   └── background.svelte      # Decorative background pattern
│       ├── HeroSection.svelte         # Hero/landing section
│       ├── Menu.svelte                # Menu wrapper
│       ├── MainMenu.svelte            # Menu items data & display
│       ├── Story.svelte               # About us section
│       └── ContactSection.svelte      # Contact form & info
└── routes/
    ├── +layout.svelte                 # Root layout
    ├── +page.svelte                   # Main page
    └── layout.css                     # Global styles & CSS variables
```

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ 
- npm or pnpm

### Installation

1. Clone the repository:
```bash
git clone https://github.com/your-username/cloudcoffee.git
cd cloudcoffee
```

2. Install dependencies:
```bash
npm install
```

3. Run the development server:
```bash
npm run dev
```

4. Open [http://localhost:5173](http://localhost:5173) in your browser.

### Build for Production

```bash
npm run build
npm run preview
```

## 🎨 Customization

### Colors

Edit the CSS variables in `src/routes/layout.css`:

```css
:root {
  --bg: #FDFBF7;        /* Background color */
  --primary: #00e5ff;
  --secondary: #cfd8dc;
  --text: #b0bec5;
}
```

### Menu Items

Edit menu data in `src/lib/components/MainMenu.svelte`:

```typescript
let mainCourses: MenuItem[] = [
  {
    name: 'Chicken Sandwich',
    price: 43,
    description: 'Your description here...'
  },
  // Add more items
];
```

## 📱 Responsive Design

The website is fully responsive with breakpoints:
- **Mobile**: < 768px (hamburger menu, stacked layouts)
- **Tablet**: 768px - 1024px
- **Desktop**: > 1024px (full navigation, grid layouts)

## 📄 License

© 2024 sushi cibaduyut. All rights reserved.

---
