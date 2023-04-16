Итоговый проект по разделу «Автоматизация тестирования»

**Готовые тест-кейсы и баг-репорты [тут](https://docs.google.com/spreadsheets/d/1YGowteOqKqR1prQ2_wsXgLfDN4-_XzQ2tt0kazGbQi4/edit?usp=sharing)**

- Объект тестирования: [https://b2c.passport.rt.ru/](https://b2c.passport.rt.ru/)
- Требования у проекту: [Требования](https://lms.skillfactory.ru/assets/courseware/v1/f78e146f0eb3ace247a28b07e66467de/asset-v1:SkillFactory+INTQAP+2022+type@asset+block/%D0%A2%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_SSO_%D0%B4%D0%BB%D1%8F_%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_last.doc)

Заказчик передал вам следующее задание:

1. Протестировать [требования](https://lms.skillfactory.ru/assets/courseware/v1/f78e146f0eb3ace247a28b07e66467de/asset-v1:SkillFactory+INTQAP+2022+type@asset+block/%D0%A2%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_SSO_%D0%B4%D0%BB%D1%8F_%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_last.doc).

2. Разработать тест-кейсы (не менее 15). Необходимо применить несколько техник тест-дизайна.

3. Провести автоматизированное тестирование продукта (не менее 15 автотестов). 
   Заказчик ожидает по одному автотесту на каждый написанный тест-кейс. Оформите свой 
   набор автотестов в GitHub.

4. Оформить описание обнаруженных дефектов. 
   Во время обучения вы работали с разными сервисами и шаблонами, 
   используйте их для оформления тест-кейсов и обнаруженных дефектов. 
   Если дефекты не обнаружены, то подумайте и опишите 3 потенциально возможных дефекта 
   на данном ресурсе.


Для разработки тест-кейсов использованы методы "черного ящика", функционального тестирование, UX тестирование. 
Так же использованы техники тест дизайна : диаграмма состояний и переходов, классы эквивалентности, граничные значения и попарное тестирование.

Разработка проекта автотестирования выполнена по паттерну PageObject. Для разработки автотестов применялись библиотеки pytest, pytest-selenium. 
Использовались фикстуры, фикстуры параметризации, явные и неявные ожидания драйвером, различные способы описания локаторов (СSS_SELECTOR, XPATH, ID, CLASS_NAME, NAME). 
Проект разработан для операционной системы macOS и ей подобных.

Структура проекта:

Основная директория "28" содержит:
Требования_SSO_для_тестирования.docx - требования по проекту 
README.md - содержит информацию о проекте.
В корневом каталоге проекта содержатся:

Директория driver содержит:
chromedriver.exe -Драйвер для управления браузером Chrome

Директория page содержит:
auth_page.py - описание атрибутов и методов работы со страницей авторизации проекта.
base_page.py - описание атрибутов и методов работы с базовой страницей.
reg_page.py - описание атрибутов и методов работы со страницей регистрации проекта.
reset_page.py - описание атрибутов и методов работы со страницей восстановления пароля проекта.
locators.py - описание локаторов проекта.

Директория tests содержит:
test_auth_page.py - тесты страницы авторизации проекта.
test_reg_page.py - тесты страницы регистрации проекта.
test_reset_page.py - тесты страницы восстановления пароля проекта.
config.py - описание значений элементов страниц и переменных.
conftest.py - описание фикстур для проекта.
pytest.ini - файл конфигурации Pytest.

Директория venv содержит виртуальное окружение проекта.


Запуск тестов производится из терминала следующими командами:

1. Для тестов страницы авторизации:
python3 -m pytest -v --driver Chrome --driver-path /driver/chromedriver tests/test_auth_page.py 

2. Для тестов страницы регистрации:
python3 -m pytest -v --driver Chrome --driver-path /driver/chromedriver tests/test_reg_page.py

3. Для тестов страницы восстановления пароля:
python3 -m pytest -v --driver Chrome --driver-path /driver/chromedriver tests/test_reset_page.py

**Готовые тест-кейсы и баг-репорты [тут](https://docs.google.com/spreadsheets/d/1YGowteOqKqR1prQ2_wsXgLfDN4-_XzQ2tt0kazGbQi4/edit?usp=sharing)**

Прописанные тесты нестабильны, запускать следует в отображаемом графическом режиме chromedriver
Для включения драйвера в фоном режиме , в файле conftest.py расскоментировать параметр опций драйвера ("--headless")
