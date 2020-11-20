# DjangoSIGE [![Build Status](https://travis-ci.org/thiagopena/djangoSIGE.svg?branch=master)](https://travis-ci.org/thiagopena/djangoSIGE)

Sistema Integrado de Gestão Empresarial baseado em Django

Projeto independente open-source desenvolvido em Python 3 no Windows, testado no GNU/Linux e Windows.


## Dependências

- [Python](https://www.python.org/downloads/) - Versão 3.5+
- [django](http://www.djangoproject.com) == 2.1.3
- [geraldo](https://github.com/thiagopena/geraldo) - Geração de PDF para pedidos de venda/compra
- [PySIGNFe](https://github.com/thiagopena/PySIGNFe) (Opcional) - Necessário para a geração de NF-e, NFC-e, comunicação com SEFAZ, geração do DANFE, etc.
- [apache2](https://www.apache.org/) (Opcional)
- [mod_wsgi](https://modwsgi.readthedocs.io/en/develop/) (Opcional)

## Minhas observações: Antes da instalação

Apanhei muito para instalar e rodar o aplicativo, então resolvi postar aqui os macetes antes da instalação padrão, siga os passos abaixo se for instalar no Linux Mint ou Ubuntu, fiz as instalações usando o Linux Mint 20 Cinnamon, no Windows 10 não consegui instalar devido a muitos erros e dependências, caso alguém tenha conseguido, utilize [Issues](https://github.com/nilton-medeiros/djangoSIGE/issues) ou via email nilton@sistrom.com.br.

1. Clonar do gitHub o projeto djangoSIGE para a pasta de projetos:

    ```bash
	    https://github.com/thiagopena/djangoSIGE.git
   ``` 
   ou
    ```bash
	    https://github.com/nilton-medeiros/djangoSIGE.git
    ```

2. No terminal do PyCharm ou no prompt, vá para a pasta raiz do projeto “djangoSIGE”, atualizar o  PIP:

    ```bash
	    python3 -m pip install -U pip –user
    ```
   
3. Instalar as  bibliotecas/pacotes abaixo:

    ```bash
	    sudo apt install libxml2
	    sudo apt install gcc
	    sudo apt install python3-dev
	    sudo apt install -y libxml2-dev libxslt1-dev zlib1g-dev python3-pip
    ```

4. Atualizar bibliotecas:

    ```bash
	    sudo apt update
    ```

5. Finalmente, instale as dependências:

    ```bash
	    pip3 install -r requirements.txt
    ```
   
6. Rodar o env_gen.py:
    
   ```bash
	    python3 contrib/env_gen.py
   ```

7. Migrate:

    ```bash
	    python3 manage.py migrate
    ```

8. Criar o super usuário:

    ```bash
	    python3 manage.py createsuperuser
    ```

9. O grande final:

    ```bash
	    python3 manage.py runserver
    ```
   
10. Execute no localhost:

    ```bash   
     http://127.0.0.1:8000/login/
    ```   
    
Segue abaixo a instalação original, se até aqui você conseguiu executar sem problemas o djangoSIGE então não é preciso rodar os comandos abaixo, porem leia atentamente as recomendações do Thiago.  


## Instalação (original):

1. Instalar dependências:

    ```bash
    pip install -r requirements.txt
    ```

2. Edite o conteúdo do arquivo **djangosige/configs/configs.py**

3. Gere um `.env` local

    ```bash
    python contrib/env_gen.py
    ```


4. Sincronize a base de dados:

    ```bash
    python manage.py migrate
    ```

5. Crie um usuário (Administrador do sistema):

    ```bash
    python manage.py createsuperuser
    ```

6. Teste a instalação carregando o servidor de desenvolvimento (http://localhost:8000 no navegador):

    ```bash
    python manage.py runserver
    ```

## Implementações

- Cadastro de produtos, clientes, empresas, fornecedores e transportadoras
- Login/Logout
- Criação de perfil para cada usuário.
- Definição de permissões para usuários.
- Criação e geração de PDF para orçamentos e pedidos de compra/venda
- Módulo financeiro (Plano de Contas, Fluxo de Caixa e Lançamentos)
- Módulo para controle de estoque
- Módulo fiscal:
    - Geração e armazenamento de notas fiscais
    - Validação do XML de NF-e/NFC-es
    - Emissão, download, consulta e cancelamento de NF-e/NFC-es **(Testar em ambiente de homologação)**
    - Comunicação com SEFAZ (Consulta de cadastro, inutilização de notas, manifestação do destinatário)
- Interface simples e em português

## Créditos

- [AdminBSBMaterialDesign](https://github.com/gurayyarar/AdminBSBMaterialDesign)
- [geraldo](https://github.com/marinho/geraldo)
- [jQuery-Mask-Plugin](https://igorescobar.github.io/jQuery-Mask-Plugin/)
- [DataTables](https://datatables.net/)
- [JQuery multiselect](http://loudev.com/)

## Ajuda

Para relatar bugs ou fazer perguntas utilize o [Issues](https://github.com/thiagopena/djangoSIGE/issues) ou via email thiagopena01@gmail.com

Como este é um projeto em desenvolvimento, qualquer feedback será bem-vindo.
