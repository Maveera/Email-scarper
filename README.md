# Code Overview:
Import Required Libraries: The code begins by importing necessary libraries, including BeautifulSoup, requests, deque (for managing URLs in a queue), urllib.parse (for parsing URLs), and re (for regular expressions).

User Input: It prompts the user to enter a target URL to start the scanning process.

Initialize Data Structures: The code initializes several data structures: urls (a deque to store URLs to be processed), scraped_urls (a set to keep track of processed URLs to avoid duplicates), and emails (a set to store extracted email addresses).

Scanning Loop: The main part of the code is a loop that iteratively processes URLs, extracts email addresses, and explores links within the domain. It is designed to stop after processing 100 URLs, as indicated by the count variable.

a. For each URL, it sends an HTTP GET request using requests.get().

b. If there's a MissingSchema or ConnectionError exception, the code continues to the next URL.

c. It extracts email addresses from the webpage's text using a regular expression and adds them to the emails set.

d. It parses the HTML content of the page using BeautifulSoup and searches for anchor tags <a> to find links.

e. It processes each link found in the webpage:

If the link starts with '/', it is treated as a relative path and combined with the base URL.
If the link does not start with 'http', it is considered a relative URL and is combined with the current path.
If the link is neither in urls nor in scraped_urls, it is added to urls for further exploration.
KeyboardInterrupt Handling: The code handles a KeyboardInterrupt (usually triggered by Ctrl+C) to gracefully exit the scanning process.

Email Address Output: Finally, the script prints the extracted email addresses.

# How to Use:
Ensure you have Python installed on your system, along with the required libraries (requests, BeautifulSoup, lxml).

Copy the code into a Python file (e.g., email_scraper.py).

Run the script in your terminal or command prompt.

When prompted, enter the target URL (e.g., "https://example.com") you want to start the scanning process from.

The script will begin scanning web pages within the domain and extract email addresses. It will stop after processing 100 URLs or when interrupted with Ctrl+C.

Once the scanning is complete, the script will print the extracted email addresses on the screen.

# Steps to Install:
1. git clone https://github.com/Maveera/Email-scarper.git
2. cd Email-scarper
3. Run the code : python3 Email-scarper.py
4. If Shows any error 
5. install needed libraries
6.pip install requests
7.pip install beautifulsoup4
8.pip install lxml 
9.If you see version information and other details, it means the library is installed. If you see an error or no information, it means the library is not installed, and you should use the pip install.
10. Run the code : python3 Email-scarper.py

# Happy Hacking !
