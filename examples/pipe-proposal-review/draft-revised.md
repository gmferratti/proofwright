# SensorGuard: Detecção Preditiva de Falhas em Compressores Industriais via SLM Embarcado e Fusão de Sensores

## Resumo

Falhas não planejadas em compressores de ar industriais representam uma das principais causas de parada de produção no setor de manufatura, com custo médio estimado em R$ 15.000–80.000 por hora de downtime dependendo do setor (McKinsey, 2022). As soluções existentes de manutenção preditiva (GE Predix, Siemens MindSphere, Tractian) exigem integração complexa com sistemas legados, conectividade contínua de nuvem e contratos enterprise a partir de R$ 80.000/ano, tornando-as inviáveis para pequenas e médias indústrias brasileiras.

Este projeto PIPE (Fase 1) propõe demonstrar a viabilidade técnico-científica de um módulo de detecção embarcada de falhas incipientes em compressores — composto por: (a) pipeline de fusão de sensores (vibração triaxial, temperatura, corrente) com feature extraction em tempo real; (b) modelo compacto de detecção de anomalias operando on-device sem dependência de nuvem; e (c) protocolo de calibração por tipo de equipamento. Ao final da Fase 1, esperamos entregar: benchmark de falhas em compressores industriais brasileiros (SensorBench-BR v1), protótipo embarcado validado em ambiente de laboratório, e métricas comparativas contra baseline (threshold fixo e FFT simples), com precisão-alvo ≥ 85% e taxa de falsos positivos ≤ 10%.

## Objetivos

### Objetivo geral
Demonstrar a viabilidade técnico-científica de detecção embarcada de falhas incipientes em compressores industriais, com precisão ≥ 85% e antecedência mínima de 48h em ambiente controlado.

### Objetivos específicos
1. Construir o SensorBench-BR v1: conjunto de dados de vibração/temperatura/corrente de compressores em diferentes estágios de degradação, com rubricas de avaliação rotuladas por especialistas
2. Implementar pipeline de feature extraction em tempo real: domínio do tempo (RMS, curtose, skewness), domínio da frequência (FFT, bandas de frequência de falha por componente) e estatísticas de envelope
3. Treinar e validar modelo embarcado de detecção de anomalias (Isolation Forest + LSTM compacto) comparado a baseline (threshold fixo por vibração global)
4. Validar protótipo em bancada com compressores instrumentados em condições controladas de falha (rolamentos, folga de válvulas, desbalanceamento)
5. Consolidar relatório de viabilidade técnico-científica e plano de escala para Fase 2

### TRL
- **TRL inicial:** 2–3 (conceito de fusão de sensores para diagnóstico de compressores validado em literatura; sem protótipo próprio)
- **TRL esperado ao final da Fase 1:** 4 (validação em laboratório com equipamento real instrumentado)

## Metodologia

### Visão geral
A pergunta central de pesquisa é: *um modelo compacto embarcado, alimentado por features de fusão de sensores, consegue detectar falhas incipientes em compressores com antecedência operacional relevante, sem acesso à nuvem?*

A metodologia combina quatro frentes:

**WP1 — SensorBench-BR v1**
Montagem de bancada com dois compressores de pistão (5–15 cv) instrumentados com acelerômetro triaxial (MEMS, 10 kHz), sensor de temperatura NTC e transdutor de corrente AC. Indução controlada de falhas: desgaste de rolamento (lixamento progressivo de pista interna), folga de válvula (calço graduado), desbalanceamento de rotor (massa excêntrica calibrada). Cada falha será registrada em 5 estágios de severidade (0 = saudável, 4 = crítico). Rubricas de rotulagem definidas com inspetor de manutenção industrial certificado.

**WP2 — Pipeline de feature extraction**
Implementação em Python (scikit-learn, SciPy) com posterior conversão para C embarcado (ESP32-S3): extração de 24 features por janela de 1s, normalização por baseline de equipamento em operação normal, seleção de features por importância (SHAP values sobre o modelo WP3).

**WP3 — Modelo embarcado**
Comparação de três estratégias: (a) Isolation Forest sobre features estáticas — baseline; (b) LSTM compacto (≤50K parâmetros) sobre sequência de features — candidato principal; (c) Autoencoder convolucional 1D — candidato alternativo. Critérios de seleção: precisão no SensorBench-BR, latência de inferência ≤ 200ms, consumo de RAM ≤ 256KB.

**WP4 — Validação em bancada e estudo de ablação**
Protocolo de teste com 30 ciclos por condição de falha. Ablação: sem features de frequência, sem temperatura, sem fusão de sensores — para medir contribuição de cada canal. Avaliação humana: engenheiro de manutenção avalia utilidade operacional dos alertas gerados.

**WP5 — Relatório e plano de Fase 2**
Consolidação de métricas, análise de custo-benefício do hardware embarcado vs. gateway de nuvem, e roadmap técnico para escala (múltiplos tipos de equipamento, campo em produção).

## Equipe

### Pesquisador Responsável
**Dra. Ana Ferreira** — Doutora em Engenharia Elétrica (UNICAMP, 2018) com especialização em processamento de sinais e diagnóstico de máquinas. Publicou 8 artigos em periódicos indexados sobre detecção de falhas em rolamentos via análise de vibração (IEEE Transactions on Industrial Electronics, Mechanical Systems and Signal Processing). Desenvolveu sistema de diagnóstico de motores para o setor de celulose como pesquisadora no IPT (2018–2021). Sócia-fundadora da SensorGuard desde 2022. Dedicação: 60%.

