# "Compare Plans" Button is Non-Functional on Pricing Page

**Severity:** Medium
**Priority:** Medium

## Description
On the pricing page, clicking the "قارن الخطط" (Compare Plans) button in the hero section does not trigger any action, navigation, or scroll behavior. Additionally, since the comparison table is already fully visible further down the same page, the button is effectively redundant in its current non-functional state — it should either scroll the user to that table or be removed.

## Steps to Reproduce
1. Navigate to the pricing page (the staging environment/pricing)
2. Locate the main hero section with the text "خطط شفافة لكل فريق"
3. Click the "قارن الخطط" button next to "ابدأ مجاناً"
4. Observe the behavior

## Actual Result
Nothing happens when the button is clicked. The URL doesn't change, and no scroll action is triggered.

## Expected Result
Clicking the button should smoothly scroll the user down to the "قارن الخطط" comparison table located further down the page, or the button should be removed if this behavior isn't intended.

## Environment
* URL: [the workforce management platform public site staging URL] 
* Browser: Chrome
* Page section: Hero section — "قارن الخطط" button
