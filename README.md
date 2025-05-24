Subtropico Springs - Mobile Barcode Scanner
🌟 Overview
Subtropico Springs - Mobile is a web-based barcode scanning application designed for mobile devices. It allows users to log in, scan barcodes either manually or using their device's camera, track scanned items, and manage scan history. The application also features an admin panel for user management and viewing aggregated scan data. All data is stored locally in the browser's localStorage.

✨ Features
User Authentication:

User signup and login system.

Dedicated Admin account with special privileges.

Maximum of 2 user-creatable accounts (plus one admin account).

Barcode Scanning:

Manual barcode entry.

Camera-based barcode scanning using html5-qrcode library.

Support for a specific barcode format (T\d[A-Z0-9]{3}[A-Z0-9]{2}\d{4}).

Visual feedback for scanned barcodes (image generated via tec-it.com API).

Audible feedback (beeps) for scan success, duplicates, and errors.

Scan History & Management:

Displays a history of scanned items with status (new, duplicate, invalid).

Timestamps for scans (displayed in SAST - South African Standard Time).

Item counter for valid scans.

Ability to clear scan history for the logged-in user (password protected).

Export scan history to CSV format.

Import scan history from a CSV file (for the logged-in user).

Admin Panel (for user "DylanK"):

View aggregated scan count and history from all users.

Manage user accounts:

Change usernames.

Change passwords.

Delete user accounts.

Admin actions are password-protected.

User Settings:

Logout functionality.

Delete own account (password protected, not available for admin).

User Interface:

Mobile-first responsive design.

Loading screen with animations.

Notifications for actions (success, error, info).

Dynamic display of current date and time.

Customizable theme colors via CSS variables.

Security (Basic):

Attempts to disable right-click context menu and some developer keyboard shortcuts.

Admin credentials are hardcoded.

User data stored in localStorage.

🛠️ Technologies Used
HTML5: Structure of the web application.

CSS3: Styling and layout, including custom properties (variables) for theming and animations.

JavaScript (ES6+): Application logic, DOM manipulation, event handling, and data management.

html5-qrcode: Library for integrating camera-based QR code and barcode scanning.

TEC-IT Barcode API: Used to generate barcode images for display.

Google Fonts: Roboto font.

Iconify Design: For SVG icons.

🚀 Setup and Usage
No Build Needed: This is a single HTML file application.

Open in Browser: Simply open the index.html (or the provided HTML file) in a modern web browser that supports the Web Audio API and localStorage.

Permissions: For camera scanning, you will need to grant camera permissions to the browser when prompted.

Default Admin Credentials:
Username: DylanK

Password: DylanKar13

(These are hardcoded in the JavaScript section of the HTML file.)

📝 Key Functionalities Explained
User Accounts
Users can sign up for an account. A maximum of two non-admin accounts can be created.

The Admin (DylanK) has a pre-defined password and can manage other user accounts.

Login provides access to the main application features.

Barcode Scanning
Manual Entry: Users can type a barcode into the input field. The barcode must match the format T\d[A-Z0-9]{3}[A-Z0-9]{2}\d{4} (e.g., T1ABCDE1234).

Camera Scan: Users can activate their device camera to scan barcodes. A reticle and scan line animation guide the process. The camera will attempt continuous autofocus. A "Refocus Camera" button is available if needed.

Duplicate Handling: The system checks for duplicate barcodes for the current user. If a barcode has been scanned before (and was valid), it's marked as a duplicate.

Scan Counter: Only new, valid barcodes increment the user's scan counter.

History Management
View History: Users can toggle a section to view their previous scans, including the barcode, timestamp, and status.

Clear History: Users can clear their entire scan history and reset their scan counter. This action requires password confirmation.

Export/Import (CSV):

Users can export their scan history to a CSV file. The CSV includes barcode value, scan timestamp (SAST), scan status, and the timestamp of the first valid scan for duplicates.

Users can import scan history from a CSV file. The CSV must have "BarcodeValue" and "ScanTimestampSAST" headers. Imported scans are processed, and user statistics (scan count, duplicates) are recalculated.

Admin Dashboard
The admin user sees an aggregated view of all scans from all non-admin users.

The admin can manage user accounts, including changing their usernames/passwords or deleting their accounts. These actions require the admin's password for confirmation.

Admin users cannot directly scan barcodes or import/clear history for individual users through the main UI elements designed for standard users. Their primary role is oversight and account management.

📁 File Structure
The entire application is contained within a single HTML file.

<style> block: Contains all CSS rules.

<script> block (inline): Contains all JavaScript logic.

HTML body: Defines the structure of the application.

⚠️ Important Notes & Limitations
Data Storage: All user account information, scan history, and counts are stored in the browser's localStorage. This means data is specific to the browser and device it was created on and can be cleared by the user through browser settings. Data is not persistent across different browsers or devices, nor is it backed up externally.

Security:

Admin credentials are hardcoded in the JavaScript. This is not secure for a production environment.

Passwords are stored in plain text in localStorage. This is highly insecure.

The attempts to disable developer tools are basic and can be easily bypassed.

Account Limit: Only two user-creatable accounts are allowed. This limit is also managed via localStorage.

External Dependencies:

Relies on html5-qrcode library hosted on unpkg.com.

Relies on barcode.tec-it.com for generating barcode images.

Relies on fonts.googleapis.com for the Roboto font.

Relies on api.iconify.design for SVG icons.
An internet connection is required for these external resources to load correctly.

Error Handling: Basic error handling is implemented, with notifications shown to the user. More robust error handling could be added.

SAST Timezone: Timestamps are formatted and parsed assuming SAST (Africa/Johannesburg). This might need adjustment if used in different timezones.

Sound Effects: The application uses the Web Audio API for simple sound effects. User interaction might be required to enable audio in some browsers.

©️ Disclaimer & Author
© D.K Brand . All rights reserved. Unauthorized copying or distribution of the code is prohibited.

Author: Dylan Karsten

This README provides a comprehensive guide to the Subtropico Springs mobile barcode scanning application.
