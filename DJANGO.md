Documentação: inicializando um aplicativo django pronto para o deploy 

Passo 0: antes de clonar o repositorio, adicione um template de .gitignore padrão para Python 

Passo 1: vamos criar o nosso ambiente virtual: 

- python3 -m venv venv

- source venv/bin/activate

Passo 2: adicione o arquivo requirements.txt a raiz do projeto com suas dependencias, depois execute dentro do venv: 

- pip install -r requirements.txt  

Passo 3: Adicione uma pasta app a raiz do projeto 

Passo 4: Vamos criar nosso projeto através de:

- django-admin startproject app . 

Passo 5: deve aparecer diversos arquivos, como settings.py, manage.py, urls.py, etc. Agora, para testar se esta tudo funcionando, digite: 

- python manage.py runserver

No endereço http://127.0.0.1:8000/ - aqui deve aparecer o foguetinho do django. 

Passo 6: Vamos criar nosso django app CORE agora através desse comando: 

- python manage.py startapp core

Passo 7: em settings.py, em INSTALLED APPS, adicione: 

- 'core',

Passo 8: mude, em settings.py, ALLOWED HOSTS para ALLOWED_HOSTS = ['*']

Passo 9: mude, em settings.py:

- STATIC_URL = '/static/'
- MEDIA_URL = '/media/'

Passo 10: mude, em settings.py:

- DATABASES = {
    'default': dj_database_url.parse(os.environ.get('DATABASE_URL'))
}

Passo 11: adicione, em urls.py:

- urlpatterns += staticfiles_urlpatterns()

Passo 12: adicione, em settings.py: 

- import os
- import dj_database_url

Passo 13: digite no terminal: 

- export DATABASE_URL=(aqui vai o link EXTERNO da sua base de dados postgre do Render)

Passo 14: digite no terminal: 

- python manage.py migrate 

Pronto! Agora consulte RENDER.md para prosseguir com o DEPLOY. 

Suas mudanças locais deve ser rodadas com o comando: 

python manage.py runserver 

Suas mudanças em produção ja vão via auto-deploy no render.com. 
