# about-me

My personal portfolio website built with Astro and TypeScript.

## Why This Project?

I wanted a portfolio that shows who I am. Not just as a developer, but as someone who plays cricket, travels, and loves sports. I'm based in Stockholm and have been writing code for over 7 years now.

But this project was also an experiment. I built the entire thing using Claude Code (Anthropic's AI assistant) as a pair programmer. I wanted to see how it feels to work with AI on a real project, not just ask it to generate boilerplate.

## Working with Claude

The whole site came out of a conversation. I'd describe what I wanted, Claude would write the code, and then I'd review it, push back on things, and ask for changes. It was genuinely collaborative.

Some examples of how this played out: I told Claude the design felt "too much" and we stripped it back together. Emojis were rendering as raw unicode and we debugged that. I gave it my LinkedIn page source and it extracted my career history from the React SSR data.

It's not magic. You still need to know what you want and be willing to steer. But it's a surprisingly effective way to learn a new framework while building something real.

## Why Astro?

I've been using React for years. I didn't want to reach for it again. I wanted to learn something new by actually building with it, not just reading docs.

Astro made sense because it ships zero JavaScript by default. For a portfolio, that means the site is fast without any effort. The component model feels familiar if you come from React, but there's no virtual DOM or hydration overhead. TypeScript works out of the box in strict mode. And if I ever need interactivity (like a photo gallery lightbox), I can drop in React or Svelte components just for those parts without touching the rest.

It's a different mental model from what I'm used to with Next.js, and that was the whole point.

## Tech Stack

| Layer       | Technology                        |
| :---------- | :-------------------------------- |
| Framework   | Astro v6                          |
| Language    | TypeScript (strict mode)          |
| Styling     | Vanilla CSS (custom properties)   |
| Fonts       | Inter + Space Grotesk (Google)    |
| Deployment  | Static build (deploy anywhere)    |
| Dev Tool    | Claude Code (AI pair programming) |

## Project Structure

```
src/
  layouts/
    BaseLayout.astro         Main HTML shell with fonts, meta tags, and scripts
  components/
    Navbar.astro             Fixed nav with mobile hamburger menu
    Hero.astro               Video background hero section
    About.astro              Bio and highlight stats
    Experience.astro         Career timeline with roles and education
    Skills.astro             Tech skills in categorized cards
    Projects.astro           Featured GitHub projects
    BeyondCode.astro         Cricket, sports, travel, content creation
    TravelGallery.astro      Photo gallery with travel photography
    Contact.astro            Email, LinkedIn, GitHub, YouTube, Instagram
    Footer.astro             Footer
  styles/
    global.css               Design system with dark theme and responsive layout
  pages/
    index.astro              Main page that brings all components together
public/
  hero-bg.mp4               Hero background video
  travel/                    Optimized travel photos
  favicon.svg               KP favicon
```

## Getting Started

```bash
npm install
npm run dev
npm run build
npm run preview
```

## What I Learned

Astro feels refreshingly simple. It's closer to writing HTML than building a React app, and that simplicity is a feature, not a limitation.

AI pair programming works best when you stay in the driver's seat. Give clear direction, review everything, and don't just accept the first suggestion. The best results came from pushing back and iterating.

Choosing an unfamiliar framework forces you to think about why you reach for certain tools, not just how to use them.

This portfolio is a starting point. It will keep evolving.

## License

MIT

---

[kshyatisekhar-panda.vercel.app](https://kshyatisekhar-panda.vercel.app)

Built with [Astro](https://astro.build) and [Claude Code](https://claude.ai/code)
