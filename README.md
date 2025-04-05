# 🧠 Análise de Sentimentos com Gemini API

Este projeto demonstra como utilizar a API Gemini (modelo generativo da Google) para analisar sentimentos em avaliações de hotéis escritas em português. O foco da análise está em identificar o sentimento em cinco aspectos principais:

- Localização
- Limpeza
- Atendimento
- Café da manhã
- Quarto

## 🔍 Como funciona

1. As avaliações são lidas a partir de um arquivo de texto (`review_hoteis_portugues.txt`).
2. Cada review é enviado à API Gemini com um prompt que pede a classificação de sentimentos por aspecto.
3. A resposta (em JSON) é tratada, limpa e convertida para um DataFrame.
4. O resultado final é estruturado e pode ser utilizado para relatórios ou visualizações.

## 🧰 Ferramentas e Tecnologias

- **Python 3**
- **Google Generative AI (gemini-1.5-flash)**
- **Pandas** – manipulação de dados
- **Regex** – limpeza de resposta JSON
- **JSON** – estrutura de retorno
- **time.sleep** – controle de chamadas à API

## 📂 Estrutura do Projeto

- `analise_sentimentos.ipynb`: notebook principal com todo o fluxo de análise
- `review_hoteis_portugues.txt`: arquivo com os reviews de entrada
- `README.md`: documentação do projeto

## ⚠️ Observações

- A chave da API Gemini não deve ser compartilhada publicamente. Substitua por uma variável de ambiente ou outro método seguro.

## 📌 Possíveis Melhorias

- Exportação dos resultados para CSV ou integração com dashboards
- Aplicação do mesmo fluxo a outros contextos (produtos, restaurantes, etc.)
- Uso de modelos open-source para evitar dependência de APIs

