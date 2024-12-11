# DSA-lab4Lab 4: Bucket Sort, Counting Sort, and Web Scraping
Overview
In this lab, we dive into the following key topics:

Bucket Sort
A sorting algorithm that distributes elements into buckets and sorts them individually.
Counting Sort
A non-comparison-based sorting algorithm that sorts integers by counting their occurrences.
Web Scraping
Extracting data from websites using libraries like BeautifulSoup and Selenium.
Learning Outcomes
By the end of this lab, you will:

Understand and implement Bucket Sort and Counting Sort algorithms.
Gain insights into the time complexity and use cases of each sorting method.
Learn the basics of web scraping to extract structured data from websites.
Work with external libraries like requests, BeautifulSoup, or Selenium.
Structure
Part 1: Sorting Algorithms
Bucket Sort Implementation:
Write a function that partitions input data into buckets, sorts them, and combines the results.
Counting Sort Implementation:
Write a function that efficiently sorts an array of integers using a counting mechanism.
Part 2: Web Scraping
Learn how to:
Send HTTP requests to a webpage.
Parse HTML data to extract meaningful content (e.g., titles, prices, or reviews).
Handle pagination to scrape multiple pages.
Prerequisites
Ensure the following libraries are installed:

bash
Copy code
pip install requests beautifulsoup4 selenium pandas
Instructions
Part 1: Sorting Algorithms
Implement Bucket Sort and Counting Sort in Python.
Test the algorithms on randomly generated datasets.
Compare their performance on different input sizes.
Part 2: Web Scraping
Use requests or Selenium to fetch webpage data.
Parse the data with BeautifulSoup or other parsers.
Save the scraped data into a .csv file for analysis.
Example Code
Bucket Sort
python
Copy code
def bucket_sort(arr):
    max_value = max(arr)
    size = len(arr)
    buckets = [[] for _ in range(size)]
    
    for num in arr:
        index = int(num * size / (max_value + 1))
        buckets[index].append(num)
    
    for bucket in buckets:
        bucket.sort()
    
    sorted_arr = [num for bucket in buckets for num in bucket]
    return sorted_arr
Web Scraping with BeautifulSoup
python
Copy code
import requests
from bs4 import BeautifulSoup

url = "https://example.com"
response = requests.get(url)
soup = BeautifulSoup(response.content, "html.parser")

# Example: Extract all titles
titles = [tag.text for tag in soup.find_all("h2")]
print(titles)
Deliverables
Python scripts for Bucket Sort and Counting Sort.
A .csv file containing data scraped from a website.
A brief report analyzing the sorting performance and the scraping results.
