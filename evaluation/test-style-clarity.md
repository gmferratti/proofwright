# Fragmento para teste — `/style-clarity`

> Audiência-alvo declarada: engenheiros de software sênior.

---

A implementação da solução proposta pelo presente documento visa, de forma abrangente e considerando todos os aspectos relevantes do problema em questão, realizar a otimização do processo de entrega contínua de software, o que pode potencialmente resultar em melhorias significativas nos indicadores de performance do pipeline de CI/CD da organização.

É importante notar que a utilização de ferramentas de containerização, como por exemplo o Docker, tem se mostrado cada vez mais presente no ecossistema de desenvolvimento de software moderno. Muitos times têm feito a adoção dessas ferramentas. Isto é algo que pode ser considerado como uma tendência relevante para o contexto atual do mercado de tecnologia.

No que se refere à questão da escalabilidade horizontal dos serviços, é necessário que seja feita uma análise cuidadosa das necessidades específicas de cada componente do sistema antes de se proceder com a tomada de decisão acerca de qual estratégia de escalabilidade será a mais adequada para o contexto em questão, dado que existem múltiplas abordagens possíveis que podem ser utilizadas dependendo das circunstâncias particulares de cada caso.

O time teve uma reunião e chegou numa conclusão. A gente vai usar Kubernetes. É uma boa escolha pois resolve os problemas mencionados acima.

---

## Gabarito — Problemas plantados

> Não mostrar ao modelo durante o teste.

**P1 — Nominalização desnecessária**
"realizar a otimização" → "otimizar". A skill deve identificar nominalizações que enfraquecem o verbo.

**P2 — Preamble e hedging excessivo**
"visa, de forma abrangente e considerando todos os aspectos relevantes do problema em questão" é padding sem conteúdo. A skill deve sinalizar.

**P3 — Weasel words que enfraquecem a afirmação**
"pode potencialmente resultar em melhorias significativas" — tripla incerteza onde uma basta. A skill deve identificar e propor revisão.

**P4 — Frase sobrecarregada com múltiplas subordinadas**
O terceiro parágrafo é uma frase única de ~70 palavras com três camadas de subordinação. A skill deve sinalizar e propor quebra.

**P5 — Jargão não explicado para audiência técnica**
"CI/CD" é adequado para a audiência, mas "escalabilidade horizontal" e "containerização" são usados sem precisão — a skill deve avaliar se o nível de detalhe é consistente com engenheiros sênior.

**P6 — Quebra de registro**
O último parágrafo usa linguagem informal ("a gente", "chegou numa conclusão") em um texto que manteve registro formal até então. A skill deve identificar a inconsistência de registro.
