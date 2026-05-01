# Evaluation Suite

Testes para verificar se as skills encontram o que deveriam encontrar. Cada arquivo de teste contém problemas plantados intencionalmente — use-o como entrada para a skill correspondente e confira se o output identifica todos os problemas listados no final do arquivo.

## Como usar

1. Abra um arquivo de teste (ex. `test-grant-review.md`)
2. Invoque a skill correspondente com o conteúdo do arquivo
3. Compare o output com a seção `## Gabarito` ao final do arquivo
4. Uma skill está funcionando bem se encontra ≥ 80% dos problemas plantados sem gerar falsos positivos relevantes

## Arquivos

| Arquivo | Skill testada | Problemas plantados |
|---------|--------------|---------------------|
| `test-grant-review.md` | `/grant-review` | 8 problemas em 5 dimensões |
| `test-argumentation.md` | `/argumentation` | 6 problemas lógicos |
| `test-scientific-review.md` | `/scientific-review` | 7 problemas metodológicos |
| `test-style-clarity.md` | `/style-clarity` | 6 problemas de prosa |

## Critério de qualidade

- **Passa:** ≥ 6 de 8 problemas identificados, sem falsos positivos que distorçam o feedback
- **Atenção:** 4–5 de 8 problemas — skill está subestimando
- **Falha:** < 4 de 8 — skill precisa ser revisada
