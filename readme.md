# 🤖 BotFlix - Recomendações de Filmes com IA

![Animação da interface do BotFlix](./src/images/animação.gif)

Bem-vindo ao BotFlix! Uma aplicação inovadora que utiliza inteligência artificial para recomendar filmes com base no seu humor, em uma cena que você queira assistir ou em qualquer descrição que vier à sua mente. Diga adeus à rolagem infinita e deixe nossa IA encontrar o filme perfeito para você.

## 📜 Descrição

O BotFlix foi criado para resolver o eterno problema: "o que assistir?". Em vez de navegar por categorias genéricas, você pode simplesmente descrever o que sente ou o que gostaria de ver.

Por exemplo:
- "Estou me sentindo triste e queria um filme para chorar."
- "Um filme de ação com perseguições de carro alucinantes."
- "Quero ver uma comédia romântica que se passa em Nova York."

A aplicação envia sua descrição para uma IA, que interpreta seu pedido e busca os filmes mais relevantes em um banco de dados, exibindo os resultados de forma elegante e intuitiva.

## ✨ Funcionalidades

- **Busca por Sentimento**: Descreva seu humor e receba recomendações personalizadas.
- **Interface Moderna**: Design limpo e futurista, com tema escuro e animações sutis.
- **Resultados Dinâmicos**: Os filmes são exibidos em um grid com pôster, título, sinopse e avaliação.
- **Responsividade**: (Suposição baseada no CSS) A interface se adapta a diferentes tamanhos de tela.

## ⚙️ Como Funciona

A aplicação opera em um fluxo simples, porém poderoso, combinando o poder de uma API de IA com uma API de banco de dados de filmes.

1.  **Entrada do Usuário**: O usuário digita sua solicitação na área de texto principal.
2.  **Processamento com IA**: Ao clicar em "Buscar", o texto é enviado para uma API de Inteligência Artificial (como a **API do Gemini** ou **OpenAI**). A IA analisa o texto e gera uma lista com nomes de filmes que correspondem à descrição.
3.  **Busca de Detalhes**: A aplicação percorre a lista de nomes de filmes gerada pela IA. Para cada nome, ela faz uma consulta a uma API de filmes (como a **API do The Movie Database - TMDb**) para obter informações detalhadas, como pôster, sinopse, data de lançamento e avaliação.
4.  **Exibição dos Resultados**: As informações dos filmes são usadas para criar "cards" dinamicamente na interface, que são exibidos para o usuário no grid de resultados.

## 🛠️ Tecnologias Utilizadas

O projeto foi construído com tecnologias web modernas para garantir uma experiência de usuário fluida e uma base de código eficiente, utilizando um conjunto de tecnologias modernas para garantir performance e escalabilidade.

- **Frontend**:
  - **HTML5**: Estrutura semântica da página.
  - **CSS3**: Estilização avançada, layout com Flexbox, animações e design responsivo.
  - **JavaScript (Vanilla)**: Manipulação do DOM, lógica da aplicação e comunicação com as APIs (fetch).

- **APIs**:
  - **API de IA Generativa**: Essencial para interpretar a linguagem natural do usuário e sugerir filmes.
    - *Exemplos: Google Gemini API, OpenAI API.*
  - **API de Banco de Dados de Filmes**: Utilizada para buscar os metadados dos filmes recomendados pela IA.
    - *Exemplo: The Movie Database (TMDb) API.*

### Backend e Automação
*   **n8n.io**: Utilizamos o n8n como nossa ferramenta de automação de fluxos de trabalho (_workflow automation_). Ele é responsável por orquestrar tarefas em segundo plano, como a busca e sincronização de dados.
*   **API do TMDB (The Movie Database)**: Para obter todos os dados relacionados a filmes, séries e artistas (como pôsteres, sinopses, elenco e avaliações), integramos a aplicação com a API oficial do TMDB.

### Como o n8n e o TMDB funcionam juntos?

O fluxo de dados de filmes é gerenciado por um workflow no n8n. Periodicamente, ele executa as seguintes ações:
1.  **Busca dados** na API do TMDB para encontrar os filmes mais populares ou atualizações recentes.
2.  **Transforma e formata** esses dados para o padrão exigido pela nossa aplicação.
3.  **Armazena** as informações tratadas em nosso banco de dados, garantindo que o aplicativo principal tenha acesso rápido e consistente aos dados, sem a necessidade de consultar a API do TMDB a cada requisição do usuário.

## 🚀 Como Executar o Projeto

Para executar este projeto localmente, você precisará de chaves de API para os serviços de IA e de banco de dados de filmes.

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/seu-usuario/botflix.git
    cd botflix
    ```

2.  **Obtenha as chaves de API:**
    - Crie uma conta em uma plataforma de IA (como [Google AI Studio](https://aistudio.google.com/) para o Gemini) e obtenha sua chave de API.
    - Crie uma conta no [The Movie Database (TMDb)](https://www.themoviedb.org/signup) e solicite uma chave de API.

3.  **Configure as chaves no código:**
    - Abra o arquivo JavaScript principal (ex: `src/js/main.js`).
    - Insira suas chaves de API nas variáveis correspondentes.
    ```javascript
    const GEMINI_API_KEY = "SUA_CHAVE_API_GEMINI_AQUI";
    const TMDB_API_KEY = "SUA_CHAVE_API_TMDB_AQUI";
    ```

4.  **Abra o `index.html` no seu navegador:**
    - A maneira mais fácil é usar uma extensão como o "Live Server" no VS Code para evitar problemas com CORS ao fazer as requisições para as APIs.

---

*Projeto desenvolvido como parte de um estudo sobre integração de APIs e desenvolvimento frontend moderno.*


