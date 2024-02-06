# django_tutorial

## Conceitos básicos

### Projeto

É a aplicação como um todo. Dentro dele vão ficar as configurações, aplicações menores e todas as peças para fazer a tudo funcionar em conjunto.

### Apps

São partes menores, como módulos. Cada "app" tem uma responsabilidade específica e um projeto pode ter múltiplos apps. Ex: um site pode ter um app chamado "blog", que vai cuidar das postagens, autores etc.
Um mesmo app também pode ester presente em múltiplos projetos.

### MVT

- **Model**: São as estruturas/classes. Servem tanto para definir os campos como os métodos próprios. São usados também pelo banco de dados.

- **View**: É aqui onde as requisições web chegam e então uma resposta é devolvida. Essa resposta normalmente vai ser um template.

- **Template**: É onde a estrutura HTML é definida. Apesar disso, não são os arquivos criados aqui que são devolvidos para o cliente. Primeiro eles são interpretados pelo Django, que tem sua própria linguagem de template, e só então renderizados.

### Migrações

São a forma de passar para o banco de dados as modificações feitas nos modelos dos apps, como criação de um modelo ou campo novo.

### Painel administrativo

O Django já vem com um painel semi-pronto que permite administrar o conteúdo do projeto e de seus apps. Nele podemos criar, editar e excluir o conteúdo do banco de dados.

Normalmente será acessado em `http://127.0.0.1:8000/admin`.

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
python manage.py makemigrations # Cria as "migrações"
python manage.py migrate # Aplica as "migrações no banco de dados
```

Entrar no shell do Django (útil para testar modelos e métodos):
```shell
python manage.py shell
```

Criar superusuário para poder acessar painel administrativo:
```shell
python manage.py createsuperuser
```

## Arquivos e diretórios

- **manage.py**: Principal arquivo do projeto. É a partir dele que interagimos com o projeto Django, como iniciar um servidor, criar apps, trabalhar com bancos de dados, etc.

### Projeto

- **<project_name>/settings.py**: Contém as configurações do projeto Django, incluindo informações de banco de dados, idioma, fuso horário, apps instalados, entre outras configurações.

- **<project_name>/urls.py**: Define as rotas URL do projeto e as mapeia para as views correspondentes. As URLs dos apps podem ser incluídas aqui para manter o roteamento modular e organizado.

### App

- **<app_name>/apps.py**: Define a configuração do app Django, incluindo o nome do app e qualquer configuração específica do app. Funciona como o ponto de entrada para o app.

- **<app_name>/models.py**: Define os modelos do app, que são classes Python que descrevem os dados e comportamento do banco de dados. Cada modelo representa uma tabela no banco de dados.

- **<app_name>/urls.py**: Especifica as rotas URL dentro de um app específico, direcionando as requisições para as views adequadas.

- **<app_name>/views.py**: Contém as views do app, que processam as requisições e retornam respostas. A lógica do negócio é geralmente implementada aqui.

- **<app_name>/templates/**: Diretório que armazena os arquivos de template do app. Os templates definem a estrutura HTML das páginas web e podem incluir dados dinâmicos passados pelas views.

- **<app_name>/admin.py**: Permite registrar modelos do app no site administrativo do Django, facilitando a gestão de conteúdos do banco de dados através de uma interface gráfica.