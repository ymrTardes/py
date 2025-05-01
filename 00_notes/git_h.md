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

# слияние веток
Чтобы переключиться на другую ветку в Git, выполните следующие команды. Это безопасно, если у вас нет незакоммиченных изменений.
1. Проверьте текущие ветки
bash

git branch

2. Переключитесь на нужную ветку (например, py)
bash

git checkout py

Или (в новых версиях Git):
bash

git switch py

3. Если есть незакоммиченные изменения
Вариант A: Сохранить изменения и переключиться
bash

git stash          # Временно сохранить изменения
git checkout py    # Переключиться
git stash pop      # Вернуть изменения (уже в новой ветке)

Вариант B: Отменить изменения (осторожно!)
bash

git reset --hard   # Удалить все незакоммиченные изменения
git checkout py

4. Обновите ветку (если она уже существует)

После переключения подтяните свежие изменения из удалённой ветки:
bash

git pull origin py

## Чтобы объединить ваши ветки (например, ветка_друга и ваша_ветка) в одну (обычно main или master), используйте мерж (merge) или ребейз (rebase). Вот как это сделать правильно:
1. Сначала синхронизируйтесь с основной веткой

Перед слиянием убедитесь, что ваши ветки обновлены:
bash

# Переключиться в основную ветку (main/master)
git checkout main

# Подтянуть свежие изменения с удалённого репозитория
git pull origin main

2. Вариант A: Мерж (простое слияние)
Если вы хотите сохранить историю коммитов каждого:
bash

# Переключиться в вашу ветку
git checkout ваша_ветка

# Слить основную ветку в вашу (чтобы проверить конфликты)
git merge main

# Исправить конфликты (если они есть), затем:
git add .
git commit -m "Merge main into ваша_ветка"

# Теперь слить вашу ветку в main
git checkout main
git merge ваша_ветка

# Запушить изменения
git push origin main

Затем ваш друг делает то же самое:
bash

git checkout ветка_друга
git merge main
# Исправляет конфликты → коммитит → мержит в main → пушит.

bash

# Вернуться в свою ветку и обновить её
git checkout ваша_ветка
git merge main  # Чтобы синхронизировать

# То же самое делает ваш друг
