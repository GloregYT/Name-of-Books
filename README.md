import urllib.request

from bs4 import BeautifulSoup

url = "http://books.toscrape.com/"

response = urllib.request.urlopen(url)

html = response.read()

soup = BeautifulSoup(html, 'html.parser')

book_titles = [book.get_text() for book in soup.find_all('h3')]

print(book_titles)
