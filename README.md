PROMPT 1
Prompt I gave chatgpt
I need to implement responsive breakpoints for a portfolio page using only HTML and CSS.
The layout includes:
A header with logo and navigation
A hero section with text on the left and a KPI card on the right
A 4-column grid section
Requirements:
Desktop layout shows full horizontal layout
Tablet should reduce grid columns
Mobile should stack hero content vertically
Navigation should stack and center on mobile

Two Things I Accepted from the Plan:
Use mobile-first or structured breakpoints (600px and 900px).
I accepted the suggestion to define clear breakpoint ranges:
0–600px → Mobile
601–900px → Tablet
901px+ → Desktop

Use Flexbox direction change for hero stacking.
The plan suggested switching flex-direction: row to column for mobile instead of rewriting layout logic.
This made the hero behavior clean and easy to control.

One Thing I Rejected:
The plan suggested using order properties to reposition the hero card on mobile.
I rejected this because the layout already stacked naturally, changing flex-direction was simpler and 
adding order would introduce unnecessary complexity. I prioritized simplicity and readability over advanced positioning.

PROMPT 2
Problem Statement:
When resizing to mobile width (below 600px), the hero section was not stacking vertically.
The KPI card stayed beside the text instead of moving below it.

Exact CSS Snippet I Asked About:
.hero {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 40px 0;
}

@media (max-width: 600px) {
  .hero {
    flex-direction: column;
  }
}

Most Important Part of the AI Response:
The AI explained if the layout is not stacking, check whether: another CSS rule overrides flex-direction,
the media query is placed before the main .hero rule and the viewport meta tag is missing in the HTML

It also emphasized that media queries should appear after the base styles to properly override them.

What I Changed Afterward:
I moved the mobile media query to the bottom of the CSS file.
I confirmed the <meta name="viewport"> tag was present.
I added text-align: center; inside the mobile rule to improve visual layout.
After this, the hero stacked correctly at 600px and below.

VERTIFICATION LIST
Viewport Sizes Tested
375px (mobile)
768px (tablet)
1200px (desktop)

What I Checked Visually:
At 375px (Mobile)
Header stacked vertically
Navigation links centered and stacked
Hero text above KPI card
Grid displayed 1 column
No horizontal scrolling

At 768px (Tablet)
Header horizontal
Hero remained horizontal
Grid displayed 2 columns
Spacing looked balanced

At 1200px (Desktop)
Logo left, nav right
Hero two columns
KPI card aligned right
Grid displayed 4 columns
Hover effects worked on cards and button
