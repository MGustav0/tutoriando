# GitHub

Iniciando com o GitHub para armazenamento e versionamento de projetos.

## Create a new repository on the command line

1. git init
2. git add README.md
3. git commit -m "first commit"

## Pushing (enviar ao GitHub)

1. git remote add origin git@github.com:MGustav0/seu_repositorio.git
2. git push -u origin master

## Erros

Se você estiver editando arquivos e não estiver conseguindo enviar as atualizações, execute

´´´git checkout master´´´
´´´git pull origin master´´´

Caso ainda esteja dando erro:

´´´git push origin master --force´´´

**WARNING**: Use com cuidado, pois irá SOBRESCREVER o repositório remoto pelo seu local.
