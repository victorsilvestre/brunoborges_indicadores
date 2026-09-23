# Indicadores Bruno Borges

Projeto para criação, manutenção e implementação de indicadores, regras de coloração e robôs de trading em **NTSL** (Nelogica Trading System Language) para a plataforma **Profit**, da Nelogica.

## Estrutura

- [`indicadores/`](indicadores/) — Indicadores técnicos em NTSL.
- [`cores/`](cores/) — Regras de coloração em NTSL.
- [`robos/`](robos/) — Estratégias automatizadas (fase futura).
- [`docs/`](docs/) — Documentação, validações e decisões de design.

## Fluxo de trabalho

1. O código NTSL é escrito e versionado aqui.
2. O arquivo é levado manualmente para o Profit para validação (simulador, replay, gráfico ao vivo).
3. Resultados e observações da validação são registrados em `docs/`.

## Status

Fase atual: **indicadores e regras de coloração**. Robôs de trading ficam para uma etapa posterior.
