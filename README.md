# LinkedIn Web Scraper

This project is a LinkedIn scraper built to extract posts, the number of likes on each post, and the links of each post from LinkedIn profiles. The scraper leverages **Selenium** for browser automation and **pandas** for managing the data.

## Features

* **Scrape LinkedIn Profiles**: Extract posts and engagement (likes) for each post on a LinkedIn profile.
* **Data Export**: Scraped data is saved into CSV files for easy analysis and review.
* **Customizable**: The scraper can be run on a single profile or multiple profiles using CSV input.
* **Handles Multiple Profiles**: The scraper can process a list of LinkedIn profiles efficiently.

## Project Structure

```
LINKEDIN_WEB_SCRAPER/
├── chrome-profile/              # Chrome user profile for Selenium
├── chromedriver-win64/          # Chrome WebDriver (Windows version)
├── selenium_profile_3533/       # Selenium browser profile (alternative)
├── selenium_profile_9090/       # Another Selenium browser profile (alternative)
├── LinkedIn_Scraper.ipynb       # Jupyter notebook for scraping LinkedIn profiles
├── profiles.csv                 # CSV file containing LinkedIn profile URLs to scrape
├── sardar-dawar.csv             # Example output CSV with scraped data
└── scraper_posts_links_likes.ipynb # Jupyter notebook for scraping posts, likes, and links from LinkedIn profiles
```

## Requirements

Make sure you have the following dependencies installed:

* Python 3.8 or higher
* Selenium
* pandas
* Chrome WebDriver (compatible with your version of Chrome)

Install the required dependencies using the following command:

```bash
pip install -r requirements.txt
```

## Setup Instructions

1. **Clone the Repository:**

```bash
git clone https://github.com/yourusername/linkedin-web-scraper.git
cd linkedin-web-scraper
```

2. **WebDriver Setup:**

   * Download the correct version of **ChromeDriver** from [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/) based on your installed version of Chrome.
   * Make sure the WebDriver is in the **chromedriver-win64/** folder.

3. **Profile Configuration:**

   * You can use your Chrome browser's user profile for Selenium to facilitate login.
   * The profile will be stored in **chrome-profile/** (or any alternative `selenium_profile_*` directory).

4. **Profile URLs:**

   * Add LinkedIn profile URLs that you want to scrape into the `profiles.csv` file.

5. **Login:**

   * During the first run, Selenium will require you to log in manually. Once logged in, your session will be saved and reused automatically.

## Usage

1. **Single Profile Scraping:**

To scrape data from a single LinkedIn profile, run the `LinkedIn_Scraper.ipynb` notebook:

```bash
jupyter notebook LinkedIn_Scraper.ipynb
```

2. **Multiple Profiles Scraping:**

To scrape posts, likes, and links from a list of profiles in `profiles.csv`, run the `scraper_posts_links_likes.ipynb` notebook:

```bash
jupyter notebook scraper_posts_links_likes.ipynb
```

This will process all profiles in the CSV file and store the results in a CSV file like `sardar-dawar.csv`.

## Output

The scraper saves the data into a CSV file with the following format:

```csv
Post URL, Likes Count, Post Content
https://linkedin.com/post/xyz, 123, "This is a sample post"
https://linkedin.com/post/abc, 56, "Another example post"
```

## Notes

* **Authentication:** On the first run, you may need to manually log in to LinkedIn. After logging in, Selenium will reuse your session for subsequent scrapes.
* **Rate Limiting:** LinkedIn may block or limit requests if scraping is done too frequently. Add delays between requests to avoid being flagged.
* **Respect LinkedIn's Terms of Service:** Ensure that you are in compliance with LinkedIn’s terms of service and use this tool responsibly.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.
