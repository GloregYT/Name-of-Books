# Name-of-Books

import urllib.request
from bs4 import BeautifulSoup

# URL для парсинга
url = "http://books.toscrape.com/"

# Получение содержимого страницы
response = urllib.request.urlopen(url)
html = response.read()

# Использование BeautifulSoup для парсинга HTML
soup = BeautifulSoup(html, 'html.parser')

# Извлечение названий книг
book_titles = [book.get_text() for book in soup.find_all('h3')]
print(book_titles)
