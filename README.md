# Israeli Pension XML Analyzer

A client-side HTML application that processes XML files from Israeli pension providers (including the "Mimshak Achid" - Unified Interface format from the pension clearinghouse or providers) and displays a visual summary of your savings. All processing is done locally in your browser.

## ✨ Features

-   Upload one or more XML pension files.
-   Parses data locally in your browser – no data is sent to any server.
-   Supports the Israeli "Mimshak Achid" (Unified Interface) XML format.
-   Displays:
    -   A total summary: total balance, number of providers, and number of distinct products/accounts.
    -   A pie chart visualizing asset distribution by general product type (e.g., Pension Fund, Study Fund).
    -   A detailed table listing each account with its provider, specific program name, general product type, balance, management fees (deposit and estimated annual balance fee), and investment track.
-   User interface translated to Hebrew.
-   Export aggregated report to PDF (via browser's print functionality).
-   Export the detailed table data to a CSV file.

## 🛠 Tech Stack

-   HTML5
-   Vanilla JavaScript (ES6+)
-   Tailwind CSS (via CDN for styling)
-   Chart.js (for the pie chart)
-   Font Awesome (for icons, via CDN)

## 🚀 How to Use

1.  **Download:** Get the `pension_analyzer.html` file (or the name you've given it).
2.  **Open:** Open the `pension_analyzer.html` file in any modern web browser (like Chrome, Firefox, Edge, Safari).
3.  **Upload:**
    * Drag and drop your Israeli pension XML file(s) onto the designated area.
    * Or, click the "בחר קבצים" (Select Files) button to browse and select your XML files.
4.  **Analyze:** The tool will process the files and display the summary, chart, and table.
5.  **Export:**
    * Click "הדפס/ייצא ל-PDF" (Print/Export to PDF) to use your browser's print dialog to save the report as a PDF.
    * Click "ייצא טבלה ל-CSV" (Export Table to CSV) to download the detailed fund data as a CSV file.

## 💡 Notes & Known Limitations

* **Tailwind CSS CDN:** The browser console will show a warning: `cdn.tailwindcss.com should not be used in production.` This is because Tailwind CSS is loaded via a CDN, which is suitable for development and tools like this, but for large-scale production websites, an installation via npm/CLI is recommended. This does not affect the functionality of this tool.
* **Fee & Track Information:** For accounts/policies that might have multiple segments (e.g., different employers linked to the same pension account within the XML), the displayed management fees and investment track name in the table are based on the *first relevant segment* found for that account. The balance, however, is aggregated across all segments of that specific account.
* **PDF Export Layout:** The PDF export relies on the browser's "Print to PDF" functionality. The layout and appearance of the PDF might vary slightly between different web browsers or PDF viewers.
* **CSV Encoding:** The CSV file is exported with UTF-8 encoding and includes a BOM (Byte Order Mark) to improve compatibility with Hebrew characters in Microsoft Excel.

## 🔮 Future Improvements (Possible Ideas)

* More granular display of data if an account has multiple underlying segments (e.g., different fee structures per employer within the same pension policy).
* Advanced fee analysis, explicitly showing any discounts or special fee arrangements mentioned in the XML.
* Direct PDF generation using a JavaScript library (like jsPDF) for more consistent PDF output and control.
* Support for a wider range of older or proprietary XML formats if needed.
* Saving/loading analysis sessions using browser local storage.

---

*This tool is for informational purposes and helps visualize data from official pension XML reports. Always refer to your official statements from pension providers for definitive information.*
