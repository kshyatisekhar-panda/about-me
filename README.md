# about-me — Personal Portfolio

A personal portfolio website built with **Astro** and **TypeScript**, developed collaboratively with **Claude (AI)** as an experiment in AI-assisted development.

## Why This Project?

I wanted to build a portfolio that represents who I am — a full stack developer, cricket player, traveler, and sports enthusiast based in Stockholm. But beyond the end result, the process mattered just as much.

### AI-Assisted Development with Claude

This entire project was built in collaboration with [Claude](https://claude.ai/) (Anthropic's AI assistant) using **Claude Code**. The goal was to explore:

- **How AI pair-programming actually works** in practice — prompting, iterating, reviewing suggestions, and steering decisions
- **Whether AI tools can accelerate learning** a new framework from scratch
- **The balance between AI-generated code and developer intent** — Claude writes the code, but the vision, design choices, and direction are mine

This wasn't about generating a template and calling it done. It was a back-and-forth conversation — adjusting layouts, debating whether the design was "too much", fixing emoji rendering quirks, and iterating until it felt right.

### Why Astro?

Coming from a React background, I deliberately chose **not** to use React for this project. I wanted to learn something new, and Astro stood out for several reasons:

- **Zero JS by default** — Astro ships pure HTML/CSS unless you explicitly opt into client-side JavaScript. For a portfolio site, this means blazing fast performance out of the box
- **Component-based without the overhead** — `.astro` files feel familiar (HTML + JS frontmatter) but without the virtual DOM, hydration costs, or bundle bloat
- **TypeScript first-class** — strict mode from day one, no extra config
- **Island architecture** — if I need interactivity later (say, a photo gallery lightbox), I can add React/Svelte/Vue components only where needed without rewriting the whole site
- **Built for content sites** — portfolios, blogs, docs — exactly what Astro is optimized for

In short: Astro let me build a fast, modern site while learning a fundamentally different approach to web development than what I'm used to with React/Next.js.

## Tech Stack

| Layer       | Technology                        |
| :---------- | :-------------------------------- |
| Framework   | Astro v6                          |
| Language    | TypeScript (strict mode)          |
| Styling     | Vanilla CSS (custom properties)   |
| Fonts       | Inter + Space Grotesk (Google)    |
| Deployment  | Static build (deploy anywhere)    |
| Dev Tool    | Claude Code (AI pair-programming) |

## Project Structure

```
src/
  layouts/
    BaseLayout.astro         # HTML shell, fonts, meta, scroll animations
  components/
    Navbar.astro             # Fixed nav with mobile hamburger menu
    Hero.astro               # Video background hero section
    About.astro              # Bio + highlight stats
    Skills.astro             # Tech skills in categorized cards
    Projects.astro           # Featured GitHub projects
    BeyondCode.astro         # Cricket, sports, travel, content creation
    Contact.astro            # Email, LinkedIn, GitHub, YouTube, Instagram
    TravelGallery.astro      # Photo gallery (ready, hidden until photos added)
    Footer.astro             # Footer
  styles/
    global.css               # Full design system — dark theme, responsive
  pages/
    index.astro              # Main page composing all components
public/
  hero-bg.mp4               # Hero background video
  favicon.svg               # KP favicon
```

## Getting Started

```bash
# Install dependencies
npm install

# Start dev server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## What I Learned

- Astro's mental model is refreshingly simple — it's closer to writing HTML than building a React app
- AI pair-programming works best when you stay in the driver's seat — give clear direction, review everything, and don't just accept the first suggestion
- Choosing an unfamiliar framework forces you to think about *why* you reach for certain tools, not just *how* to use them
- A portfolio should evolve — this is a starting point, not a finished product

## License

MIT

---

Built with [Astro](https://astro.build) + [Claude Code](https://claude.ai/code)
