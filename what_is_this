import requests
from bs4 import BeautifulSoup

def fetch_articles(language='ru'):
    url = f'https://habr.com/{language}/all/'
    response = requests.get(url)
    soup = BeautifulSoup(response.text, 'html.parser')

    articles = soup.find_all('h2', class_='tm-title tm-title_h2')
    return [article.text.strip() for article in articles]

def main():
    while True:
        print("Выберите действие:")
        print("1. Прочитать статьи на русском")
        print("2. Прочитать статьи на английском")
        print("3. Выйти из программы")
        choice = input("Введите номер действия: ")

        if choice == '1':
            articles = fetch_articles('ru')
            for article in articles:
                print(article)
        elif choice == '2':
            articles = fetch_articles('en')
            for article in articles:
                print(article)
        elif choice == '3':
            print("Выход из программы.")
            break
        else:
            print("Неверный выбор. Попробуйте снова.")

if __name__ == "__main__":
    main()
