# Gaming Backlog - Imersão IA Alura

E aí, pessoal! 🚀 Esse é o projeto que desenvolvi na Imersão Alura em IA com o Google Gemini. O negócio ficou show e resolvi compartilhar com a comunidade!

## 💡 O Projeto

A ideia foi criar um jeito esperto de organizar o backlog de jogos. Sabe como é, a lista só cresce! Com o Gemini e a API do IGDB, o projeto faz isso:

* **Busca Inteligente:** Você digita o nome do jogo e o Gemini dá um gás na busca na API do IGDB.
* **Detalhes Completos:** Pega informações como desenvolvedora, lançamento, plataformas e capa do jogo.
* **Organização Top:** Integra tudo com o Google Sheets para organizar o backlog.
* **[Se tiver mais coisas com o Gemini, descreva!]**

## 🛠️ Tecnologias

Usei essas ferramentas:

* **Python:** Para fazer tudo funcionar. O Gemini me ajudou a elaborar o código Python de ponta a ponta.
* **Google Gemini:** Para turbinar a busca e me auxiliar na programação.
* **API do IGDB:** Para pegar os dados dos jogos.
* **gspread:** Para mexer com o Google Sheets.
* **requests:** Para as requisições na API.
* **[Outras bibliotecas]**
* **Google Sheets:** Para a organização.
* **Google Colab:** Para desenvolver e testar o projeto de forma prática, sem precisar instalar nada na minha máquina.
* **GitHub:** Para hospedar o projeto! 😉

## ⚙️ Como Rodar

Para testar o projeto, siga esses passos:

1.  **Clone o Repositório:**

    ```bash
    git clone [https://github.com/desktop/desktop/issues/18661](https://github.com/desktop/desktop/issues/18661)
    cd [nome do seu repositório]
    ```
