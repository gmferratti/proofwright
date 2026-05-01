# AquaDetect: Sistema de Detecção de Vazamentos em Redes de Distribuição de Água

## Resumo

O AquaDetect é um sistema de detecção de vazamentos em redes de abastecimento de água usando sensores de pressão e aprendizado de máquina. O Brasil perde cerca de 40% da água tratada em vazamentos, gerando prejuízos enormes. Nossa solução resolve esse problema de forma inovadora e mais eficiente que as alternativas atuais.

A equipe tem vasta experiência em tecnologia e está animada para desenvolver essa solução que vai transformar o setor de saneamento brasileiro.

## Objetivos

Desenvolver e validar o AquaDetect para detecção automática de vazamentos em redes de distribuição.

Objetivos específicos:
1. Instalar sensores de pressão em pontos estratégicos da rede
2. Desenvolver algoritmo de detecção baseado em machine learning
3. Criar sistema de alertas para operadores
4. Realizar piloto em rede real

## Equipe

**Dr. Ricardo Alves** — Diretor de tecnologia, PhD em Ciência da Computação com foco em redes de computadores. 15 anos de experiência em desenvolvimento de software. Lidera a equipe técnica. Dedicação: 20%.

**Bruno Costa** — Engenheiro de software, 2 anos de experiência. Responsável pelo desenvolvimento do sistema. Dedicação: 100%.

## Mercado

O mercado de smart water é gigantesco globalmente. Não há soluções consolidadas para o Brasil especificamente voltadas para detecção de vazamentos com IA. Nosso diferencial é usar machine learning, que é mais avançado que as tecnologias atuais usadas pelas concessionárias.

Pretendemos atender todas as concessionárias de água do Brasil.

## Metodologia

Instalaremos sensores de pressão em uma rede de distribuição parceira, coletaremos dados de pressão, treinaremos um modelo de ML para identificar padrões de vazamento, e disponibilizaremos os alertas via dashboard web. A metodologia segue as melhores práticas da área.

## Propriedade Intelectual

Fizemos uma pesquisa e não encontramos patentes relevantes que impeçam nosso trabalho. O sistema que vamos desenvolver é inovador e não há nada igual no mercado.

## TRL

O projeto parte do zero e ao final da Fase 1 teremos um sistema completo operando em campo com concessionária real.

## Orçamento

| Item | Valor (R$) |
|------|-----------|
| Sensores de pressão (50 unidades) | R$ 75.000 |
| Infraestrutura de servidores (cloud, 12 meses) | R$ 36.000 |
| Salários da equipe (9 meses) | R$ 180.000 |
| Viagens para instalação | R$ 15.000 |
| Marketing e vendas | R$ 24.000 |
| **Total** | R$ 330.000 |

---

## Gabarito — Problemas plantados

> Não mostrar ao modelo durante o teste. Conferir após o output da skill.

**P1 — Dimensão 2 (Equipe): PR com expertise errada**
O PhD em "redes de computadores" não tem qualificação em hidráulica, detecção de anomalias em séries temporais de pressão, ou sistemas de distribuição de água. A skill deve sinalizar desalinhamento entre a expertise declarada e as demandas técnicas do projeto.

**P2 — Dimensão 2 (Equipe): Dedicação insuficiente do PR**
20% de dedicação do Pesquisador Responsável é muito baixo. A skill deve sinalizar que isso é inadequado para liderar um projeto de P&D.

**P3 — Dimensão 1 (Metodologia): Ausência de especificação técnica**
"A metodologia segue as melhores práticas da área" não descreve nada. A skill deve sinalizar que a metodologia não é reprodutível e não especifica *como* os objetivos serão alcançados.

**P4 — Dimensão 4 (Orçamento): Itens inelegíveis**
"Salários da equipe" e "Marketing e vendas" são inelegíveis no PIPE. A skill deve identificar ambos.

**P5 — Dimensão 3 (Mercado): Segmento-alvo irreal**
"Atender todas as concessionárias do Brasil" não é um segmento-alvo — é a totalidade do mercado, sem priorização. A skill deve sinalizar ausência de estratégia de entrada realista.

**P6 — Dimensão 5 (PI): Levantamento superficial**
"Fizemos uma pesquisa e não encontramos patentes" sem nomear bases consultadas, termos de busca ou patentes analisadas. A skill deve sinalizar que isso não é um levantamento adequado.

**P7 — Dimensão 6 (TRL): Incompatibilidade de fase**
"Sistema completo operando em campo com concessionária real" é TRL 7–8, incompatível com Fase 1 (que deve chegar a TRL 3–4). A skill deve identificar o desalinhamento de TRL.

**P8 — Dimensão 3 (Mercado): Afirmação de ausência de concorrentes sem fundamento**
"Não há soluções consolidadas para o Brasil" ignora players como Idrica, Sensus (Xylem), Itron e startups brasileiras. A skill deve questionar esta afirmação.
