# Proofwright

**Um companheiro de escrita aumentado por IA para autores técnicos e científicos.**

Proofwright é um framework pessoal de escrita que combina sua expertise de domínio com um agente de IA para produzir argumentos mais sólidos, prosa mais limpa e trabalhos mais rigorosos. De posts no Medium a propostas FAPESP PIPE, de artigos científicos a relatórios técnicos, Proofwright te ajuda a escrever melhor, não no seu lugar.

> *"wright"* — artesão que constrói com as próprias mãos.
> *"proof"* — tanto o rigor da ciência quanto o ato de revisar com cuidado.

---

## Por que Proofwright?

Escrever conteúdo técnico e científico é exigente. Clareza argumentativa, precisão factual, solidez metodológica e consistência estilística — frequentemente tudo isso ao mesmo tempo, em formatos muito diferentes. A maioria das ferramentas de IA resolve o problema errado: elas escrevem por você. Proofwright parte de uma premissa diferente: você já sabe o que quer dizer, e o agente existe para te ajudar a dizer melhor.

**Este projeto é transparente por design.** Toda contribuição é visível, revisável e sua para aceitar ou rejeitar. Sem reescritas ocultas.

---

## O que faz

Proofwright fornece instruções de prompt reutilizáveis ("skills") organizadas em torno das principais atividades de escrita:

| Skill | Comando | Para quê |
|-------|---------|----------|
| Revisão PIPE integrada | `/pipe-review` | Revisão completa de proposta FAPESP PIPE na voz do próprio autor |
| Revisão de proposta | `/grant-review` | Avaliação FAPESP PIPE (7 dimensões), Fase 1 ou Fase 2 |
| Auditoria de argumentação | `/argumentation` | Estrutura lógica, afirmações fracas, lacunas de evidência |
| Revisão científica | `/scientific-review` | Metodologia, raciocínio estatístico, padrões disciplinares |
| Edição estrutural | `/structural-edit` | Organização, fluxo, transições, equilíbrio entre seções |
| Estilo e clareza | `/style-clarity` | Prosa, jargão, adequação ao público-alvo |
| Verificação factual | `/fact-check` | Afirmações sem suporte, estatísticas sem fonte |
| Referências | `/references` | Formatação e auditoria bibliográfica |
| Perfil de estilo | `/extract-author-style` | Extrai fingerprint estilométrica do corpus do autor |

---

## Voz do autor

O diretório `author_corpus/` contém textos de referência escritos pelo autor (posts, tese, artigos). Eles são usados para extrair um perfil estilométrico que as skills podem consultar para preservar a voz original durante a revisão.

**Configuração inicial (rode uma vez):**

```
/extract-author-style
```

Isso lê o corpus e gera `author_corpus/style_profile.md`. Revise e edite o perfil gerado como quiser. É um arquivo markdown simples e o ponto central de toda a consciência de voz do sistema.

**Uso:** Adicione `--preserve-voice` a qualquer skill compatível para ativar revisão com consciência de voz:

```
/style-clarity --preserve-voice
```

Skills compatíveis: `/style-clarity`

---

## Fluxos recomendados por tipo de documento

### Proposta FAPESP PIPE
1. `/structural-edit`: corrija a arquitetura antes de avaliar o conteúdo
2. `/grant-review`: aplique o framework de avaliação PIPE (7 dimensões)
3. `/argumentation`: fortaleça os argumentos de inovação e mercado
4. `/style-clarity`: aperte a prosa para a versão final

### Artigo científico
1. `/structural-edit`: equilíbrio entre seções, transições, conformidade IMRaD
2. `/scientific-review`: metodologia, estatística, conclusões
3. `/argumentation`: lógica da seção de discussão
4. `/references`: completude e formatação das citações
5. `/fact-check`: verifique afirmações com citações

### Post técnico
1. `/argumentation`: a tese central é sólida e bem suportada?
2. `/style-clarity`: público são pares técnicos ou leitores gerais?
3. `/fact-check`: sinalize estatísticas ou atribuições sem fonte

---

## Formatos suportados

| Formato | Caso de uso |
|---------|-------------|
| Posts de blog | Medium, Dev.to, sites pessoais |
| Artigos científicos | Submissões a journals, preprints |
| Propostas de financiamento | FAPESP PIPE, CNPq, FINEP |
| Relatórios técnicos | Documentação interna, white papers |

---

## Primeiros passos

### Pré-requisitos

