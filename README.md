
# Quickstart de Projeto Django

## Criando o repositório para o Projeto

* Abra o terminal, navegue até a pasta que vai querer criar seu projeto, em Documentos, por exemplo.

* Já na pasta Documentos, digite:
```bash
mkdir <nome da nova pasta para o projeto>
```   
Digite sem as chaves.
Esse comando vai criar uma pasta com o nome que você der.
    
* Em seguida vamos entrar na pasta do projeto, com o comando:
```bash
cd <nome da pasta que você criou>
```    

## Criando Ambiente Virtual

#### Virtualenv do Python:
Dentro da pasta que ficará o projeto, precisamos criar um ambiente virtual, vai ser nossa **virtualenv do python**.

Antes de tudo, você precisa se certificar de já ter o Python instalado na sua máquina. E também o pip, gerenciador 
de pacotes do Python. Com o Python e o pip instalados, podemos iniciar a produção...

* A virtualenv consegue criar diferentes ambientes na mesma máquina, evitando interferência de um projeto com outro.

* Utilizaremos o pip (gerenciador de pacotes do python) para instalar a virtualenv, com o comando:
```bash
$ sudo pip3 install virtualenv
```
Dependendo da sua versão do pip, pode ser que baste digitar o mesmo comando, trocando pip3 por pip.
Para saber qual a versão dele, digite:
```bash
pip --version
```
Caso não tenha efeito, tente:
```bash
pip3 --version
```
Com isso, ele instala o executável do python
e também os seus gerenciadores de pacote.

* Se necessário, atualiaze sua versão do pacote pip, com:
```bash
python -m pip install --upgrade pip
```

* Após instalar a virtualenv utilizando o gerenciador pip,
vamos agora criar um novo ambiente, executando o comando:
```bash
python3 -m virtualenv myenv
```
*myenv* foi o nome dado para o meu novo ambiente virtual, você pode dar o nome que quiser!
Depois só conferir esses arquivos, explorando a pasta criada.

* Com o ambiente virtual criado, precisamos ativá-lo:
```bash
source myenv/bin/activate
```
* Para desativar, utilize:
```bash
deactivate
```

## Instalando Django e dependências

* Para instalar Django, utilize o comando:
```bash
pip install django
```
* Para seguir com as instalações, vamos agora trabalhar diretamente
no editor, utilize o comando, para abrir o projeto com o Vs code:
```bash
code .
```
#### Iniciando o projeto

```bash
django-admin startproject <nome do projeto> .  
```
Ao digitar no bash, ignore < >, não esquecendo do ponto após espaço,
isso fará com que ele não crie um subdiretório.

* Em seguida criaremos nossa primeira aplicação:
```bash
python3 manage.py startapp <nome da aplicação>
```
Devemos sempre registrar as *app's* criadas no arquivo settings.py
do nosso projeto, dessa:

```bash
INSTALLED_APPS = [
    # apps django
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    
    # my apps
    'minhaApp.apps.MinhaAppConfig',
]
     
```     

* Pronto, neste momento você já pode rodar seu projeto:
```bash
python3 manage.py runserver
```

## 🎲 Criando nosso Data Base

* Com seus modelos  já criados, precisamos criar as migrações 
(gerar os SQLcomandos) com:
```bash
python3 manage.py makemigrations
```
* Em seguida nós executamos essas migrações (executamos os 
SQLcomandos) com:
```bash
python3 manage.py migrate
```
* Para ter acesso a tela de administração do Django,
precisamos criar um usuário:

```bash
python3 manage.py createsuperuser
```
