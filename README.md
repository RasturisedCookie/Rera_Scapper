## RERA Project Card Scraper

A robust Python script using Selenium to scrape project details directly from project cards on the Odisha RERA website, extracting key information (RERA No., Project Name, Promoter Name, Address) and saving it to a CSV file. The script is designed for reliability, avoiding navigation to detail pages and focusing only on the essential fields.

---

### **Features**

- Scrapes project data from the main listing page:  
  - RERA Registration Number  
  - Project Name  
  - Promoter Name  
  - Promoter Address
- Processes the first 6 project cards for demonstration.
- Saves results to `rera_projects_final.csv`.
- Uses robust Chrome driver configuration to minimize detection and maximize stability.
- Provides detailed console output for each step and summary statistics at the end.

---

## **Requirements**

- Python 3.7+
- Google Chrome browser
- [ChromeDriver](https://chromedriver.chromium.org/downloads) (ensure the path is set correctly in the script)
- The following Python packages:
  - selenium
  - webdriver-manager
  - beautifulsoup4
  - pandas

Install dependencies with:
```bash
pip install selenium webdriver-manager beautifulsoup4 pandas
```

---

## **Usage**

1. **Set up ChromeDriver**  
   Download and extract ChromeDriver. Update the `executable_path` in the script to point to your ChromeDriver location:
   ```python
   service = Service(executable_path=r"D:/chromedriver-win64/chromedriver.exe")
   ```

2. **Run the Script**  
   Execute the script in your terminal or Jupyter environment:
   ```bash
   python Untitled1.ipynb
   ```
   Or, if using Jupyter, run all cells.

3. **Output**  
   - The script will print extraction progress and summaries to the console.
   - The final data is saved as `rera_projects_final.csv` in the working directory.

---

## **Extracted Data Example**

| RERA Regd. No     | Project Name          | Promoter Name                                 | Promoter Address |
|-------------------|----------------------|-----------------------------------------------|------------------|
| RP/01/2025/01362  | Basanti Enclave      | M/S. NEELACHAL INFRA DEVELOPERS PVT. LTD      | Angul            |
| RP/19/2025/01361  | UDYAYEEN             | SHYAMCHAND BUILDERS PRIVATE LIMITED           | Khordha          |
| PS/28/2025        | BARSANA RESIDENCY-II | RITA PODDAR                                   | Sambalpur        |
| PS/7/2025         | KRISHNA MANOR PH-II  | KRISHNA PROPERTIES & DEVELOPERS PRIVATE LIMITED| Cuttack         |
| PS/19/2025        | BHAVYAVILLA          | SUNSHINE INFRATECH                            | Khordha          |
| RP/19/2025/01355  | MURALIDHARA HEIGHTS  | TRILOCHAN PROJECTS AND DEVELOPERS PVT. LTD    | Khordha          |

---

## **How It Works**

- Launches a Chrome browser with anti-detection settings.
- Loads the Odisha RERA projects listing page.
- Finds all project cards (`.project-card` CSS selector).
- For each card (up to 6):
  - Extracts text and parses for required fields using regex and string matching.
- Compiles results into a pandas DataFrame and saves to CSV.
- Prints a summary of extraction success.

---

## **Customization**

- **Number of Projects:**  
  Change `project_cards[:6]` to process more or fewer cards.
- **ChromeDriver Path:**  
  Update the `executable_path` as needed for your system.

---

## **Troubleshooting**

- If ChromeDriver version mismatch errors occur, download the version matching your Chrome browser.
- If no project cards are found, the website structure may have changed—check the selector `.project-card`.
- For package errors, ensure all dependencies are installed and restart your Python kernel if needed.

---

## **License**

MIT License.  
For educational and research use only.  
Not affiliated with or endorsed by Odisha RERA.

---

## **Acknowledgments**

- Odisha RERA for the publicly available data.
- Selenium and pandas open-source communities.

---

**Author:**  
Avishek Bhakta

April 2025
