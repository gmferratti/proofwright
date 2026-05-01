# Review — `/grant-review` aplicado ao SensorGuard

> Output gerado pela skill `grant-review` sobre o rascunho original.

---

## Avaliação FAPESP PIPE — SensorGuard

### Dimensão 1 — Projeto de Pesquisa
**Verdict: Fraco**

> *"Desenvolver o SensorGuard para monitoramento preditivo industrial."*
> **Problema:** Objetivo geral não é mensurável. Não especifica o que será provado ao final da Fase 1, qual métrica define sucesso, nem qual é o TRL esperado.

> *"Vamos instalar sensores nos equipamentos, coletar dados por alguns meses, treinar um modelo de machine learning com os dados coletados"*
> **Problema crítico:** A metodologia descreve *o quê* será feito, não *como*. Qual arquitetura de ML? Quais features serão extraídas dos dados de vibração/temperatura? Qual o volume de dados necessário para treinar um modelo confiável? Qual o critério de suficiência para cada etapa? Sem isso, o assessor não consegue avaliar se o projeto é viável.

> *"coletar dados por alguns meses"*
> **Problema:** "Alguns meses" não é uma especificação metodológica. Quantos meses? Qual frequência de amostragem? Sob quais condições operacionais?

**Ações necessárias:**
- Definir objetivo mensurável: ex. "atingir precisão ≥ X% na detecção de falhas com Y dias de antecedência em ambiente controlado"
- Especificar arquitetura de ML candidata e justificativa (ex. LSTM para séries temporais, Isolation Forest para detecção de anomalias)
- Detalhar protocolo de coleta: frequência, duração, condições, equipamentos-alvo

---

### Dimensão 2 — Pesquisador Responsável e Equipe
**Verdict: Fraco**

> *"João Silva — CEO da empresa, responsável pelo projeto"*
> **Problema crítico:** O PR é o CEO — isso não estabelece qualificação técnica. O assessor precisa saber: qual é a formação de João? Ele tem experiência em ML, processamento de sinais, ou sistemas embarcados? Sem isso, a proposta falha no critério mais importante do PIPE.

> *"a equipe tem experiência em desenvolvimento de software e vai aprender as técnicas de ML necessárias durante o projeto"*
> **Problema bloqueante:** Esta frase sinaliza explicitamente que a equipe não tem a expertise necessária para executar o projeto. O PIPE não financia aprendizado — financia pesquisa conduzida por equipe já qualificada. Esta afirmação, se submetida assim, garantirá reprovação nesta dimensão.

> *"Pedro Lima — estagiário"*
> **Problema:** Estagiário não qualifica como membro de equipe de pesquisa sem bolsa TT formalizada e plano de atividades.

**Ações necessárias:**
- Descrever currículo técnico do PR: formação, projetos anteriores em IoT/ML/sistemas embarcados, publicações ou produtos desenvolvidos na área
- Se a equipe não tem expertise em ML, adicionar um pesquisador ou consultor com essa qualificação — ou reposicionar o projeto para o que a equipe sabe fazer
- Remover ou reformular a frase sobre "aprender durante o projeto"

---

### Dimensão 3 — Viabilidade do Empreendimento
**Verdict: Fraco**

> *"O mercado de manutenção preditiva é enorme e está crescendo muito."*
> **Problema:** Afirmação sem dado. Qual o tamanho do mercado? Qual a taxa de crescimento? Fonte?

> *"sem concorrentes diretos no mercado brasileiro"*
> **Problema crítico:** Esta afirmação é improvável e sinalizará para o assessor falta de pesquisa de mercado. Há players como Tractian (São Paulo), Mtell (Oracle), SKF, e outros. "Sem concorrentes" quase nunca é verdade e prejudica a credibilidade da proposta.

> *"Nossa solução vai ser mais barata"*
> **Problema:** Estratégia competitiva baseada apenas em preço é fraca. Não especifica quanto mais barata, em qual segmento de cliente, e não endereça por que clientes migrariam de soluções existentes.

**Ações necessárias:**
- Incluir TAM/SAM/SOM com fontes (ex. relatórios de mercado, ABIMAQ, CNI)
- Mapear concorrentes reais: Tractian, Uptake, C3.ai, soluções de OEMs como GE e Siemens — e mostrar onde o SensorGuard se diferencia *além do preço*
- Definir segmento-alvo específico: qual indústria (papel e celulose? alimentos? petroquímica?), qual porte de empresa, qual equipamento prioritário

---

### Dimensão 4 — Orçamento
**Verdict: Fraco**

> *"Salários da equipe (6 meses): R$ 120.000"*
> **Problema bloqueante:** FAPESP não financia salários como item de orçamento. Isso é despesa operacional da empresa, não item elegível no PIPE. O assessor rejeitará este item e o valor total solicitado estará incorreto.

> *"Software e licenças: R$ 20.000"*
> **Problema:** Sem justificativa. Quais softwares? Para quê? Com cotações?

> *"Sensores (10 unidades): R$ 50.000"*
> **Problema:** Sem especificação técnica (fabricante, modelo, faixa de medição) e sem cotações. R$5.000 por sensor pode ser adequado ou não — depende do tipo.

**Ações necessárias:**
- Remover salários como item FAPESP — registrar como contrapartida da empresa
- Adicionar justificativa técnica e memória de cálculo para cada item
- Incluir ao menos 3 cotações para equipamentos acima do limite FAPESP
- Verificar elegibilidade de cada item nas normas PIPE

---

### Dimensão 5 — Propriedade Intelectual
**Verdict: Ausente**

Não há menção a levantamento de anterioridade ou análise de PI em nenhuma seção. Causa frequente de reprovação.

**Ações necessárias:**
- Realizar busca de patentes (INPI, USPTO, Google Patents) com termos como "predictive maintenance IoT", "vibration anomaly detection"
- Documentar o que foi encontrado e concluir sobre liberdade de operação
- Definir estratégia de proteção dos ativos gerados (registro de software? depósito de patente?)

---

### Dimensão 6 — TRL
**Verdict: Ausente**

TRL não é mencionado em nenhum momento. O cronograma não permite inferir qual é o estado atual da tecnologia nem o que será entregue.

**Ações necessárias:**
- Declarar TRL inicial (provavelmente TRL 2–3 se não há protótipo)
- Declarar TRL esperado ao final da Fase 1 (TRL 3–4)
- Justificar a evolução com base nas atividades planejadas

---

## Resumo da Avaliação

### Problemas críticos (impediriam aprovação)
1. Equipe sem expertise demonstrada em ML — e a proposta admite isso explicitamente
2. Salários incluídos como item FAPESP (inelegível)
3. Metodologia sem especificação técnica suficiente
4. PI e TRL ausentes

### Problemas relevantes
5. Concorrentes mal mapeados ("sem concorrentes" é red flag)
6. Objetivo geral não mensurável
7. Mercado sem dimensionamento quantitativo

### Próximos passos (por prioridade)
1. Recrutar ou formalizar um pesquisador com expertise em ML/processamento de sinais — sem isso, o projeto não passa na Dimensão 2
2. Reescrever a metodologia com especificação técnica real
3. Corrigir o orçamento: remover salários, adicionar justificativas e cotações
4. Fazer levantamento de PI e mapear concorrentes reais
