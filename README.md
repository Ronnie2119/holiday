TUI Holiday Scraper

Automates browsing the TUI Last-Minute Holidays page, extracting hotel listings that are adults-only, have a TripAdvisor rating of 4.5 or above, and do not advertise kids' facilities. Outputs data into .txt, .csv, and .json formats, complete with screenshots for each step.

Requirements

Install required packages:

pip install tqdm pyppeteer2

Or on Windows:

py -m pip install tqdm pyppeteer2

Additional Requirements for Windows:
Pyppeteer2 will auto-download a Chromium build on first run. Ensure internet access and permissions to write to user folders.

Running the Script

Once dependencies are installed, simply run:

python tui_scraper.py

Or on Windows:

py tui_scraper.py

Features

Navigates the TUI website and clicks through cookie banners and "Load More" buttons using pyppeteer2

Captures screenshots at key stages (initial_load.png, after_click.png, etc.)

Scrolls and extracts all hotel links

For each hotel, it checks:

If the hotel is adults-only

If the TripAdvisor rating is 4.5 or higher

If no references to kids’ facilities are found


Exports filtered results to:

results.txt

results.csv

previous_results.json (used to track cost changes)


Compares current cost against the last run and logs any changes


Output Files

results.csv: Full tabular data of valid listings

results.txt: Human-readable summary

previous_results.json: Used internally for cost tracking

debug_links.txt: All scraped hotel detail page links

Screenshots saved for each key interaction and page load


Troubleshooting

If Chromium fails to download or open, delete the .local-chromium folder in your user profile and try again

Set headless=True in launch() if you don’t want the browser to open visibly
