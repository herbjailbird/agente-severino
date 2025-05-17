# Agente Severino: Marido de Aluguel Digital com Inteligência Artificial

 ```
    ![Imagem do Projeto](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgaXi1jk5XKKgbiZWDrucB7XEIdeh7yb9OfSpdHDHHlzh4UWzet-9P1ITLgf-G2zmQwQTYWEf3kXNHSutda0n2ChkdrfewmW_ZeAt4tzRO8pT0CP6-N-3maMNcGFD9jaDttPttxs5HpNA7_3lYL8kvIONQU9sEyNkxsXo8W49M08qgqW_xG5HL9Zx7-tKq0/s320/severino.png)
    ```

Este script Python implementa um sistema de "Marido de Aluguel Digital" com quatro agentes de inteligência artificial, utilizando o framework ADK do Google e o modelo Gemini. Além da lógica dos agentes, esta versão inclui uma interface de usuário básica construída com HTML e JavaScript, renderizada diretamente no Google Colab para uma interação mais visual.

## Visão Geral

O sistema é composto por quatro agentes distintos que trabalham em conjunto para ajudar usuários com problemas cotidianos e, opcionalmente, encontrar prestadores de serviço locais:

1.  **Agente Buscador de Soluções:** Utiliza a pesquisa do Google para encontrar as soluções mais relevantes para o problema do usuário, priorizando fontes com alta autoridade e interação.
2.  **Agente Severino Resolve:** Explica de forma clara e acessível a melhor solução encontrada, atuando como um "Marido de Aluguel" digital amigável e respeitoso. Pergunta ao usuário se ele gostaria de buscar por ajuda profissional.
3.  **Agente Severino Pergunta:** Após o usuário informar sua cidade e estado, este agente utiliza a pesquisa do Google para encontrar prestadores de serviço que possam solucionar o problema original.
4.  **Agente Severino Indica:** Analisa os prestadores de serviço encontrados, priorizando aqueles com mais avaliações e melhores notas. Apresenta ao usuário uma lista com o nome, endereço e telefone de até três profissionais.

A principal novidade desta versão é a inclusão de uma interface HTML interativa, permitindo que o usuário insira o problema, a cidade e o estado através de campos de texto e um botão. Os resultados dos agentes são exibidos abaixo da interface.

## Como Funciona

1.  O script define funções para cada um dos quatro agentes, cada um com uma responsabilidade específica no processo de resolução de problemas e busca por ajuda profissional.
2.  Uma interface de usuário básica é construída usando HTML e estilos CSS, incorporada diretamente no Colab através da função `display(HTML(...))`.
3.  A interface apresenta campos de texto para o usuário inserir seu problema, cidade e estado, além de um botão "Executar Agentes".
4.  Ao executar a célula contendo o código, a interface HTML é renderizada no Colab.
5.  O script Python subsequente (após a seção da interface HTML) utiliza a função `input()` para obter os valores do problema, cidade e estado diretamente do *prompt interativo do Colab* (abaixo da célula de código), e não diretamente dos campos da interface HTML renderizada.
6.  Os agentes são executados em sequência, utilizando as informações fornecidas pelo usuário através do `input()`.
7.  Os resultados de cada agente são formatados em Markdown e exibidos na saída do Colab usando `display(to_markdown(...))`.

**Observação Importante:** A interação da interface HTML (campos de texto e botão) com o backend Python (a execução dos agentes) nesta configuração do Colab é limitada. O JavaScript na interface HTML serve principalmente para exibir mensagens básicas na área de saída da interface. A *execução real* dos agentes e a obtenção dos dados do usuário ainda dependem das chamadas `input()` no código Python que segue a definição da interface HTML. Para uma interação totalmente dinâmica entre a interface HTML e o backend Python no Colab, seria necessário o uso de ferramentas como `ipywidgets`.

## Pré-requisitos

* **Google Colab:** Este script foi desenvolvido para ser executado no Google Colaboratory.
* **Chave de API do Google Gemini:** Você precisará obter e configurar uma chave de API do Google Gemini e armazená-la secretamente usando o recurso `userdata` do Google Colab.
* **Framework ADK do Google:** O framework é instalado automaticamente durante a execução do script utilizando `!pip install -q google-adk`.
* **Biblioteca `google-genai`:** A biblioteca é instalada automaticamente durante a execução do script utilizando `%pip -q install google-genai`.

