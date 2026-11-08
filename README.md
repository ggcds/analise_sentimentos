# Aspect-Based Sentiment Analysis with Gemini

Uses the Google Gemini API to analyze hotel reviews written in Portuguese, classifying the sentiment for five aspects:

- Location (*localização*)
- Cleanliness (*limpeza*)
- Service (*atendimento*)
- Breakfast (*café da manhã*)
- Room (*quarto*)

Each aspect is labeled as `muito negativo`, `negativo`, `neutro`, `positivo` or `muito positivo`. Aspects not mentioned in a review default to `neutro`.

## How it works

1. Reviews are read from `review_hoteis_portugues.txt` (one per line).
2. Each review is sent to Gemini (`gemini-1.5-flash`) with a prompt asking for a JSON classification per aspect.
3. The response is cleaned (markdown fences removed with regex), parsed and loaded into a pandas DataFrame.
4. Sentiment counts per aspect are aggregated and saved to `contagem_aspectos.csv`.

`time.sleep` is used between calls to respect API rate limits.

## Project structure

```
.
├── analise_sentimentos.ipynb      # Full analysis flow
├── review_hoteis_portugues.txt    # Input reviews
├── requirements.txt
├── LICENSE
└── README.md
```

## Getting started

```bash
git clone https://github.com/ggcds/analise_sentimentos.git
cd analise_sentimentos
pip install -r requirements.txt
jupyter notebook analise_sentimentos.ipynb
```

Get an API key at [Google AI Studio](https://aistudio.google.com/apikey) and set it in the notebook. **Never commit your key**; prefer an environment variable, e.g. `os.environ["GEMINI_API_KEY"]`.

Note: `gemini-1.5-flash` may be retired by Google; if calls fail, switch to a currently available Gemini model in the notebook.

## Possible improvements

- Export results to dashboards
- Apply the same flow to other domains (products, restaurants)
- Use open-source models to avoid API dependency

## Author

**Guilherme Barros Caldas**

## License

[MIT](LICENSE)
