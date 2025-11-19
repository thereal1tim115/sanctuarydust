# Documentation for `index.html`

## Overview
This document provides a technical overview of the `index.html` file for the "Sanctuary Dust" forthcoming album landing page. The page is designed to be visually engaging, featuring animations and links to music streaming platforms.

## Technology Stack
- **HTML5**: Semantic structure.
- **Tailwind CSS**: Utility-first CSS framework loaded via CDN for layout and styling.
- **Font Awesome**: Icon library loaded via CDN for social/music platform icons.
- **Custom CSS**: Inline styles in the `<head>` for specific animations.

## JavaScript Functions
**There is no custom JavaScript logic in this file.** 
The only `<script>` tag present is used to load the Tailwind CSS library:
```html
<script src="https://cdn.tailwindcss.com"></script>
```
All interactive elements and animations are achieved using **CSS3 Animations** and **Pseudo-classes** (like `:hover`).

## Features & Implementation Details

### 1. Visual Animations (CSS)
The page uses several custom `@keyframes` defined in the `<style>` block to create dynamic effects without JavaScript.

| Animation Name | Description | Usage |
| :--- | :--- | :--- |
| `float` | Moves an element up and down while slightly rotating it. | Applied to album covers via `.float-animation` class. |
| `fadeInUp` | Fades an element in from opacity 0 to 1 while moving it up. | Used for entrance animations on text and cards via `.fade-in-up`. |
| `shimmer` | Moves a background gradient across text. | Used on the "Forthcoming Album 2026" badge via `.shimmer`. |
| `pulse-glow` | Pulsates the box-shadow of an element. | Applied to album covers via `.pulse-glow`. |
| `particle-float` | Moves background particles upwards and fades them out. | Used for the background particle effects via `.particle`. |

### 2. Interactive Elements
Interactivity is handled purely through CSS classes, particularly Tailwind's `group` and `hover` modifiers.

*   **Album Covers**:
    *   **Zoom & Rotate**: On hover, the `.album-cover` class scales up (`scale(1.03)`) and rotates slightly (`rotate(1deg)`).
    *   **Overlay**: An overlay with "Listen Now" text fades in using `opacity-0` to `group-hover:opacity-100`.

*   **Music Platform Icons**:
    *   **Scale Effect**: Icons grow in size on hover (`hover:scale-110`).
    *   **Shadow**: Colored shadows appear on hover (`group-hover:shadow-[color]-500/50`).

### 3. Background Particles
The background features floating particles implemented as `div` elements with the class `.particle`.
*   **Positioning**: They are absolutely positioned (`fixed inset-0`) and ignore pointer events (`pointer-events-none`) so they don't interfere with clicking.
*   **Timing**: Each particle has a different `left` position and `animation-delay` inline style to create a random, organic feel.

### 4. Responsive Design
The layout uses Tailwind's responsive prefixes:
*   `grid-cols-1 md:grid-cols-3`: Stacks columns on mobile but creates a 3-column grid on medium screens and larger.
*   `text-7xl md:text-9xl`: Adjusts the main title size based on screen width.

## Structure Breakdown

1.  **Head**:
    *   Meta tags for viewport and charset.
    *   CDNs for Tailwind and Font Awesome.
    *   Internal `<style>` block for custom animations.

2.  **Body**:
    *   **Background**: A fixed gradient background (`bg-gradient-to-br`).
    *   **Particles Container**: Holds the floating background elements.
    *   **Main Container**:
        *   **Header**: Title "Sanctuary Dust" and subtitle.
        *   **Grid**: Contains 3 album cards (Midnight Mercy, Half Hallelujah, Sanctuary Dust).
            *   Each card has an image and a row of links (Spotify, Apple Music, Amazon).
    *   **Footer**: Copyright notice.
