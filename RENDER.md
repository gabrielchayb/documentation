Documentação completa do deploy no render.com

Passo 0: crie sua conta no render.com /faça login 

Passo 1: crie um novo serviço: POSTGRESQL 

Passo 2: coloque um nome, escolha qual instancia (pago ou gratuito), escolha uma região proxima a voce e crie sua database;

Passo 3: copie a EXTERNAL DATABASE URL e use no terminal do aplicativo django, via:

- - export DATABASE_URL=(aqui vai o link EXTERNO da sua base de dados postgre do Render)

Passo 4: Agora, crie um novo WEB SERVICE no render.com, conecte-se ao repositorio do github, escolha um nome (mesmo que o rep), uma regiao proxima

Passo 5: atenção, no campo "start command", coloque: gunicorn NOMEDOREPO.wsgi:application

Passo 6: Adicione as seguintes variaveis de ambiente: 

PYTHON_VERSION : 3.10.6
DATABASE_URL : INTERNAL DATABASE URL (copiada no postgresql criado pelo render)

pronto, agora é so criar o serviço que o deploy vai ser realizado automaticamente. 
