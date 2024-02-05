# django_tutorial

## Requisito
- Python e PIP
- Django

## Conceitos básicos
### Projeto
Lorem ipsum

### Apps
Lorem ipsum

### MVT
Lorem ipsum

## Comandos básicos
Para criar um projeto:
```shell
django-admin startproject <project_name> [<directory>]
```

Para criar um app dentro do projeto:
```shell
python manage.py startapp <app_name>
```

Para rodar o servidor:
```shell
python manage.py runserver [port or ip:port]
```
(Por padrão o ip é `127.0.0.1` a porta é `8000`)

Para atualizar banco de dados com modelos:
```shell
python manage.py makemigrations #Cria as "migrações"
python manage.py migrate #Aplica as "migrações no banco de dados
```

Entrar no shell do Django:
```shell
python manage.py shell
```

## Arquivos e diretórios