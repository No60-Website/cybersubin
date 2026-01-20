# CyberSubin Open Lab

Evolving Culture Heritage through Technology

An interactive web experience exploring CyberSubin through multiple temporal perspectives: The Past, The Present, and The Future. Built with cutting-edge web technologies including Svelte, Three.js, and GSAP animations.

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Development](#development)
- [Building for Production](#building-for-production)
- [Project Status](#project-status)

## Features

- **Multi-language Support** - English and Thai language support with dynamic switching
- **Responsive Design** - Fully responsive interface that works on all device sizes
- **3D Visualization** - Interactive Three.js 3D character page with keyframe sliders
- **Rich Animations** - Smooth GSAP animations including parallax effects and transitions
- **Interactive Components** - Image carousels, dialogs, and dynamic content sections
- **Accessible UI** - Modern Svelte components with proper semantic HTML

## Tech Stack

- **Framework**: [SvelteKit 2](https://kit.svelte.dev/) - Full-stack Svelte framework
- **Language**: [TypeScript](https://www.typescriptlang.org/) - Type-safe JavaScript
- **Styling**: [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- **Animation**: [GSAP 3](https://greensock.com/gsap/) - Professional animation library
- **3D Graphics**: [Three.js](https://threejs.org/) - WebGL 3D library
- **3D in Svelte**: [Svelte Cubed](https://svelte-cubed.vercel.app/) - Three.js integration for Svelte
- **Build Tool**: [Vite 5](https://vitejs.dev/) - Next-generation build tool
- **i18n**: [svelte-i18n](https://github.com/kaisermann/svelte-i18n) - Internationalization
- **Utilities**: 
  - GSAP for animations
  - Simple Parallax JS for parallax effects
  - Saos for intersection observer support

## Project Structure

```
src/
├── routes/              # SvelteKit routes
│   ├── +page.svelte    # Home page
│   ├── +layout.svelte  # Root layout
│   ├── lab/            # Lab page
│   └── three/          # 3D visualization page
├── lib/
│   ├── Components/     # Reusable Svelte components
│   │   ├── Card.svelte
│   │   ├── Carousel.svelte
│   │   ├── Dialog.svelte
│   │   └── ...
│   ├── sections/       # Page section components
│   │   ├── Hero.svelte
│   │   ├── About.svelte
│   │   ├── Past.svelte
│   │   ├── Present.svelte
│   │   ├── Future.svelte
│   │   └── SixElements.svelte
│   ├── text/           # i18n language files
│   │   ├── en.json
│   │   └── th.json
│   ├── 59.ts           # 59 elements data
│   ├── elements.ts     # Element definitions
│   ├── i18n.js         # i18n configuration
│   ├── store.js        # Svelte stores
│   └── index.ts        # Library exports
├── app.css             # Global styles
└── app.html            # HTML template

static/                 # Static assets
├── 6-elements/
├── hero/
├── intro/
├── code/
├── diagram/
├── fonts/
└── ...
```

## Getting Started

### Prerequisites

- Node.js 18+ and pnpm installed

### Installation

1. Clone or navigate to the project directory
2. Install dependencies:

```bash
pnpm install
```

## Development

Start the development server:

```bash
pnpm dev
```

The application will be available at `http://localhost:5173/`

### Other Development Commands

- **Type Check**: `pnpm check` - Run Svelte type checking
- **Type Check (Watch)**: `pnpm check:watch` - Continuous type checking
- **Lint**: `pnpm lint` - Check code style with Prettier and ESLint
- **Format**: `pnpm format` - Auto-format code

## Building for Production

Build the project for production:

```bash
pnpm build
```

Preview the production build:

```bash
pnpm preview
```

The project is configured to deploy on Cloudflare Pages using the `@sveltejs/adapter-cloudflare` adapter.

## Project Status

### Completed Features

#### Overall + Introduction
- [x] Responsive design
- [x] Hero character with parallax effect
- [x] Sidebar highlighting
- [x] Image assets
- [x] Multi-language support (i18n)

#### The Past
- [x] Image gallery
- [x] Carousel functionality
- [x] 59 elements generation
- [x] 3D character page
- [x] 3D model loading state
- [x] 3D keyframe slider

#### The Present
- [x] Image gallery
- [x] Six elements 59x integration
- [x] Merge animation
- [x] Diagram lines
- [x] Six elements dialog

#### The Future
- [x] Image gallery
- [x] CyberSubin user control interface

## TODO List

### Overall + Introduction

- [x] Responsiveness
- [x] Hero Character + Parallel Effect
- [x] Sidebar Highlight
- [x] Add Images
- [x] i18n

### The Past

- [x] Add Images
- [x] Carousel Functionality
- [x] Fix generate 59
- [x] 3D character page
- [x] Loading State for 3d Model
- [x] 3d keyframe slider

### The Present

- [x] Add Images
- [x] 59x Six Elements Image
- [x] Merge Animation
- [x] DIagram Line
- [x] Six Element dialog

### The Future

- [x] Add Images
- [x] Revamp CyberSubin User Control
