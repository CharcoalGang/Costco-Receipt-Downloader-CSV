# Costco Receipt CSV Fetcher

A JavaScript snippet that fetches your Costco order history and converts it into a detailed CSV format suitable for spreadsheets (Excel, Google Sheets).

## Features
* **Detailed Data:** Exports 28 columns including Item Name, Unit Price, Quantity, Tax Flags, and Discounts.
* **Smart Math:** Automatically calculates individual unit prices (e.g., price per steak) and handles item quantities.
* **Adjustments:** Properly handles "Instant Savings," CRV taxes, and other surcharges by attaching them to the correct items rather than listing them as separate rows.
* **No Extension Required:** Runs directly in your browser console.

## How to Use

1. **Login:** Go to [www.costco.com](https://www.costco.com) and log in to your account.
2. **Navigate:** Go to the [Order Status page](https://www.costco.com/OrderStatusCmd).
   * *Note:* You must be on this specific page for the script to access the correct authorization tokens.
3. **Open Console:**
   * **Windows:** Press `F12` or right-click anywhere on the page and select **Inspect**, then click the **Console** tab.
   * **Mac:** Press `Command + Option + J` (Chrome) or `Command + Option + C` (Safari).
4. **Enable Pasting:** Attempt to paste the code. If your browser blocks it and shows a warning (e.g., "Warning: Don't paste code..."), type `allow pasting` and press **Enter**.
   * *Note:* This is a standard browser security feature.
5. **Run:** Copy the entire script, paste it into the console, and press **Enter**.
6. **Select Dates:** A popup window will appear asking for your **Start Date** and **End Date**. Enter them in `MM/DD/YYYY` format.
7. **Download:** The script will fetch your history and automatically trigger a `.csv` download.

## Configuration

### Changing Default Dates
The script is interactive and will ask you for dates every time you run it. However, if you want to change the **pre-filled default dates** (so you don't have to type them every time):

1. Scroll to the bottom of the script to the `downloadFullCsv` function.
2. Find the lines:
   ```javascript
   var defaultStart = '01/01/2023';
