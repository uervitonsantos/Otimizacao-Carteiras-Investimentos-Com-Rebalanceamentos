## Otimização Multiobjetivo de Carteiras de Investimentos com Rebalanceamento Utilizando NSGA-II e Modelos de Sobrevivência Baseados em Weibull com Frailty


Este trabalho apresenta uma abordagem integrada para a otimização de carteiras de investimentos, considerando os aspectos de retorno, risco e custo de rebalanceamento de forma simultânea. A proposta parte da premissa de que a tomada de decisão no ambiente financeiro deve incorporar múltiplas dimensões de avaliação e levar em conta a dinâmica temporal dos ativos. Para isso, são utilizados Modelos de Sobrevivência com Distribuição de Weibull com Frailty, que permitem estimar o tempo até eventos relevantes de mercado (como pontos de entrada ou saída de ativos), considerando riscos observáveis e não observáveis. A frailty introduz heterogeneidade não mensurável entre os ativos, capturando comportamentos individuais além dos fatores conhecidos.

A estimação dos parâmetros desses modelos é realizada via método da Máxima Verossimilhança, com base em três fontes de dados principais: (i) simulações de relatórios de composição de carteiras, que reproduzem aportes reais; (ii) cotações e informações do mercado acionário obtidas por meio da API da Brapi; e (iii) indicadores de análise fundamentalista, que fornecem uma avaliação qualitativa e quantitativa dos ativos. Esses dados servem tanto para a avaliação dos ativos quanto para a construção dos modelos estatísticos.

Com os ativos avaliados e os riscos modelados, aplica-se a Otimização Bayesiana para identificar os pontos ótimos de rebalanceamento da carteira, considerando variáveis como aporte, preço atual, preço médio, número de ações e pontuação fundamentalista. A etapa posterior consiste na implementação da otimização multiobjetiva utilizando o algoritmo evolutivo NSGA-II (Non-dominated Sorting Genetic Algorithm II), que gera um conjunto de soluções não-dominadas — a chamada Fronteira de Pareto — considerando simultaneamente a maximização do retorno, a minimização do risco e a redução dos custos de rebalanceamento.

A visualização tridimensional da fronteira permite analisar as soluções eficientes e identificar perfis distintos de carteiras, como o ponto com maior retorno ou o ponto de equilíbrio ideal entre os três objetivos. Esta análise é essencial para apoiar decisões estratégicas em investimentos, oferecendo ao investidor uma visão ampla das possibilidades de alocação frente aos trade-offs envolvidos. O estudo concentra-se exclusivamente no uso do NSGA-II, sem realizar comparações com outros algoritmos evolutivos, com o objetivo de validar a viabilidade e a robustez da metodologia proposta. Ao final, os resultados evidenciam o potencial da combinação entre técnicas de modelagem estatística, análise fundamentalista e otimização evolutiva para a construção de carteiras mais eficientes e adaptadas ao perfil de risco e aos custos operacionais do investidor.

#### **Objetivo**

Este trabalho tem como objetivo desenvolver uma metodologia para a otimização de carteiras de investimentos sujeitas a rebalanceamentos periódicos, considerando simultaneamente três critérios de decisão: retorno esperado, risco associado e custo operacional envolvido nas movimentações da carteira. A abordagem proposta integra técnicas de análise fundamentalista e modelagem estatística por meio de Modelos de Sobrevivência baseados na Distribuição de Weibull com Frailty, com o propósito de incorporar tanto riscos observáveis quanto latentes à dinâmica dos ativos avaliados.

A avaliação fundamentalista dos ativos fornece subsídios para a definição dos parâmetros do modelo de sobrevivência, permitindo a estimação do tempo até eventos relevantes, como quedas ou valorizações significativas, a partir de séries temporais e dados simulados. A estimação dos parâmetros dos modelos é realizada por meio do método da Máxima Verossimilhança, assegurando a adequação estatística à natureza dos dados históricos.

Com base nos riscos estimados, nos retornos esperados e nos custos de rebalanceamento, aplica-se uma estratégia de otimização multiobjetivo utilizando o algoritmo evolutivo NSGA-II (Non-dominated Sorting Genetic Algorithm II). Esse algoritmo permite a identificação de soluções não dominadas que representam diferentes compromissos entre os objetivos, formando uma fronteira de Pareto tridimensional. A visualização dessa fronteira possibilita uma análise comparativa entre as soluções, destacando pontos de interesse como o de maior retorno e o ponto ideal de equilíbrio entre retorno, risco e custo.

O desenvolvimento da metodologia é conduzido exclusivamente com o NSGA-II, não sendo realizadas comparações com outros algoritmos evolutivos ou técnicas de otimização. Os dados utilizados no estudo são provenientes de três fontes principais: (i) simulações de relatórios de composição de carteira, (ii) dados de mercado obtidos por meio da API da Brapi e (iii) indicadores de análise fundamentalista dos ativos. A proposta visa oferecer uma ferramenta analítica para apoiar decisões em ambientes de incerteza, respeitando os princípios de diversificação, eficiência e controle de custos.

#### **Objetivos Específicos**

* Avaliar os ativos com base em métricas de análise fundamentalista, a fim de incorporar essas informações na modelagem dos riscos de mercado.

* Aplicar Modelos de Sobrevivência com Distribuição de Weibull com Frailty para estimar o tempo até eventos financeiros relevantes, considerando riscos observáveis e latentes associados aos ativos.

* Calcular o retorno esperado, o risco estimado e o custo de rebalanceamento com base em dados de mercado, características da carteira e frequência dos aportes.

* Implementar uma estratégia de otimização multiobjetivo utilizando o algoritmo NSGA-II, com o objetivo de:

* Maximizar o retorno esperado da carteira;
* Minimizar o risco dos ativos;
* Reduzir os custos relacionados aos rebalanceamentos.
