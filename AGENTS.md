# Instruções para agentes de IA

Este repositório contém **exclusivamente** código em **NTSL (Nelogica Trading System Language)**, a linguagem proprietária da Nelogica usada no Editor de Estratégias da plataforma **Profit**.

## Regra fundamental

- **Todo código escrito neste projeto deve ser NTSL válido**, sintaticamente e semanticamente compatível com o que o Profit compila e executa.
- **Nunca** usar outra linguagem de programação (Python, JavaScript, C#, Pine Script, MQL, etc.) para implementar indicadores, regras de coloração ou robôs — nem mesmo como "pseudocódigo", protótipo, ou exemplo ilustrativo dentro dos arquivos do projeto.
- **Nunca** inventar funções, palavras-chave ou estruturas que não existam na NTSL. Se uma função não existir no manual oficial, ou você não tiver certeza de que ela existe, isso deve ser sinalizado ao usuário — não inventada nem aproximada de outra linguagem.
- A referência de sintaxe, funções e estrutura é **sempre** o manual oficial em [`docs/ntsl/manual-ntsl.pdf`](docs/ntsl/manual-ntsl.pdf) (fonte: nelogica.com.br/manualntsl) e os artigos da central de ajuda da Nelogica (ajuda.nelogica.com.br). Consulte esse material antes de afirmar como uma função se comporta ou quais parâmetros aceita.

## Estrutura de arquivo obrigatória

Todo indicador, regra de coloração ou robô deve:
- Ser um arquivo `.ntsl` autocontido, seguindo a estrutura de blocos da NTSL (declaração de `input`s, variáveis, seções de cálculo/plotagem conforme o manual).
- Ter um cabeçalho em comentário no topo do arquivo com: nome, objetivo, parâmetros, ativos/timeframes testados e data da última alteração (ver READMEs de [`indicadores/`](indicadores/), [`cores/`](cores/) e [`robos/`](robos/)).
- Usar nomes de arquivo em snake_case, sem espaços ou acentos.

## O que evitar

- Não sugerir "adaptar" bibliotecas, frameworks ou lógicas de outras linguagens/plataformas (ex: TA-Lib, pandas, Pine Script) para NTSL — a tradução deve ser feita usando apenas os recursos nativos da linguagem, documentados no manual.
- Não criar arquivos de suporte em outras linguagens (scripts Python de apoio, testes automatizados fora do Profit, etc.) a menos que o usuário peça isso explicitamente e entenda que não faz parte do código que roda no Profit.
- Não assumir compatibilidade com versões antigas/diferentes da NTSL sem checar o manual — a linguagem recebe atualizações periódicas.

## Fluxo de trabalho

1. O código é escrito aqui, em NTSL.
2. O usuário leva o arquivo manualmente para o Profit para validar (simulador, replay, gráfico ao vivo).
3. Resultados e observações da validação são registrados em [`docs/`](docs/).
