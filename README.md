## График зависимостей

**Описание**
Данная программа строит граф зависимостей указанного пакета на основе файла package-lock.json. Она позволяет визуализировать
зависимости пакетов, используя библиотеку Graphviz, и сохраняет результат в формате DOT.

**Использование:**
python main.py <имя_пакета> <путь_к_package_lock> <путь_для_сохранения> <глубина>

**Аргументы:**
<имя_пакета> — имя целевого пакета, для которого нужно построить граф зависимостей.
<путь_к_package_lock> — путь к файлу package-lock.json.
<путь_для_сохранения> — путь, по которому будет сохранён файл графа (без расширения).
<глубина> — максимальная глубина, до которой будут отображены зависимости.

**Пример:**
python main.py lodash ./package-lock.json ./dependency_graph 3
Этот пример создаст граф зависимостей пакета lodash с глубиной 3 и сохранит его в файл dependency_graph.dot.

**Установка и требования:**
Нам необходим graphviz
pip install graphviz

**Принцип работы:**
Программа считывает файл package-lock.json и проверяет его корректность.
Ищет информацию о пакете в разделе packages.
Рекурсивно проходит по зависимостям пакета и добавляет их в граф, учитывая заданное ограничение по глубине.
Сохраняет результат в формате DOT в указанное пользователем

**Пример работы:**
![Alt text](https://github.com/diedfck/dependencies-graph/blob/main/1.PNG)

#Запустим программу запросом: >py main.py @babel/core ./package-lock.json ./output.dot 4

![Alt text](https://github.com/diedfck/dependencies-graph/blob/main/2.PNG)