**Carlos Menezes** — Engenheiro de Computação (USP, 2020), 3 anos de experiência em sistemas embarcados (ESP32, STM32, FreeRTOS) e edge ML (TensorFlow Lite, ONNX Runtime). Responsável pelo WP2 e WP3. Dedicação: 80%.

**Bolsista TT-3 (a contratar)** — Engenheiro eletricista para montagem e operação da bancada experimental (WP1 e WP4). Dedicação: 40h/semana. Plano de atividades disponível em separado.

## Mercado e Viabilidade Comercial

### Segmento-alvo
PMEs do setor de manufatura (alimentos, papel, plásticos) com 50–500 funcionários, operando compressores de ar de 5–50 cv sem contrato de manutenção preditiva. Estimativa: ~12.000 empresas no estado de São Paulo (FIESP, 2023).

### Dimensionamento de mercado
- **TAM:** R$ 2,1 bilhões (mercado brasileiro de manutenção preditiva industrial — Mordor Intelligence, 2023)
- **SAM:** R$ 380 milhões (segmento PME + compressores, SP e Sul)
- **SOM (3 anos):** R$ 4,2 milhões (350 clientes × R$ 12.000/ano)

### Análise competitiva

| Concorrente | Ponto forte | Limitação para PME | Nosso diferencial |
|-------------|-------------|-------------------|-------------------|
| Tractian (BR) | Produto maduro, suporte local | A partir de R$ 60k/ano + integração | On-device, sem nuvem obrigatória; instalação em 2h |
| GE Predix | Escalabilidade enterprise | Mínimo R$ 200k/ano; exige SI | Plug-and-play, foco em compressores |
| Siemens MindSphere | Ecossistema completo | Não atende PME | Preço acessível, sem lock-in de plataforma |
| Soluções DIY (Arduino + planilha) | Baixo custo | Sem modelo preditivo; exige manutenção manual | Modelo treinado + alertas automáticos |

### Modelo de negócio
Hardware (módulo SensorGuard) vendido a R$ 3.500 por equipamento monitorado + assinatura de software R$ 350/mês por instalação. Payback estimado para o cliente: 4–8 meses (1 parada evitada por ano).

## Propriedade Intelectual

Levantamento realizado em INPI, USPTO e Google Patents (março/2024) com termos: "embedded predictive maintenance", "vibration fault detection edge computing", "anomaly detection industrial IoT". Encontradas 23 patentes relevantes, todas em escopo de grandes sistemas (nuvem, múltiplos protocolos industriais). Nenhuma cobre a combinação específica de: modelo compacto on-device + fusão de sensores + calibração por baseline de equipamento individual. Liberdade de operação confirmada para o escopo proposto. Estratégia: registro de software do firmware e do pipeline de feature extraction no INPI.

## Orçamento

| Item | Especificação | Valor (R$) | Fonte |
|------|---------------|-----------|-------|
| Acelerômetros triaxiais (4×) | ADXL355, ±8g, 10kHz | 8.400 | FAPESP |
| Sensores de temperatura e corrente (8×) | NTC 10kΩ + ACS712 | 1.200 | FAPESP |
| Plataformas embarcadas protótipo (6×) | ESP32-S3 DevKit | 900 | FAPESP |
| Compressor bancada (1×) | Schulz CSL 20, 5cv | 4.800 | FAPESP |
| Material para indução de falhas | Rolamentos, calços, massas | 3.200 | FAPESP |
| Servidor de desenvolvimento (1×) | Dell PowerEdge T150, 32GB RAM | 12.000 | FAPESP |
| Bolsa TT-3 (9 meses) | 40h/semana | 27.000 | FAPESP |
| Serviços de inspeção industrial | 10 dias × inspetor certificado | 8.000 | FAPESP |
| **Total FAPESP** | | **65.500** | |
| Salários equipe fundadora (contrapartida) | Dra. Ana (60%) + Carlos (80%) × 9 meses | 135.000 | Empresa |
| Infraestrutura e overhead | Espaço, energia, internet | 12.000 | Empresa |
| **Total projeto** | | **212.500** | |

*(Cotações disponíveis para todos os itens acima de R$ 3.000)*

## Cronograma

| Atividade | M1 | M2 | M3 | M4 | M5 | M6 | M7 | M8 | M9 |
|-----------|----|----|----|----|----|----|----|----|-----|
| WP1 — Montagem de bancada | X | X | | | | | | | |
| WP1 — Coleta e rotulagem | | X | X | X | | | | | |
| WP2 — Feature extraction | | | X | X | | | | | |
| WP3 — Treinamento e comparação | | | | X | X | X | | | |
| WP4 — Validação em bancada | | | | | | X | X | | |
| WP4 — Estudo de ablação | | | | | | | X | | |
| WP5 — Relatório final | | | | | | | | X | X |
| Relatório parcial FAPESP | | | X | | | X | | | X |

## Referências

- McKinsey & Company. (2022). *Predictive maintenance: the unexpected driver of productivity gains in manufacturing*. McKinsey Global Institute.
- FIESP. (2023). *Relatório de competitividade industrial do estado de São Paulo*. Federação das Indústrias do Estado de São Paulo.
- Mordor Intelligence. (2023). *Brazil Predictive Maintenance Market — Size, Share & Trends*.
- Lei, Y. et al. (2020). Applications of machine learning to machine fault diagnosis: A review and roadmap. *Mechanical Systems and Signal Processing*, 138, 106587.
- Zhang, W. et al. (2022). Fault diagnosis of rotating machinery based on recurrent neural networks. *Measurement*, 171, 108774.
