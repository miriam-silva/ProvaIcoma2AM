**Relatório de Consultoria**

**Cliente:** IBM

**Aluna:** Miriam Silva



**Problema de Negócio**

Prever a direção diária das ações da IBM (alta ou baixa no fechamento do mercado) utilizando informações históricas de preço e volume negociado.



**Análise Comparativa dos Modelos**

Os cinco algoritmos foram treinados utilizando exatamente a mesma base de ados, o mesmo conjunto de atributos preditores, a mesma divisão temporal entre treinamento e teste e o mesmo processo de normalização. Dessa forma, a comparação realizada é cientificamente válida e livre de vazamento de dados.



| Modelo              | Acurácia | Precisão | Recall | F1-Score |

| ------------------- | -------- | -------- | ------ | -------- |

| Random Forest       | 0,70     | 0,25     | 1,00   | 0,40     |

| Redes Neurais (MLP) | 0,70     | 0,25     | 1,00   | 0,40     |

| Árvore de Decisão   | 0,60     | 0,20     | 1,00   | 0,33     |

| KNN                 | 0,50     | 0,17     | 1,00   | 0,29     |

| SVM                 | 0,20     | 0,11     | 1,00   | 0,20     |



Observa-se que todos os modelos alcançaram recall de 100%, identificando corretamente todos os dias de alta presentes no conjunto de teste. Entretanto, a principal diferença entre os algoritmos ocorreu na quantidade de falsos positivos gerados. Por esse motivo, o F1-Score foi considerado a métrica mais relevante para comparação, pois equilibra precisão e recall.



O Random Forest e a rede Neural apresentam os melhores resultados, ambos com acurácia de 70% e F1-Score de 0,40. A Árvore de Decisão apresentou um desempenho intermediário, enquanto o KNN e principalmente o SVM demonstraram menor capacidade de generalização para os padrões encontrados na série temporal da IBM.



**Interpretação Científica dos Resultados**

Os resultados indicam que os modelos baseados em árvores conseguiram capturar melhor as relações não lineares existentes entre as variações históricas de preço e volume negociado. O Random Forest superou a Árvore de Decisão tradicional porque a variância das previsões e aumentando a robustez do modelo.



A Rede Neural apresentou desempenho equivalente ao Random Forest. Entretanto, durante o treinamento foi observado um aviso de não convergência após 1000 iterações, sugerindo que o modelo poderia necessitar de mais dados ou ajustes adicionais de hiperparâmetros para atingir seu potencial máximo.



O KNN apresentou desempenho inferior provavelmente devido à natureza dinâmica do mercado financeiro. Como o algoritmo depende da proximidade entre observações históricas, pequenas mudanças no comportamento do mercado podem reduzir sua capacidade de previsão.



O SVM foi o modelo com o pior desempenho. A análise da matriz de confusão mostrou que o algoritmo classificou a maioria das observações como dias de alta, produzindo muitos falsos positivos. Isso sugere que os padrões presentes nos dados não foram adequadamente separados pelo hiperplano construído pelo modelo.



**Veredito do Consultor**

Após a análise dos cinco algoritmos, recomenda-se a utilização do Random Forest como solução principal para este problema de previsão da direção diária das ações da IBM.



A recomendação é sustentada por três fatores principais:

1. Melhor desempenho geral, apresentando a maior acurácia observada (70%) e o maior F1-Score (0,40), empatado apenas com a Rede Neural.
2. Maior robustez estatística, pois o modelo utiliza um conjunto de árvores de decisão que reduz o risco de sobreajuste e melhora a capacidade de  generalização.
3. Maior interpretabilidade, permitindo identificar quais variáveis exercem maior influência sobre as previsões, aspecto importante para aplicações financeiras que exigem transparência e auditabilidade.



Embora a Rede Neural tenha alcançado resultados semelhantes, sua natureza de "caixa preta" dificulta a explicação das decisões tomadas pelo modelo. Em ambientes corporativos e financeiros, a transparência dos critérios utilizados para gerar previsões pode ser tão importante quanto a própria precisão obtida.



**Impacto Ético e Social da Recomendação**

A utilização de modelos de Inteligência Artificial para apoio à tomada de decisão financeira deve ser encarada como uma ferramenta de suporte, e não como um mecanismo autônomo de investimento. Nenhum dos modelos avaliados apresentou desempenho suficiente para garantir previsões totalmente confiáveis em um mercado naturalmente volátil.



A adoção do Random Forest contribui para uma abordagem mais transparente e auditável, reduzindo riscos associados à utilização de sistemas excessivamente opacos. Dessa forma, a recomendação busca equilibrar desempenho preditivo, responsabilidade técnica e governança algorítmica, evitando que decisões financeiras sejam tomas exclusivamente por podemos de difícil interpretação.



**Conclusão**

Com base nos experimentos realizados, conclui-se que o Random Forest representa a alternativa mais adequada para a implantação em produção, oferecendo o melhor equilíbrio entre desempenho, robustez, interpretabilidade e responsabilidade ética para o cenário de previsão da direção diária das ações da IBM.





