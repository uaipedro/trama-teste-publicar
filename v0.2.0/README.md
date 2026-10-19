# Consumo e peso

Teste da convergência.

- **Autores:** Josiah Carberry (https://orcid.org/0000-0002-1825-0097); Ana Lima
- **Versão:** 0.2.0
- **Licença:** CC-BY-4.0 para o conteúdo; MIT para o código (ver `LICENSE`).

## Como citar

Josiah Carberry; Ana Lima (2026). Consumo e peso. Versão 0.2.0. https://github.com/uaipedro/trama-teste-publicar.

O arquivo `CITATION.cff` traz a mesma citação em formato de máquina.

## O que há aqui

Um pacote [RO-Crate](https://w3id.org/ro/crate/1.1): `ro-crate-metadata.json` descreve cada arquivo, com tamanho e sha256.

- `index.qmd` — o documento (Quarto), com o texto dos autores e os resultados do trama em blocos `::: {#trama-… .trama}`; `_extensions/` traz o modelo dele, com a versão fixada.
- `_trama/` — os resultados materializados que o documento mostra, um por pasta:

  - `_trama/dados/` — Dados de exemplo (tabela): dados.csv, tabela.md
  - `_trama/lm/` — Regressão linear (modelo): modelo.md, modelo.rds, motor.rds, preditor.qmd, web.json

- `flow.json` — o fluxo do [trama](https://github.com/uaipedro/trama) que gerou tudo; `fluxo.svg` é o diagrama.
- `dados-entrada.json` — os dados que o fluxo lê e que não vieram junto.
- `ambiente.json` — versões de R, do trama, das coleções e dos pacotes.

Os modelos vêm reduzidos: só o que prevê, sem os dados de treino. `modelo.rds` lê com o trama (`trama.models::tr_models_predict()`); `motor.rds` e a função `prever` de `web.json` preveem em R puro, como a página faz no navegador.

## Como reproduzir

1. Instale o trama e as coleções listadas em `ambiente.json` (r-universe: `install.packages("trama", repos = c("https://uaipedro.r-universe.dev", "https://cloud.r-project.org"))`).
2. Traga os dados de entrada para a pasta do projeto, com o mesmo nome e o mesmo sha256:

- `dados` (Dados de exemplo): 32 linhas, 12 colunas; sha256 `—`

3. Abra `flow.json` no editor (`trama::tr_app()`) e rode o fluxo.
