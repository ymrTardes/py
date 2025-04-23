* Убрать GUI GIT
git config --global credential.helper store
git config --global --unset credential.helpermanager-core
git config --global --unset credential.helpermanager

* Сохранять учетные данные
git config --global credential.helper store

* Инициализация репозетория
git init

* Клонировать репозеторий
git clone https://github.com/ТВОЙ_ЛОГИН/ИМЯ_РЕПО.git
cd ИМЯ_РЕПО

* запись в изменений в файл
mkdir 00_notes 01_basics 02_conditions_loops 10_mini_projects
echo "# Мой путь изучения Python" > 00_notes/start.md


* сохранить созданные файлы, коммит и пуш
git add .
git commit -m "БЛА БЛА"
git push origin master

* проверка статуса репо
git status

* история коммитов с изменениями 
git log -p (подробно флаг -p)

* добавить папку в список доверенных репорзиториев
git config --global --add safe.directory "C:/Users/user/Documents/py"
* список доверенных репо
git config --global --get-all safe.directory
