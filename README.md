# Consumo e peso dos carros

Publicação de teste do trama (#14); pode ser apagada.

- **Autores:** Josiah Carberry (https://orcid.org/0000-0002-1825-0097)
- **Versão:** 0.1.0
- **Licença:** CC-BY-4.0 para o conteúdo; MIT para o código (ver `LICENSE`).

## Como citar

Josiah Carberry (2026). Consumo e peso dos carros. Versão 0.1.0. trama-teste-publicar.

O arquivo `CITATION.cff` traz a mesma citação em formato de máquina.

## O que há aqui

Um pacote [RO-Crate](https://w3id.org/ro/crate/1.1): `ro-crate-metadata.json` descreve cada arquivo, com tamanho e sha256.

- `itens/ler/` — Tabela (tabela): dados.csv
- `itens/disp/` — Figura (figura): figura.png
- `itens/lm/` — Regressão linear (modelo): modelo.rds, motor.rds, web.json

- `flow.json` — o fluxo do [trama](https://github.com/uaipedro/trama) que gerou tudo.
- `dados-entrada.json` — os dados que o fluxo lê e que não vieram junto.
- `ambiente.json` — versões de R, do trama, das coleções e dos pacotes.
- `index.qmd` — a página (Quarto com a extensão quarto-live, versão fixada em `_extensions/`).

Os modelos vêm reduzidos: só o que prevê, sem os dados de treino. `modelo.rds` lê com o trama (`trama.models::tr_models_predict()`); `motor.rds` e a função `prever` de `web.json` preveem em R puro, como a página faz no navegador.

## Como reproduzir

1. Instale o trama e as coleções listadas em `ambiente.json` (r-universe: `install.packages("trama", repos = c("https://uaipedro.r-universe.dev", "https://cloud.r-project.org"))`).
2. Traga os dados de entrada para a pasta do projeto, com o mesmo nome e o mesmo sha256:

Nenhum: tudo o que o fluxo lê está no pacote.

3. Abra `flow.json` no editor (`trama::tr_app()`) e rode o fluxo.
