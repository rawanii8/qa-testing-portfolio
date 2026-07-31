# "Subscribe" Button in Newsletter Section Incorrectly Redirects to Signup Page

**Severity:** Medium
**Priority:** Medium

## Description
In the website footer under the "Stay in the loop" newsletter section, entering an email address and clicking the "Subscribe" button does not process a newsletter subscription. Instead, it redirects the user to the free plan registration page (/signup?plan=free).

## Steps to Reproduce
1. Navigate to the workforce management platform staging site
2. Scroll down to the footer section
3. Locate the "Stay in the loop" newsletter subscription field
4. Enter a valid email address (e.g., [[test-account-email]|mailto:[test-account-email]])
5. Click the "Subscribe" button

## Actual Result
The user is redirected to the workspace creation signup page: [the workforce management platform public site staging URL]

## Expected Result
The system should validate the email, process the newsletter subscription, and display a success message inline (or redirect to a dedicated newsletter thank-you page) without forcing the user into the account creation flow.

## Environment
* URL: [the workforce management platform public site staging URL] 
* Browser: Chrome
* Page section: Footer — "Stay in the loop" newsletter subscription field
