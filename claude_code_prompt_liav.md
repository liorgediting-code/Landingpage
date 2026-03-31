# פרומפט לקלוד קוד — דף נחיתה לליאב כהן
# העתק את כל הטקסט מתחת לקו הזה ישירות לקלוד קוד

---

<task>
Build a Hebrew RTL lead generation landing page for a sales & marketing coaching business.
Single self-contained HTML file — all CSS and JS inline.
No frameworks, no build tools, no npm.
Google Fonts via CDN only. No Tailwind.
Language: Hebrew. Direction: RTL (dir="rtl" on <html>).
Goal: capture leads (name, email, phone) via form → POST to Make.com webhook.
</task>

<context>
Business: Liav Cohen — sales coach who, together with his marketing partner, offers a complete sales + marketing wrapper for Israeli service business owners.
The product is a 3-month intensive coaching & management program.
Target audience: Israeli service business owners who sell a product/service priced above ₪3,000, currently generating ₪10,000–₪20,000/month, stuck at that plateau, and hate their sales process.
They are NOT looking for a traditional business consultant (too expensive, ₪50K+, wrong stage).
They want results — more revenue, better close rates — without learning to love sales.
After form submission: they receive a WhatsApp message + email sequence. Page should redirect or show a Calendly embed for booking a discovery call.
Tone: professional and premium but grounded and direct — "בגובה העיניים". Not corporate. Not guru. Real.
</context>

<design_system>
/* ── DESIGN TOKENS ── */
:root {
  --primary:     #E8600A;   /* deep burnt orange — main CTA, accents */
  --primary-dark:#C04E08;   /* hover state */
  --bg:          #0D0D0D;   /* near-black background */
  --surface:     #161616;   /* cards, sections */
  --surface-2:   #1E1E1E;   /* elevated cards */
  --border:      #2A2A2A;   /* subtle borders */
  --text:        #F0EDE8;   /* warm off-white */
  --text-muted:  #8A8680;   /* secondary text */
  --gold:        #C9A84C;   /* premium accent for badges/results */
}

/* ── TYPOGRAPHY ── */
Font: "Assistant" from Google Fonts — weights 400, 700, 900 (ExtraBold)
Headings: Assistant ExtraBold (900), letter-spacing: -0.03em
Subheadings: Assistant Bold (700)
Body: Assistant Regular (400), line-height: 1.7
Scale: h1=56px (mobile: 36px), h2=40px (mobile: 28px), h3=24px, body=17px

/* ── SPACING ── */
Base unit: 8px — use multiples: 8, 16, 24, 32, 48, 64, 96, 128

/* ── VISUAL STYLE ── */
Cards: border-radius 16px, border: 1px solid var(--border)
Buttons: border-radius 8px, font-weight 900, font-size 18px
Shadows: layered — 0 4px 24px rgba(232,96,10,0.15), 0 1px 4px rgba(0,0,0,0.4)
Background texture: subtle noise grain on hero via CSS (use SVG filter or background-image: url("data:image/svg+xml..."))
Section dividers: thin 1px border or gradient fade — never hard lines
</design_system>

<aesthetics_directive>
This page must NOT look like a generic AI-generated landing page.
Commit to a bold visual identity: dark premium background with a single dominant warm orange accent.
Typography must create strong hierarchy — massive h1 with ultra-thin subtext below it.
Use dramatic whitespace. Let sections breathe. Avoid cramped layouts.
Add staggered scroll-reveal animations using IntersectionObserver (not libraries).
Add micro-interactions: buttons scale on hover (transform: scale(1.03)), cards lift (translateY(-4px)).
Background: the hero section must have a layered gradient — radial glow of the primary color at low opacity + noise grain texture on top.
The overall feel: "This isn't a Facebook ad course. This is a serious program for serious business owners."
AVOID: flat white sections, purple-on-white, generic card grids with emoji icons, Inter font, system fonts.
DO: extreme weight contrast (900 next to 400), warm off-white text on near-black, orange used sparingly as the single accent, gold for results/proof moments.
</aesthetics_directive>

<sections>

## 1. HERO
- Hebrew headline: WRITE THE BEST POSSIBLE headline for this audience. 
  Direction: They are stuck at ₪10K–20K/month. They hate selling. They know they should be earning more. Hit that nerve.
  Example direction (Claude should write better): "תקוע על ה-10K? הבעיה היא לא המוצר שלך."
