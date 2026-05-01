🤖 Agente de Automação de Fluxo de Trabalho (Trello com Python):

Este projeto foi desenvolvido através do desafio da plataforma DIO. O objetivo é criar um agente inteligente com Python que interage com a API do Trello para automatizar a criação e organização de tarefas.

📋 Funcionalidades: 

Conexão utilizando API Key e Token.

Criação de Tarefas:

Automação para gerar cartões no Trello.

Gestão de Ambiente:

Configuração adaptada para rodar via Google Colab, utilizando a gestão de chave de segredos para proteção de chaves.

Tratamento de Erros: 

Sistema de verificação da conexão e validação de IDs de lista.

🛠️ Tecnologias UtilizadasLinguagem: Python 3.

Para comunicação com a API REST do Trello.google.colab: 

Para gerenciamento de credenciais em ambiente de nuvem.Plataformas:Trello (Gestão de tarefas)Google Colab (Ambiente de execução)

🚀 Como Configurar

1. Preparação no Trello
Acesse o Trello Power-Ups Admin e crie um novo Power-Up para obter sua API Key;
Gere um Token de Acesso manual através do link de autorização na mesma página;
Crie um quadro e identifique o ID da Lista (adicionando .json ao final da URL do quadro no navegador)

2. Configuração no Google Colab

No menu lateral esquerdo do Colab (ícone de chave 🔑), adicione os seguintes segredos:
TRELLO_KEY: Sua API Key.TRELLO_TOKEN: Seu Token gerado.
Ative a opção "Notebook access" para ambos.

3. Execução

Execute as células do notebook para:
Instalar as dependências.
Configurar a função de comunicação.
Criar o seu primeiro card automatizado.


📂 Estrutura do Código Principal
pythonimport requests from google.colab import userdata

# Configuração de credenciais
API_KEY = userdata.get('TRELLO_KEY')
TOKEN = userdata.get('TRELLO_TOKEN')
ID_LISTA = "seu_id_de_24_caracteres"

# URL de comunicação
url = "https://trello.com"

# Envio de tarefa
response = requests.post(url, params={
    'key': API_KEY,
    'token': TOKEN,
    'idList': ID_LISTA,
    'name': 'Nova Tarefa Automatizada'
