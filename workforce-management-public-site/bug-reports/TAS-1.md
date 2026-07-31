# Untranslated/Grammatically Inconsistent Arabic Text in "Tasks & Sprints" Feature Card

**Severity:** Medium
**Priority:** Medium

## Description
On the workforce management platform features/landing page (Arabic language mode), the "Tasks & Sprints" feature card description contains two localization issues within the same string: (1) the English word "epics" was left untranslated inside an otherwise Arabic sentence, and (2) the word "سبرنتات" is missing the definite article "ال", and should read "الاسبرنتات" per correct Arabic grammar in this context.

## Steps to Reproduce
1. Navigate to the workforce management platform features/signup page (staging environment)
2. Switch the site language to Arabic (عربي)
3. Locate the "المهام والسبرنتات" (Tasks & Sprints) feature card in the Features grid
4. Read the description text under the card title

## Actual Result
The description text reads: "مهام كانبان، epics، سبرنتات، تسميات، ومؤقتات"

* "epics" appears in English in the middle of an Arabic sentence, breaking language consistency and RTL text flow.
* "سبرنتات" is missing the definite article "ال" and should be "الاسبرنتات".

## Expected Result
The full string should be grammatically correct and fully localized in Arabic, e.g.: "مهام كانبان، الملاحم، الاسبرنتات، تسميات، ومؤقتات" (or an equivalent correct Arabic phrasing), with "Epics" translated and "الاسبرنتات" carrying the correct definite article.

## Environment
* URL: [the workforce management platform public site staging URL] 
* Language: Arabic (عربي)
* Browser: Chrome
* Page section: Features grid — "Tasks & Sprints" card