- Subheadline: 2 sentences max. What this program is, who it's for.
- ONE primary CTA button: "אני רוצה לצאת מהתקרה" — scrolls to lead form
- Background: dark with radial orange glow, noise grain, optional subtle geometric line pattern
- No hero image needed — typography-first hero

## 2. PAIN POINTS (3 blocks)
Title section: "אם אתה מזדהה עם אחד מהמשפטים האלה — המשך לקרוא"
Pain 1: שונא לעשות מכירות. מרגיש לחוץ, לא אותנטי, מוותר על לידים טובים כי לא יודע להסגיר.
Pain 2: יש לידים. אין סגירות. הלקוחות "חושבים על זה" ואתה יודע שזה אומר לא.
Pain 3: תקוע על אותה הכנסה חודש אחרי חודש. לא גדל. לא מבין למה.
Design: 3 cards, dark surface, orange left-border accent, no icons — just bold text

## 3. THE SOLUTION / WHO WE ARE
Section title: "מעטפת שיווק + מכירות שעובדת בשבילך — לא בגללך"
2–3 short paragraphs introducing Liav Cohen and his marketing partner.
Key message: not a course, not a consultant — an active 3-month hands-on program.
They don't just teach — they build, manage, and close alongside you.
Include: photo placeholder (circular, 200x200px, labeled "תמונת ליאב כהן") with name + title underneath

## 4. THE PROGRAM — WHAT'S INCLUDED
Section title: "מה קורה בתוכנית"
Use the Miro board structure to explain the deliverables. Build 4 feature blocks:

Block 1 — ליווי מכירות אישי
"אנחנו נכנסים לשיחות שלך, מנתחים את הסרטונים, ומשפרים את המגרש שלך בזמן אמת. לא תיאוריה — תרגול חי."

Block 2 — ניהול קמפיינים (לחבילה המשולבת)
"ניהול מלא של הקמפיינים שלך — מהאסטרטגיה ועד הפרסום. אתה מתמקד בלקוחות, אנחנו מביאים את הלידים."

Block 3 — סרטוני המלצות + ניתוח שיחות
"אנחנו מצלמים סרטוני המלצות עם הלקוחות שלך, ומנתחים עד 3 שיחות בשבוע לפידבק מיידי."

Block 4 — קבוצת וואטסאפ 24/5
"גישה ישירה לליאב ולצוות. שאלה? עצה? ב-24/5. לא אחרי 3 ימים — עכשיו."

Layout: 2x2 bento grid, cards with orange top-border, heavy heading + body text

## 5. RESULTS / SOCIAL PROOF
Section title: "מה שקורה כשעושים את זה נכון"
Big stat callout: "לקוח אחד הגיע מ-₪4,000 לחודש ל-₪40,000 לחודש"
Style: giant number in gold color, subtitle in text-muted

Video testimonial placeholders: 2–3 video thumbnail placeholders (16:9 ratio, dark surface, play button icon, label "סרטון המלצה — [שם לקוח]")
Photo testimonial placeholders: 2 quote blocks with circular photo placeholder, name, and business type. Write placeholder quote text that sounds real: e.g. "לפני שהתחלנו הייתי מוותר על כל שיחה שנייה. עכשיו אני סוגר 7 מתוך 10."

## 6. PRICING — DO NOT SHOW EXACT PRICES
Section title: "התוכנית — 3 חודשים של עבודה אמיתית"
Explain the 3 tiers simply WITHOUT showing the numbers:
Option A — ליווי מכירות: ליווי אישי מלא על המכירות שלך
Option B — שיווק + מכירות: מעטפת מלאה — גם הקמפיינים וגם המכירות
Option C — שיווק בלבד: ניהול קמפיינים מקצועי

For each: 3-bullet feature list. CTA under each: "לפרטים ומחיר — השאיר פרטים" → scrolls to form
Note: "המחיר ניתן בשיחת ייעוץ בלבד"

## 7. OBJECTIONS / FAQ
Section title: "שאלות שכנראה עולות לך עכשיו"
Write 5 real objections for this audience in Q&A accordion format:

Q1: "אני לא צריך מאמן — אני צריך יותר לידים"
A: כתוב תשובה שמסבירה שלידים בלי יכולת סגירה = כסף זרוק. הם כבר מוציאים על שיווק ולא מסגירים. הבעיה היא המכירות.

