## Otimização Multiobjetivo de Carteiras de Investimentos com Rebalanceamento Utilizando NSGA-II e Modelos de Sobrevivência Baseados em Weibull com Frailty


### **Resumo**

Este trabalho propõe uma abordagem integrada para a otimização de carteiras de investimentos, considerando simultaneamente três critérios fundamentais: retorno esperado, risco associado e custo operacional decorrente do rebalanceamento da carteira. Partindo da premissa de que as decisões financeiras devem incorporar múltiplas dimensões de análise e refletir a dinâmica temporal dos ativos, a metodologia combina técnicas de modelagem estatística, análise fundamentalista e algoritmos evolutivos de otimização.

A modelagem do risco é realizada por meio de Modelos de Sobrevivência com distribuição de Weibull, incorporando o conceito de frailty, que representa fontes de heterogeneidade não observáveis entre os ativos. Essa abordagem permite estimar o tempo até a ocorrência de eventos relevantes de mercado — como quedas bruscas ou valorizações acentuadas — levando em consideração tanto fatores explicativos conhecidos quanto influências latentes que impactam o comportamento individual de cada ativo.

A estimação dos parâmetros dos modelos de sobrevivência é conduzida via método da Máxima Verossimilhança, garantindo rigor estatístico na adaptação aos dados históricos. As informações utilizadas provêm de três fontes principais: (i) simulações de relatórios de composição de carteiras que refletem aportes reais; (ii) cotações e dados do mercado acionário extraídos da API da Brapi; e (iii) indicadores de análise fundamentalista, que fornecem uma base quantitativa e qualitativa para avaliação dos ativos.

Com os riscos modelados e os ativos avaliados, é realizada a identificação dos pontos ótimos de rebalanceamento utilizando Otimização Bayesiana, considerando variáveis como aporte, preço atual, preço médio, número de ações e a pontuação fundamentalista. Em seguida, aplica-se uma estratégia de otimização multiobjetivo com o algoritmo evolutivo NSGA-II (Non-dominated Sorting Genetic Algorithm II), que gera uma Fronteira de Pareto com soluções não dominadas. Cada ponto dessa fronteira representa uma configuração distinta de carteira, equilibrando os três objetivos simultaneamente: maximização do retorno, minimização do risco e redução dos custos de rebalanceamento.

A visualização tridimensional das soluções eficientes permite identificar perfis estratégicos distintos, como o ponto de maior retorno, o de menor risco ou o de equilíbrio ótimo entre os objetivos. Essa análise é essencial para apoiar a tomada de decisão em ambientes de incerteza, fornecendo ao investidor uma ferramenta robusta para alocação de ativos conforme seu perfil de risco e metas financeiras. Cabe destacar que o foco do estudo é exclusivamente na aplicação do NSGA-II, não sendo realizadas comparações com outros algoritmos evolutivos, de modo a validar a viabilidade e consistência da abordagem proposta.


### **Introdução**

A alocação eficiente de ativos em carteiras de investimentos representa um dos principais desafios no campo das finanças, especialmente em contextos de elevada incerteza e dinamicidade dos mercados. Tradicionalmente, abordagens de otimização de carteiras baseiam-se em métricas como retorno esperado e risco, desconsiderando muitas vezes aspectos operacionais relevantes, como os custos envolvidos em rebalanceamentos periódicos. No entanto, decisões de investimento mais robustas requerem a incorporação simultânea de múltiplos objetivos, além da capacidade de capturar a natureza estocástica e latente do comportamento dos ativos ao longo do tempo.

Neste contexto, este trabalho propõe uma metodologia de otimização multiobjetivo de carteiras com rebalanceamento periódico, integrando modelos estatísticos avançados e algoritmos evolutivos. A abordagem emprega Modelos de Sobrevivência com distribuição de Weibull e frailty, que permitem estimar o tempo até eventos relevantes de mercado — como valorizações ou quedas significativas — considerando tanto riscos observáveis quanto não observáveis. A inclusão da frailty no modelo permite captar heterogeneidades individuais entre os ativos que não são explicadas por variáveis diretamente mensuráveis, conferindo maior realismo à modelagem do risco.

A análise dos ativos é fundamentada em indicadores de análise fundamentalista, que fornecem subsídios qualitativos e quantitativos para a avaliação do desempenho e da solidez das empresas. Os dados utilizados provêm de três principais fontes: simulações de relatórios de composição de carteiras, informações de mercado obtidas via API da Brapi e métricas fundamentalistas. Com base nesses dados, os parâmetros dos modelos de sobrevivência são estimados por meio do método da Máxima Verossimilhança.

Uma vez modelados os riscos e definidos os perfis dos ativos, aplica-se uma estratégia de otimização multiobjetivo utilizando o algoritmo evolutivo NSGA-II (Non-dominated Sorting Genetic Algorithm II). Essa técnica permite gerar um conjunto de soluções eficientes — a chamada Fronteira de Pareto — que representa diferentes configurações de carteiras com compromissos entre os objetivos de maximização do retorno, minimização do risco e redução dos custos operacionais. A visualização tridimensional dessas soluções permite uma análise comparativa entre diferentes estratégias, oferecendo ao investidor uma ferramenta poderosa para a tomada de decisões alinhadas a seus objetivos financeiros e perfil de risco.

Ao concentrar-se exclusivamente na aplicação do NSGA-II, este estudo busca validar a robustez e a viabilidade da metodologia proposta, demonstrando o potencial da integração entre modelagem estatística, análise fundamentalista e algoritmos evolutivos para a construção de carteiras mais eficientes e adaptáveis à realidade do investidor.


### **Objetivo Geral**
Desenvolver uma metodologia para otimização de carteiras de investimentos sujeitas a rebalanceamentos periódicos, considerando de forma simultânea três critérios de decisão: retorno esperado, risco estimado e custo operacional das movimentações. A abordagem integra análise fundamentalista com modelos estatísticos de sobrevivência baseados na distribuição de Weibull com frailty, incorporando riscos observáveis e não observáveis à dinâmica dos ativos.


### **Objetivos Específicos**

* Avaliar ativos com base em indicadores de análise fundamentalista, utilizando essas métricas como entrada para a modelagem dos riscos de mercado.

* Aplicar Modelos de Sobrevivência com distribuição de Weibull com frailty para estimar o tempo até eventos financeiros relevantes, levando em conta a heterogeneidade dos ativos e suas características latentes.

* Estimar o retorno esperado, o risco e o custo de rebalanceamento a partir de dados de mercado, perfil da carteira e frequência dos aportes.

* Implementar uma estratégia de otimização multiobjetivo com o algoritmo NSGA-II, com foco em:

* Maximizar o retorno da carteira;
* Minimizar os riscos associados;
* Reduzir os custos envolvidos no processo de rebalanceamento.
