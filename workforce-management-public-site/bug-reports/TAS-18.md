# Arrow Direction Not Mirrored for RTL Layout in "Testimonial Ranking" Card

**Severity:** Low
**Priority:** Medium

## Description
On the workforce management platform Customers page (Arabic language mode), the testimonial card showing "1 → أدوات 4" (4 Tools → 1) uses an arrow that points in the same direction as the LTR/English version, instead of being mirrored for RTL reading direction. Since Arabic reads right-to-left, the arrow should visually point from right to left to correctly convey the "from 4 to 1" progression.

## Steps to Reproduce
1. Navigate to the workforce management platform Customers page (the staging environment/customers)
2. Ensure the site language is set to Arabic (عربي)
3. Locate the testimonial card titled "4 أدوات → 1"
4. Observe the direction of the arrow relative to the Arabic text flow

## Actual Result
The arrow direction is not mirrored for RTL — it appears reversed relative to the natural reading flow of the Arabic text, making the "4 → 1" progression visually inconsistent with the surrounding RTL layout.

## Expected Result
The arrow should be mirrored to match RTL directionality, so the visual flow correctly represents the progression from "4" to "1" when read right-to-left.

## Environment
* URL: [the workforce management platform public site staging URL] 
* Language: Arabic (عربي)
* Browser: Chrome
* Page section: Testimonials/customer quotes grid — "4 Tools → 1" card title
