
## создать (на локальной) ключ ssh и сохранить его в акаунте гитхаба
https://github.com/settings/keys
инструкция - https://docs.github.com/ru/authentication/connecting-to-github-with-ssh

-- если несколько ключей, нужно дополнительно посмотреть, 
как настроить несколько через config и переключить акаунты 


## подготовить локальный репозиторий

клонировать несвой репозиторий (удалить скрытую папку .git)
или создать ную папку (на локальной)

инициализировать гит, добавть файлы и закоммитить их:
'''
git init
git add .
git commit -m 'initial'
'''

## создать репозиторий в гитхабе

например https://github.com/a100200x/books_app.git


## создать (на локальной) ключ ssh и сохранить его в акаунте гитхаба
https://github.com/settings/keys
инструкция - https://docs.github.com/ru/authentication/connecting-to-github-with-ssh


## настроить ssh (на локальной)

-активировать агента на локальной 
eval "$(ssh-agent -s)"

- добавить ключ
ssh-add "C:/.../.../github_a100200x/.ssh/id_ed25519_github"

- подключиться к гитхабу
ssh -T a100200x.github.com

- связать с репозиторием
git remote set-url origin git@a100200x.github.com:a100200x/books_app.git

- проверить подключение 
git remote -v

## сделать первый пуш
To push the current branch and set the remote as upstream, use
'''
git push --set-upstream origin master
'''
 