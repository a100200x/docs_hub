
## Cоздать (на локальной) ключ ssh и сохранить его в акаунте гитхаба
https://github.com/settings/keys

инструкция - https://docs.github.com/ru/authentication/connecting-to-github-with-ssh

-- если используются несколько ключей для разных акаунтов, нужно дополнительно посмотреть, как настроить несколько через config и переключить акаунты 

## Подготовить локальный репозиторий

Клонировать любой репозиторий (найти и удалить в нем скрытую папку .git)

или 

Создать новую папку (на локальной) и открыть ее в VSCode

Инициализировать гит, добавить файлы и сделать коммит:
```
git init
git add .
git commit -m 'initial'
```

## Создать репозиторий в гитхабе

Например: https://github.com/a100200x/books_app.git

## Настроить ssh (на локальной)

- запустить агента на локальной 
```
eval "$(ssh-agent -s)"
```
- добавить ключ
```
ssh-add "C:/.../.../github_a100200x/.ssh/id_ed25519_github"
```

- подключиться к гитхабу
```
ssh -T a100200x.github.com
```

- связать с репозиторием
```
git remote add origin git@a100200x.github.com:a100200x/<...repo...>.git
git remote set-url origin git@a100200x.github.com:a100200x/<...repo...>.git
```
- проверить подключение 
```
git remote -v
```

## Сделать первый пуш
To push the current branch and set the remote as upstream, use
```
git push --set-upstream origin master
```
 
## В каждом новом терминале (в том чисте при повторном открытии проекта в VSCode)
```
eval "$(ssh-agent -s)"

ssh-add 'c:/.../.../github_a100200x/.ssh/id_ed25519_github'
``` 
```
git remote -v
```
## Чтобы запушить изменения в репозиторий, нужно выполнить команды:
```
 git add .
 git commit -m 'fix github/01'
 git push
 ```