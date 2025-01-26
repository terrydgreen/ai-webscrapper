AI Web Scrapper
================
https://huggingface.co/spaces/khatri-indra/AI-Web-Scrapper 
(go to Chrome Driver page and download the driver for your version of Chrome)

import streamlit - Frontend
import selenium - Webscraper
import langchain - Used to call the Ollama LLM

Training Video:
https://www.youtube.com/watch?v=Oo8-nEuDBkk

Chrome Driver:
https://googlechromelabs.github.io/chrome-for-testing/#stable 

Bright Data (http://brightdata.com):
 Award-winning proxy networks, AI-powered web scrapers, and business-ready datasets for download.
 *Use them if you keep running into Captura or IP Blockers by your desired websites.

 
pip3 install selenium

CODE (Python & Selenium):

from selenium.webdriver import Remote, ChromeOptions
from selenium.webdriver.chromium.remote_connection import ChromiumRemoteConnection
from selenium.webdriver.common.by import By

AUTH = 'XXX'
SBR_WEBDRIVER = f'https://{AUTH}@brd.superproxy.io:9515'

def main():
    print('Connecting to Scraping Browser...')
    sbr_connection = ChromiumRemoteConnection(SBR_WEBDRIVER, 'goog', 'chrome')
    with Remote(sbr_connection, options=ChromeOptions()) as driver:
        print('Connected! Navigating...')
        driver.get('https://example.com')
        print('Taking page screenshot to file page.png')
        driver.get_screenshot_as_file('./page.png')
        print('Navigated! Scraping page content...')
        html = driver.page_source
        print(html)
if __name__ == '__main__':
  main()
