# Как создать и использовать venv
```bash
python -m venv myenv  # Создаст папку `myenv` с окружением
```
Windows:

```bash
myenv\Scripts\activate  # Активация
```
Linux/macOS:

```bash
source myenv/bin/activate  # Активация
```
## Фиксируем зависимости (либы)

```bash
pip freeze > requirements.txt
```

В гит надо заливать без папки окружения!!!
т.е без myenv(если брать пример отсюда)

## после клона на другой пк

```bash
python -m venv myenv          # Создаем новое окружение
source myenv/bin/activate     # Активируем (Linux/macOS)
myenv\Scripts\activate        # Активируем (Windows)
pip install -r requirements.txt  # Ставим зависимости
```

# использование .gitignore
```txt
myenv/
.env
__pycache__/
```
# pipenv
```bash
pip install pipenv
pipenv install requests  # Установка библиотеки
pipenv shell            # Активация окружения
```
## удаление старого окружения и создание нового. В случае конфликта
```bash
Удалите старое окружение и создайте заново:

bash
rm -rf myenv  # Linux/macOS
rmdir /s /q myenv  # Windows
```