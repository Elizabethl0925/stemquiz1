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




Name: Elizabeth Lin
Tools used: ChatGPT, Colab, Browser
Q1:
- Key finding:
The data shows that Category B has the highest performance percentage among all four categories. Category A and D performed moderately, while Category C had the lowest result. The difference between the highest and lowest categories is significant enough to suggest uneven performance across areas. Overall, the results indicate a strong opportunity to improve lower-performing categories.
- Outlier:
Category C is the outlier because it performed noticeably lower than the other categories.
Q2:
- What was broken:
The hero section was not stacking vertically on mobile screens. When resizing below 600px, the KPI card remained beside the text instead of moving underneath it.
- What I changed:
I ensured the mobile media query was placed at the bottom of the CSS file so it properly overrode the base styles. I also confirmed that flex-direction: column; was correctly applied inside the @media (max-width: 600px) rule and verified that the viewport meta tag was present in the HTML.
Q3:
Prompt 1 (plan, no code):
I need to implement responsive breakpoints for a portfolio website using only HTML and CSS. The page has a header, a hero section with text and a KPI card, and a 4-column grid. The layout must change at mobile and tablet sizes. The hero should stack on mobile, and the navigation should stack and center. Please provide a step-by-step plan for implementing this responsive behavior without including any code.
Response snippet:
Define clear breakpoints for mobile (up to 600px) and tablet (up to 900px). Use Flexbox for the header and hero sections so you can change the flex direction at smaller screen sizes. Use CSS Grid for the card section and adjust the number of columns at each breakpoint. Place media queries after base styles so they override properly.
Accepted:
Use breakpoints at 600px and 900px for mobile and tablet.
Use flex-direction changes in media queries to control stacking behavior.
Rejected:
Suggested using flex order to rearrange hero elements.
I rejected this because simply changing flex-direction achieved the required layout more cleanly and with less complexity.

Prompt 2 (debug):
My hero section is not stacking vertically on mobile even though I added a media query. Here is my CSS:

.hero {
display: flex;
justify-content: space-between;
align-items: center;
}

@media (max-width: 600px) {
.hero {
flex-direction: column;
}
}

Why is it not stacking properly?
Response snippet:
Make sure your media query appears after the main .hero rule so it overrides correctly. Also verify that the viewport meta tag is included in your HTML head section. Without it, mobile breakpoints may not behave as expected.

What I verified:
- viewport sizes tested:
375px
768px
1200px

- what I checked visually:
Header alignment (logo left, nav right on desktop)
Navigation stacked and centered on mobile
Hero stacked vertically at 375px
Grid showed 4 columns at 1200px
Grid showed 2 columns at 768px
Grid showed 1 column at 375px
No horizontal scrolling
Hover effects worked on buttons and cards

Q4:
- Chart caption:
This chart shows the percentage performance across four categories, with Category B achieving the highest result and Category C performing the lowest.
- Decision based on chart:
Based on this data, I would allocate more resources to Category B to maximize strong performance while developing an improvement strategy for Category C.
Hero two columns
KPI card aligned right
Grid displayed 4 columns
Hover effects worked on cards and button
