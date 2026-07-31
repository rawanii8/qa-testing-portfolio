# AI Chat Demo Widget Remains Fully Untranslated in Arabic Mode

**Severity:** High
**Priority:** Medium

## Description
On the workforce management platform "AI" features page (Arabic language mode), the interactive demo widget on the right side of the page — showing a sample the workforce management platform AI conversation ("Meeting notes · transcribed", "decisions captured · 2 action items ready 3") — is displayed entirely in English, while the rest of the page (feature cards, titles, descriptions) is correctly localized in Arabic.

## Steps to Reproduce
1. Navigate to the workforce management platform AI features page (the staging environment/features/ai)
2. Ensure the site language is set to Arabic (عربي)
3. Observe the demo chat widget on the right side of the page
4. Read the result card showing "Meeting notes · transcribed" and the line below it

## Actual Result
The result card text displays entirely in English: "Meeting notes · transcribed" and "decisions captured · 2 action items ready 3", with no Arabic translation, while the user-side message above it ("لخّص اجتماع الأمس وأنشئ مهامًا للعوائق") and the rest of the widget are in Arabic.

## Expected Result
The result card text should be fully localized in Arabic (e.g. "ملاحظات الاجتماع · تم تفريغها" / "تم رصد القرارات · 2 من 3 عناصر إجراء جاهزة"), consistent with the rest of the widget and page.

## Environment
* URL: [the workforce management platform public site staging URL] 
* Language: Arabic (عربي)
* Browser: Chrome
* Page section: AI demo chat widget (right side) — result card following the transcribed meeting notes message