Q2: "3 חודשים זה הרבה זמן להתחייב"
A: תשובה שמדגישה שזה הזמן המינימלי לתוצאות אמיתיות. כל מה שפחות — זה קורס.

Q3: "כבר ניסיתי קורסים ולא עזר"
A: הדגש שזה לא קורס — זה ליווי אקטיבי. הם לא לומדים, הם עובדים יחד עם ליאב.

Q4: "זה יקר לי עכשיו"
A: חשבון פשוט: אם הם תקועים על 15K ואנחנו מכפילים — ההשקעה מחזירה את עצמה בחודש הראשון.

Q5: "מה אם זה לא יעבוד בשבילי?"
A: תשובה אנושית — אין הבטחה בהסכם אבל יש מחויבות מלאה. ליאב לא לוקח לקוחות שהוא לא מאמין שיצליחו.

Design: accordion with smooth animation, orange arrow indicator

## 8. LEAD CAPTURE FORM
Section title: "מוכן לצאת מהתקרה?"
Subtext: "השאיר פרטים ונחזור אליך תוך שעה עם כל המידע"
Fields:
- שם מלא (required)
- אימייל (required, email type)
- מספר טלפון (required, tel type, Israeli format)

CTA button text: "אני רוצה לגדול →"
Button: full-width on mobile, centered on desktop, var(--primary) background, white text, weight 900

On submit:
1. Client-side validation (all fields required, email format, phone 10 digits)
2. POST to Make.com webhook: https://hook.eu1.make.com/PLACEHOLDER_WEBHOOK_URL
   Body: { "name": "...", "email": "...", "phone": "...", "source": "landing_page_liav" }
3. On success: hide form, show success message in Hebrew + Calendly embed below
   Calendly URL placeholder: https://calendly.com/PLACEHOLDER_LIAV_CALENDLY
   Success message: "תודה! נחזור אליך בוואטסאפ תוך שעה. בינתיים — קבע שיחה בזמן שנוח לך:"
4. On error: show Hebrew error message inline below form, do NOT reload page

## 9. FOOTER
Simple dark footer:
- Logo/name: "ליאב כהן | שיווק ומכירות"
- Short tagline
- © 2025 כל הזכויות שמורות
- Links: (placeholders) תנאי שימוש | פרטיות

</sections>

<rtl_rules>
- <html dir="rtl" lang="he">
- Use CSS logical properties throughout: margin-inline-start/end, padding-inline-start/end
- Text alignment: default is right-align for Hebrew content
- Flexbox: row-reverse is NOT needed if dir="rtl" is set correctly — test and verify
- Form inputs: text-align: right; direction: rtl
- Numbers, prices (₪), and phone number format stay LTR — wrap in <span dir="ltr">
- Calendly embed: add data-locale="he" if available
- Font "Assistant" is Hebrew-native — no fallback needed for Hebrew characters
</rtl_rules>

<animations>
- Page load: hero headline fades up (opacity 0→1, translateY 20px→0) with 0.6s ease
- Scroll reveal: all section cards use IntersectionObserver — stagger children with animation-delay: calc(var(--i) * 0.1s)
- Buttons: transform: scale(1.03) + brightness(1.1) on hover, transition: 0.2s ease
- Cards: translateY(-4px) + shadow intensify on hover
- Accordion: max-height transition for smooth open/close
- Respect prefers-reduced-motion: wrap all animations in @media (prefers-reduced-motion: no-preference)
</animations>

<constraints>
DO NOT use: Inter, Roboto, Arial, system fonts (Assistant only)
DO NOT use: purple, blue, green accents — orange and gold ONLY
DO NOT use: Tailwind, Bootstrap, any CSS framework
DO NOT use: Lorem ipsum or English placeholder text — all text must be real Hebrew
DO NOT use: emoji icons in section headings
DO NOT: one-shot the entire page without reviewing the design system
DO NOT: add explanatory code comments that clutter the file
DO: Use CSS custom properties (variables) for every color and size
DO: Build responsive — mobile-first, breakpoints at 768px and 1024px
DO: Keep all JS vanilla — no jQuery, no libraries
DO: Make the form UX feel fast and responsive — disable button + show spinner on submit
DO: The page must look production-ready, not like a template
</constraints>

<output>
Single file: index.html
All CSS in <style> in <head>
All JS in <script> before </body>
Google Fonts loaded via <link> in <head>
Production-ready. No tutorial comments. No placeholder console.logs.
</output>
