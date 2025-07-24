# shrinkurl
# DriveURL - Google Sheets Powered URL Shortener

## Project Prompt

Create a lightweight TinyURL-like service that:

1. Uses Google Sheets as the database with:
   - Column A: Original/long URLs
   - Column B: Automatically generated short codes

2. Client-side functionality:
   - Generates random 6-character short codes (a-z, A-Z, 0-9)
   - Allows optional custom short codes
   - Validates URL format (must include http:// or https://)

3. Data collection via Google Forms:
   - Form submissions populate the Google Sheet
   - Form should have two fields: original URL and short code
   - No server-side processing needed

4. GitHub Pages hosting:
   - Single HTML file with embedded CSS/JS
   - No backend required
   - Should handle both:
     * URL shortening interface (/) 
     * Redirection logic (/abc123)

5. Redirection workflow:
   - When visiting a short URL:
     1. Fetches the Google Sheet data (publicly readable)
     2. Looks up the short code
     3. Redirects to the original URL
     4. Shows error if:
        - Short code doesn't exist
        - Can't access spreadsheet

6. Additional requirements:
   - Mobile-responsive design
   - Copy-to-clipboard functionality
   - Clean, user-friendly interface
   - Clear error messages
   - No login/auth required

## Setup Instructions

1. Google Sheets Setup:
   - Create sheet with columns: Original URL | Short Code
   - Share publicly: Anyone with link can view
   - Note spreadsheet ID from URL

2. Google Forms Setup:
   - Create form with two text fields
   - Link to your Google Sheet
   - Note form ID from URL

3. Configuration:
   - Edit the CONFIG section in index.html:
     * domain: Your custom/GitHub domain
     * spreadsheetId: Your Google Sheet ID
     * formId: Your Google Form ID
     * sheetName: Worksheet name (default "Sheet1")

4. Deployment:
   - Upload index.html to GitHub
   - Enable GitHub Pages
   - Set up custom domain (optional)

## Technical Notes

- Uses Google Sheets API (gviz/tq) for reading data
- Form submissions use no-cors POST to Google Forms
- Entire solution in one HTML file for easy hosting
- No dependencies except Google services