## Configuração

1.  **Obtenha uma chave de API do Google Gemini:** Siga as instruções na documentação do Google AI para criar uma chave de API.
2.  **Armazene a chave de API no Google Colab:**
    * No painel lateral do Colab, clique no ícone de chave (Secrets).
    * Clique em "+ Adicionar um segredo".
    * No campo "Nome", digite `GOOGLE_API_KEY`.
    * No campo "Valor", cole sua chave de API do Google Gemini.
    * Clique em "Salvar".
3.  **Execute as células do código no Google Colab:** O script irá configurar as variáveis de ambiente e inicializar os clientes necessários.

## Utilização

1.  Execute a primeira célula do script para instalar as dependências e configurar a chave de API.
2.  Execute a célula que define a interface HTML. Você verá a interface renderizada na saída da célula.
3.  Execute a célula que contém a lógica principal dos agentes (abaixo da definição da interface HTML).
4.  Você será solicitado a digitar o seu problema, cidade e estado no *prompt interativo do Colab* (abaixo da célula de código). Insira as informações e pressione Enter após cada solicitação.
5.  O Agente Severino apresentará a solução e, se aplicável, a lista de prestadores de serviço na saída do Colab, formatada em Markdown. A área de "Resultados" na interface HTML exibirá mensagens básicas do JavaScript, mas a saída detalhada dos agentes estará na saída padrão do Colab.

## Interface

A interface HTML renderizada no Colab inclui:

* Um título "Agente Severino".
* A imagem do Robo Marido de Aluguel:

    ```
    ![Imagem do Projeto](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgaXi1jk5XKKgbiZWDrucB7XEIdeh7yb9OfSpdHDHHlzh4UWzet-9P1ITLgf-G2zmQwQTYWEf3kXNHSutda0n2ChkdrfewmW_ZeAt4tzRO8pT0CP6-N-3maMNcGFD9jaDttPttxs5HpNA7_3lYL8kvIONQU9sEyNkxsXo8W49M08qgqW_xG5HL9Zx7-tKq0/s320/severino.png)
    ```

* Campos de texto para inserir o problema, a cidade e o estado.
* Um botão "Executar Agentes".
* Uma área de "Resultados" onde mensagens básicas do JavaScript são exibidas.

## Boas Práticas Implementadas

* **Modularização:** O código é bem organizado em funções para cada agente.
* **Utilização do Framework ADK:** Aproveita os recursos do framework para criar e gerenciar agentes.
* **Pesquisa Inteligente:** O Agente Buscador prioriza fontes de alta autoridade.
* **Comunicação Clara:** O Agente Severino Resolve se comunica de forma acessível.
* **Foco na Relevância:** O Agente Indicador prioriza prestadores com base em avaliações.
* **Interface de Usuário Básica:** Introduz uma interface visual para facilitar a interação no Colab.
* **Estilização:** A interface HTML é estilizada com CSS para melhor apresentação.

## Próximos Passos e Melhorias Potenciais

* **Integração Dinâmica com `ipywidgets`:** Utilizar a biblioteca `ipywidgets` para criar campos de entrada e áreas de saída que interajam dinamicamente com o código Python, atualizando a interface sem depender do prompt interativo.
* **Backend Web Real:** Para uma aplicação web completa fora do Colab, seria necessário um backend web (Flask, Django) para servir a interface HTML e processar as requisições do usuário.
* **Persistência de Sessão:** Implementar um sistema de persistência de sessão mais robusto.
* **Filtragem Avançada:** Adicionar mais opções de filtragem para a busca de prestadores de serviço.
* **Avaliações em Tempo Real e Mapas:** Integrar dados de avaliação em tempo real e links para mapas.
* **Suporte a Múltiplos Idiomas.**

## Autor

Este script foi gerado tendo como referência o agente criado pela ALURA como exemplo para a 3ª edição da Imersão IA. O responsável pela concepção e adaptação se chama Léo Santos. 
