# Agente Severino: Marido de Aluguel Digital com Inteligência Artificial

Este script Python implementa um sistema de "Marido de Aluguel Digital" com quatro agentes de inteligência artificial, utilizando o framework ADK do Google e o modelo Gemini. O objetivo é ajudar usuários a encontrar soluções para problemas cotidianos e, se desejarem, indicar prestadores de serviço locais.

## Visão Geral

O sistema é composto por quatro agentes distintos que trabalham em conjunto:

1.  **Agente Buscador de Soluções:** Utiliza a pesquisa do Google para encontrar as soluções mais relevantes para o problema do usuário, priorizando fontes com alta autoridade e interação.
2.  **Agente Severino Resolve:** Explica de forma clara e acessível a melhor solução encontrada, atuando como um "Marido de Aluguel" digital amigável e respeitoso. Pergunta ao usuário se ele gostaria de buscar por prestadores de serviço.
3.  **Agente Severino Pergunta:** Após o usuário informar sua cidade e estado, este agente utiliza a pesquisa do Google para encontrar prestadores de serviço que possam solucionar o problema original.
4.  **Agente Severino Indica:** Analisa os prestadores de serviço encontrados, priorizando aqueles com mais avaliações e melhores notas. Apresenta ao usuário uma lista com o nome, endereço e telefone de até três profissionais.

## Como Funciona

1.  O script inicia solicitando ao usuário que digite o problema ou dificuldade que está enfrentando.
2.  O **Agente Buscador de Soluções** pesquisa na web por soluções relevantes para o problema.
3.  O **Agente Severino Resolve** analisa as soluções encontradas e apresenta a mais provável ao usuário, perguntando se ele deseja buscar por ajuda profissional.
4.  Se o usuário concordar, o script solicita a cidade e o estado onde ele reside.
5.  O **Agente Severino Pergunta** utiliza essas informações para buscar prestadores de serviço locais que possam resolver o problema.
6.  O **Agente Severino Indica** avalia os prestadores de serviço encontrados e apresenta os três melhores ao usuário.

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
2.  Execute a célula que inicia o sistema de agentes.
3.  Você será solicitado a digitar o seu problema. Insira sua dificuldade e pressione Enter.
4.  O Agente Severino apresentará uma solução.
5.  Você será perguntado se deseja buscar por prestadores de serviço. Responda "sim" ou "não".
6.  Se responder "sim", você será solicitado a informar sua cidade e estado.
7.  O Agente Severino então buscará e apresentará uma lista de até três prestadores de serviço relevantes na sua região.

## Boas Práticas Implementadas

* **Modularização:** O código é bem organizado em funções para cada agente, facilitando a leitura e manutenção.
* **Utilização do Framework ADK:** Aproveita os recursos do framework para criar e gerenciar agentes de forma estruturada.
* **Pesquisa Inteligente:** O Agente Buscador prioriza fontes de alta autoridade para garantir soluções mais confiáveis.
* **Comunicação Clara:** O Agente Severino Resolve se comunica de forma acessível e amigável com o usuário.
* **Foco na Relevância:** O Agente Indicador prioriza prestadores de serviço com base em avaliações para fornecer as melhores opções.
* **Tratamento de Entrada:** O script verifica se o usuário forneceu as informações necessárias em cada etapa.
* **Formatação de Saída:** A função `to_markdown` melhora a legibilidade das respostas no Colab.

## Próximos Passos e Melhorias Potenciais

* **Interface Web:** Desenvolver uma interface web (usando Flask, Django ou outra tecnologia) para tornar o agente acessível fora do ambiente Colab.
* **Persistência de Sessão:** Implementar um sistema de persistência de sessão mais robusto para lembrar o histórico de conversas.
* **Filtragem Mais Granular:** Adicionar mais opções de filtragem para a busca de prestadores de serviço (por exemplo, por tipo de serviço específico, faixa de preço).
* **Avaliações em Tempo Real:** Integrar dados de avaliação em tempo real, se possível.
* **Suporte a Múltiplos Idiomas:** Expandir o suporte para outros idiomas.
* **Integração com Mapas:** Adicionar links para o Google Maps para exibir a localização dos prestadores de serviço.

## Autor

Este script foi gerado tendo como referência o agente criado pela ALURA como exemplo para a 3ª edição da Imersão IA. O responsável pela concepção e adaptação se chama Léo Santos. 