- [Claude Code](https://claude.ai/code) (CLI ou extensão VSCode)
- Git
- Python >= 3.11 (para ferramentas auxiliares)

### Instalação

```bash
git clone https://github.com/gmferratti/proofwright.git
cd proofwright
```

Se quiser usar as ferramentas Python:

```bash
pip install uv
uv sync
```

As skills ficam em `.claude/commands/` e são automaticamente reconhecidas pelo Claude Code como slash commands.

---

## Estrutura do projeto

```
proofwright/
├── CLAUDE.md                          # Contexto do projeto para o Claude Code
├── LICENSE.md                         # Licença MIT
├── pyproject.toml                     # Dependências Python
├── .claude/
│   └── commands/                      # Skills — invocáveis como /slash-commands
│       ├── pipe-review.md             # Revisão PIPE integrada na voz do autor
│       ├── grant-review.md            # Avaliação FAPESP PIPE (7 dimensões)
│       ├── argumentation.md           # Estrutura lógica e análise de afirmações
│       ├── scientific-review.md       # Metodologia e raciocínio estatístico
│       ├── structural-edit.md         # Organização e fluxo
│       ├── style-clarity.md           # Qualidade de prosa e adaptação de público
│       ├── fact-check.md              # Verificação e cruzamento de referências
│       ├── references.md              # Gestão bibliográfica
│       └── extract-author-style.md    # Extração de perfil estilométrico
├── author_corpus/                     # Textos de referência do autor
│   ├── README.md
│   ├── style_profile.md               # Perfil gerado por /extract-author-style
│   ├── Tese_Doutorado.pdf
│   ├── Texto_REDD.pdf
│   ├── Analysis_of_the_Microtransaction_in_the.pdf
│   └── my-medium-KB/                  # Export do Medium do autor
├── templates/
│   ├── grant-fapesp-pipe-fase1.md     # Template completo PIPE Fase 1
│   ├── grant-fapesp-pipe-fase2.md     # Template completo PIPE Fase 2
│   ├── scientific-article.md          # Estrutura IMRaD para journals
│   ├── blog-post.md                   # Post técnico (Medium, Dev.to)
│   └── technical-report.md            # Relatórios e white papers
├── evaluation/                        # Casos de teste com problemas plantados
│   ├── README.md
│   ├── test-grant-review.md           # 8 problemas plantados em 5 dimensões PIPE
│   ├── test-argumentation.md          # 6 falácias e falhas lógicas
│   ├── test-scientific-review.md      # 7 problemas metodológicos
│   └── test-style-clarity.md          # 6 problemas de prosa
├── examples/
│   ├── blog-post-before-after/        # (placeholder)
│   └── pipe-proposal-review/          # Antes/depois de proposta PIPE com notas
│       ├── draft-original.md          # Rascunho fraco com erros comuns
│       ├── review-notes.md            # Output do /grant-review sobre o original
│       └── draft-revised.md           # Versão revisada
└── real_projects/                     # Rascunhos de trabalho (gitignored)
```

---

## Filosofia

Três princípios que guiam o projeto:

**Skills são revisoras, não assistentes.** Elas encontram problemas, não fazem elogios. O feedback é estruturado, direto e acionável, com referência a trechos específicos do texto. A ideia é simular o olhar de quem vai avaliar o trabalho de verdade (o assessor da FAPESP, o revisor do journal, o leitor técnico experiente) antes de chegar lá.

**Skills são compostas, não isoladas.** Nenhuma skill resolve tudo. Elas foram projetadas para serem usadas em sequência, cada uma atacando uma dimensão diferente do texto. Usar só uma é como revisar um artigo só pela gramática.

**Você continua no comando.** Proofwright amplifica seu conhecimento; não o substitui. Toda sugestão é explícita e rastreável. A decisão final é sempre sua.

---

## Roadmap

- [x] Definições de skills principais (9 skills)
- [x] Skill `/pipe-review`: revisão PIPE integrada na voz do autor
- [x] Skill `/grant-review`: framework de avaliação FAPESP PIPE (7 dimensões)
- [x] Skill `/extract-author-style`: extração de perfil estilométrico do corpus
- [x] Suporte a `--preserve-voice` no `/style-clarity`
- [x] Templates FAPESP PIPE Fase 1 e Fase 2
- [x] Templates de artigo científico, blog post e relatório técnico
- [x] Corpus do autor (`author_corpus/`) com tese, artigos e posts do Medium
- [x] Perfil de estilo gerado (`author_corpus/style_profile.md`)
- [x] Suite de avaliação (4 arquivos de teste com problemas plantados)
- [x] Exemplo: antes/depois de revisão de proposta PIPE
- [ ] Integração com gerenciadores de referências (Zotero, Mendeley)
- [ ] Integração com o Word

---

## Licença

MIT — veja [LICENSE.md](LICENSE.md) para detalhes.

---

*Construído com ofício e rigor por um humano, com uma pequena ajuda de um wright de IA.*
