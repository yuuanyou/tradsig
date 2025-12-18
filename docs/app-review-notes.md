# App Review – Technical Notes

This document provides technical clarification for App Store reviewers regarding the design, functionality, and data handling of the TradSig iOS application.

---

## 1. App Overview

TradSig is a lightweight native iOS application that serves as a secure wrapper for an existing web-based service.

The app uses WKWebView to display content from the official website and does not provide general web browsing functionality.

---

## 2. Core Functionality

- Display authenticated web content via WebView
- Receive system push notifications for record updates
- Redirect users to relevant pages when a notification is tapped

The app does **not** execute trades, provide investment advice, or generate trading signals.

---

## 3. Push Notification Behavior

### Purpose

Push notifications are used **only as reminders** to inform users that a record has been updated.

They do not contain sensitive data or actionable instructions.

### Payload Characteristics

- Notifications include a title and short description
- Additional parameters (e.g. page identifiers) are used only for navigation
- No financial values or trade parameters are included

---

## 4. Notification Tap Handling

When a user taps a notification:

1. iOS launches the TradSig app
2. The app parses parameters included in the notification payload
3. A specific page is opened inside the WebView
4. The page displays the latest available records

The page content is fully controlled by the web service.

---

## 5. Data Handling & Storage

- The app does **not** store trading records locally
- The app does **not** cache user financial data
- All authentication and authorization are handled by the server
- Communication uses HTTPS only

---

## 6. User Accounts

- User accounts are managed entirely by the web service
- The app does not create, modify, or store user credentials
- No third-party login providers are used

---

## 7. Payments & Monetization

- The app does not contain in-app purchases
- No payment processing is implemented
- Any access control is handled server-side

---

## 8. Privacy & Compliance

- The app does not collect personal data beyond system-required identifiers
- Push notification tokens are used solely for notification delivery
- No analytics or tracking SDKs are included

---

## 9. Disclaimer

All information presented in the app and notifications is for informational purposes only.

The app does not provide investment advice or trading recommendations.

---

## 10. Reviewer Test Information

If a test account is required, credentials will be provided in App Store Connect.

Thank you for reviewing the TradSig application.
