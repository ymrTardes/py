* Убрать GUI GIT

```
git config --global credential.helper store
git config --global --unset credential.helpermanager-core
git config --global --unset credential.helpermanager
```

* Сохранять учетные данные

```
git config --global credential.helper store
```

* Задать аккаунт по умолчанию
```  
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

* Инициализация репозетория

```
git init
```

* Клонировать репозеторий

```
git clone https://github.com/ТВОЙ_ЛОГИН/ИМЯ_РЕПО.git
cd ИМЯ_РЕПО
```

* запись в изменений в файл

```
mkdir 00_notes 01_basics 02_conditions_loops 10_mini_projects
echo "# Мой путь изучения Python" > 00_notes/start.md
```

* сохранить созданные файлы, коммит и пуш

```
git add .
git commit -m "БЛА БЛА"
git push origin master
```

* можно git add и git cpmmit объеденить в:

```
git commit -a -m "bla bla"
```

* проверка статуса репо

```
git status
```

* история коммитов с изменениями

```
git log -p (подробно флаг -p)
```

* добавить папку в список доверенных репорзиториев

```
git config --global --add safe.directory "C:/Users/user/Documents/py"
```

* список доверенных репо

```
git config --global --get-all safe.directory
```
### Шаги для создания репозитория через терминал:
1. Установите GitHub CLI
   - Если он ещё не установлен, скачайте его [отсюда](https://cli.github.com/) и установите.
   - После установки проверьте доступность команды:
    
```Bash
     gh --version
```     
2. Выполните авторизацию
   - Введите команду:
    
```Bash
     gh auth login
```   
   - Выберите способ авторизации (через браузер или токен доступа).
   - Авторизуйтесь, чтобы связать GitHub CLI со своим аккаунтом.

3. Инициализируйте локальный репозиторий
   - Если вы ещё не сделали это, запустите:
    
```Bash
     git init
```     
1. Создайте удалённый репозиторий
   - Введите команду:
    
```Bash
     gh repo create имя_репозитория --public
```     
     Опции:
     - --public — сделать репозиторий публичным.
     - --private — сделать репозиторий приватным.

5. Свяжите локальный репозиторий с удалённым
   GitHub CLI автоматически добавит удалённый репозиторий, но если нужно вручную, выполните:
  
```Bash
   git remote add origin https://github.com/ваш_пользователь/имя_репозитория.git
```  
6. Добавьте файлы и залейте их
   Выполните стандартные команды Git:
  
```Bash
   git add .
   git commit -m "Первый коммит"
   git push -u origin main
```
# использование .gitignore
```txt
myenv/
.env
__pycache__/
```
## удаление папки из репозетория ПРИМЕР:
### Для всех папок __pycache__ в проекте:
```bash
git rm -r --cached */__pycache__
```
### Или для конкретной папки:
```bash
git rm -r --cached path/to/__pycache__
```