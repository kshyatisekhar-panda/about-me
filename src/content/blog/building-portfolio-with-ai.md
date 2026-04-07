---
title: "Building My Portfolio with AI as a Pair Programmer"
description: "I built my entire portfolio site using Claude Code as a pair programmer. Here's what actually happened, what surprised me, and what I'd do differently."
date: "2026-04-07"
tags: ["ai", "claude", "astro", "developer-experience"]
draft: false
---

I've been a full stack developer for over 7 years. I've built dashboards, APIs, real-time apps, and enterprise software. But I'd never built a proper portfolio site for myself. It was always on the list, never at the top.

What changed was Claude Code. I wanted to try AI-assisted development on a real project, not a toy example. And I wanted to learn Astro at the same time. So I opened a terminal and started a conversation.

This post is about what that experience was actually like.

## The Setup

I started with an empty directory and a vague idea. I knew I wanted a dark-themed portfolio that showed my work, my career history, my cricket stats, and some travel photography. I didn't have a design in mind. I didn't have a Figma file. I just had a list of things I wanted on the page.

I told Claude what I was looking for and it scaffolded an Astro project with TypeScript in strict mode. Within minutes I had a full project structure with components for each section: Hero, About, Skills, Projects, Beyond Code, Contact, and a Footer.

That first version was fast. Maybe too fast.

## The First Version Was Too Much

The initial design had a lot going on. The hero section had a video background with a blur filter, a grain texture overlay, an accent gradient, and a dark overlay on top of all that. Every section had hover animations. There were four cards in a row that felt cramped on most screens.

I looked at it and told Claude it felt like too much. That one comment changed the direction of the whole project. Claude agreed and suggested stripping the hero down to just video plus a dark overlay, changing the Beyond Code section to a 2x2 grid, and hiding the empty travel gallery until I had actual photos.

This was the moment I realized what AI pair programming is really about. It's not about generating code. It's about having a conversation where you steer the direction and the AI handles the execution.

## Debugging Emoji Rendering

One of the more unexpected bugs was emoji rendering. I wanted emojis for the Beyond Code section. Cricket bat, football, airplane, video camera. Claude used unicode escape sequences like `\uD83C\uDFCF` in the Astro template.

They rendered as literal text. Instead of a cricket bat emoji, the page showed the string `\uD83C\uDFCF`.

The issue was that Astro's HTML template doesn't evaluate unicode escapes the way JavaScript string literals do. The fix was simple: use actual emoji characters instead of escape sequences. But diagnosing it required understanding how Astro processes templates differently from JavaScript.

## Extracting My LinkedIn Data

I wanted my real career history on the site, not placeholder text. But LinkedIn blocks automated access. Every fetch attempt returned HTTP 999.

So I saved the page source from my browser and gave it to Claude. The file was 1.3MB, two lines of heavily escaped React SSR data. Not exactly readable.

Claude searched through the data using pattern matching. It found my job titles, company names, and education buried inside nested React component trees. Things like `"children":["Senior Analyst Programmer at Gateway Group of Companies"]` hidden among thousands of lines of tracking data and UI component definitions.

From that mess it extracted my complete career timeline: six roles at Gateway Group from Project Trainee to Senior Analyst, plus my internships at DRDO and Birla Tyre, and my B.Tech from Centurion University. All real, all accurate.

That was genuinely impressive. I wouldn't have had the patience to parse that file manually.

## Adding Travel Photography

I dropped some photos into the project directory. A shot of Trollstigen in Norway, two Northern Lights photos from Kiruna and Abisko, a Stockholm sunset, kayaks by the Norwegian fjords, and a winter campfire scene.

One of the photos was a `.dng` file (a RAW camera format). Claude converted it to JPEG using sharp-cli, then resized and optimized all six images from 21MB down to about 650KB total. It set up a gallery grid with hover overlays showing the location of each photo.

When I told Claude the Northern Lights photos were from Kiruna and Abisko (not just "Scandinavia"), it updated the captions immediately. Small detail, but it matters. These are my photos and my memories. Getting the locations right matters.

## Theme Toggle

I mentioned wanting both dark and light themes. Claude added CSS custom properties for a light theme, a moon/sun toggle button in the navbar, localStorage persistence, and a script that runs before the page renders to prevent a flash of the wrong theme.

It also respects the system preference on first visit. If your OS is set to light mode, the site starts in light mode. That kind of detail is easy to forget but makes a real difference.

## What Worked

**Speed.** The entire site went from empty directory to deployed on Vercel in one session. Components, styles, responsive design, animations, image optimization, blog setup with Astro content collections. All of it.

**Iteration.** The back and forth felt natural. I'd describe what I wanted, Claude would build it, I'd review and push back, and we'd converge on something good. It wasn't me accepting whatever was generated. It was a real collaboration.

**Learning Astro.** I came in knowing React and left understanding a fundamentally different approach to frontend development. Astro's component model, its zero-JS-by-default philosophy, content collections, and island architecture. I learned all of it by building, not by reading docs.

## What Didn't Work

**First drafts are generic.** Claude's initial text for my experience descriptions was made up. "Developed enterprise-grade software solutions" for Thomson Reuters. I had to call that out and provide my real career data. AI can't know what you actually did at your job.

**Unicode in Astro templates.** This one caught us both off guard. It's the kind of framework-specific gotcha that AI doesn't always know about until it fails.

**You still need taste.** Claude will build whatever you ask for. If you ask for grain textures, blur filters, and gradient overlays all at once, you'll get exactly that. It takes a human to look at the result and say "this is too much."

## What I'd Tell Other Developers

Try it. Not as a replacement for knowing how to code, but as a way to move faster on things you already understand conceptually. I knew what I wanted in a portfolio. I knew what good frontend code looks like. Claude helped me get there without spending a week on CSS.

Stay in the driver's seat. Review every line. Push back when something feels off. The best results came from me being specific about what I wanted and honest about what wasn't working.

Use it to learn. I specifically chose Astro because I didn't know it. Having an AI that could scaffold, explain, and iterate on Astro code while I was learning it was genuinely useful. It's like having a coworker who already knows the framework you're picking up.

## The Result

The site is live at [kshyatisekhar-panda.vercel.app](https://kshyatisekhar-panda.vercel.app). The code is on [GitHub](https://github.com/kshyatisekhar-panda/about-me). It has a video hero, career timeline, skills grid, project showcase, cricket stats, travel photography, a resume viewer, a blog (you're reading it), and light/dark theme support.

Every line of code was written through conversation. Not generated and forgotten, but discussed, reviewed, and refined.

That's what AI pair programming looks like in practice.