2.  **Crie um Ambiente Virtual (Recomendado):**

    * **Opção 1: Usando o seu computador:**

        ```bash
        python -m venv venv
        source venv/bin/activate  # Linux/Mac
        venv\Scripts\activate  # Windows
        ```
    * **Opção 2: Usando o Google Colab:**

        * Abra um novo notebook no [Google Colab](https://colab.research.google.com/).
        * Você pode clonar o repositório diretamente no Colab usando o comando `!git clone https://github.com/desktop/desktop/issues/18661`.
        * Para instalar as dependências, use `!pip install -r requirements.txt`.
        * Lembre-se de que, no Colab, você precisará autenticar o acesso ao Google Sheets usando suas credenciais.

3.  **Instale as Dependências:**

    ```bash
    pip install -r requirements.txt
    ```
4.  **Configure o Google Sheets e a API do IGDB:**
    * **Google Sheets:**
        * Você vai precisar de um arquivo de credenciais JSON para acessar o Google Sheets. Siga os passos da [documentação do gspread](https://docs.gspread.com/oauth2) para criar e baixar esse arquivo.
        * Salve o arquivo como `credenciais.json` na raiz do seu projeto (NÃO COMPARTILHE!).
        * O arquivo `config.py` deve conter o caminho para o arquivo de credenciais e o ID da planilha do Google Sheets. Exemplo:
            ```python
            # config.py
            GOOGLE_SHEETS_CREDENTIALS_FILE = "/caminho/para/credenciais.json"  # Substitua pelo caminho real
            GOOGLE_SHEETS_ID = "ID_DA_SUA_PLANILHA"  # Substitua pelo ID da sua planilha
            ```
    * **API do IGDB (via Twitch):**
        * A API do IGDB utiliza a API da Twitch para autenticação. Portanto, você precisará ter uma conta na Twitch e registrar uma aplicação para obter as credenciais necessárias. Siga os passos detalhados na [documentação da API do IGDB](https://api-docs.igdb.com/#getting-started).
        * Você precisará obter um `Client ID` e um `Client Secret` da sua aplicação Twitch.
        * Essas informações também devem ser armazenadas no arquivo `config.py`:
            ```python
            # config.py
            IGDB_CLIENT_ID = "SEU_CLIENT_ID"
            IGDB_CLIENT_SECRET = "SEU_CLIENT_SECRET"
            ```
        * E acessadas no código principal:
            ```python
            # main.py
            from config import IGDB_CLIENT_ID, IGDB_CLIENT_SECRET, GOOGLE_SHEETS_CREDENTIALS_FILE, GOOGLE_SHEETS_ID
            ```

5.  **Use o Template da Planilha:**

    * Para facilitar a configuração do Google Sheets, disponibilizei um template da planilha que já está formatado para funcionar com o projeto. Você pode acessar e fazer uma cópia para a sua conta através deste link: [https://docs.google.com/spreadsheets/d/1J0ExYkPIAEg4tuQ5NdTbNlVamxn1paWujd3eovsnjaA/edit?usp=sharing&copy=true](https://docs.google.com/spreadsheets/d/1J0ExYkPIAEg4tuQ5NdTbNlVamxn1paWujd3eovsnjaA/edit?usp=sharing&copy=true)
    * Ao acessar o link, o Google Sheets perguntará se você deseja fazer uma cópia da planilha. Clique em "Fazer uma cópia".
    * Depois de criar a sua cópia, pegue o ID da planilha (a sequência de caracteres na URL entre `/d/` e `/edit`) e coloque-o na variável `GOOGLE_SHEETS_ID` dentro do arquivo `src/config.py`.

6.  **Rode o Script:**

    ```bash
    python src/main.py  # Ou o nome do seu script
    ```
7.  **Siga as Instruções:** O script vai te guiar para adicionar os jogos!

## 🗺️ Detalhes dos Arquivos do Projeto

Para facilitar a compreensão do projeto, aqui está um detalhamento dos arquivos principais:

* `README.md`: Este arquivo que você está lendo, com a descrição do projeto, como rodar, etc.
* `src/main.py`: O script principal que contém a lógica do projeto, incluindo a interação com a API do IGDB, o Google Gemini e o Google Sheets.
* `src/utils.py`: (Se existir) Arquivo para funções utilitárias que são usadas em `main.py`.
* `src/config.py`: Arquivo para armazenar informações de configuração, como tokens de API e o caminho para o arquivo de credenciais do Google Sheets. **Esse arquivo não deve ser compartilhado publicamente, especialmente se contiver informações confidenciais.**
* `requirements.txt`: Lista das bibliotecas Python necessárias para rodar o projeto.
* `credenciais.json`: **(Não incluído no repositório por motivos de segurança)** Arquivo de credenciais do Google Sheets.
* `data/`: (Se existir) Pasta para armazenar dados relacionados ao projeto.
* `notebooks/`: (Se existir) Pasta para arquivos Jupyter Notebooks usados no desenvolvimento.

## 🖼️ Imagens

Umas imagens valem mais que mil palavras:

* **Print do Script:** Mostrando o script rodando no terminal ou no Colab.
* ![image](https://github.com/user-attachments/assets/937cec14-2db6-4d0e-95c4-042a4d7227a8)

* **Print do Google Sheets:** A planilha com uns jogos adicionados.
* ![image](https://github.com/user-attachments/assets/39b27f11-2c1f-4ff6-8f96-74d8dda7d50c)


## 📝 Próximos Passos

Gostaria de ouvir suas ideias para melhorarmos esse projeto juntos! Se tiverem alguma sugestão, adição ou quiserem colaborar para deixar o Backlog ainda mais robusto e visualmente atraente, fiquem à vontade para contribuir!

## 🙏 Agradecimentos

Agradeço à Alura e à comunidade por essa imersão! Foi demais aprender e criar isso.

---

Feito com ❤️ por [Henry Santana/ZHenryZ/@s_henry_s - Discord]
