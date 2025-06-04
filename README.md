# **Análise de Sentimento em Avaliações de E-commerce: Modelagem e Comparação de Arquiteturas de NLP**

# 1. Descrição Geral do Projeto
Este é um projeto de Processamento de Linguagem Natural (NLP) focado na análise de sentimento de avaliações da plataforma de e-commerce B2W. A solução utiliza diferentes arquiteturas de redes neurais (BERT, LSTM) para classificar as avaliações em sentimentos positivos e negativos. O projeto abrange desde o pré-processamento textual até a comparação de performance entre modelos.

Foram utilizadas boas práticas de tratamento de texto, balanceamento de classes, avaliação de modelos e visualização para facilitar a compreensão dos resultados e apoiar decisões de negócio baseadas em feedback de clientes.

# 2. Ferramentas e Tecnologias
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
<img alt="Pandas" src="https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&amp;logo=pandas&amp;logoColor=white">
<img alt="NumPy" src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&amp;logo=numpy&amp;logoColor=white">
<img alt="TensorFlow" src="https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&amp;logo=TensorFlow&amp;logoColor=white">
<img alt="Matplotlib" src="https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&amp;logo=Matplotlib&amp;logoColor=black">
<img alt="Jupyter Notebook" src="https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&amp;logo=jupyter&amp;logoColor=white">
<img alt="Hugging Face" src="https://img.shields.io/badge/Hugging Face-FFBC00.svg?style=for-the-badge&amp;logo=huggingface&amp;logoColor=black">
<img alt="spaCy" src="https://img.shields.io/badge/spaCy-09A3D5.svg?style=for-the-badge&amp;logo=spacy&amp;logoColor=white">
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)


# 3. Problema de Negócio e Objetivo do Projeto
* **3.1 Qual é o problema de negócio?** 

    A B2W, grande plataforma de e-commerce brasileira, precisa analisar e classificar automaticamente o sentimento de milhares de avaliações de clientes. A empresa busca identificar comentários positivos e negativos para tomar ações direcionadas de melhoria de produtos e serviços.

* **3.2 Qual o contexto?**

    A análise manual de avaliações é inviável devido ao grande volume de dados. Indicadores importantes incluem:

    * Satisfação do cliente (ratings)

    * Comentários textuais detalhados

    * Padrões de linguagem em feedback positivo e negativo

    * Temas recorrentes em reclamações e elogios

    * Um modelo de classificação automática permitirá direcionar esforços para melhorias específicas e monitorar a reputação dos produtos.

* **3.3 Objetivos do Projeto**

    O projeto tem como principal objetivo construir modelos de classificação de sentimento capazes de identificar com precisão avaliações positivas e negativas de clientes. Para isso, será realizado um extenso pré-processamento textual, removendo ruídos e normalizando o texto. Serão testadas diferentes arquiteturas de redes neurais (BERT e LSTM) para determinar qual oferece melhor desempenho na classificação de sentimento em português. O objetivo final é fornecer à empresa uma ferramenta confiável para processar automaticamente o feedback dos clientes e extrair insights acionáveis.

* **3.4 Benefícios do Projeto**

    Os benefícios esperados com este projeto são diversos. Primeiramente, a automatização da classificação de avaliações permitirá um processamento mais rápido e eficiente do feedback dos clientes. A identificação precisa de problemas recorrentes possibilitará melhorias direcionadas em produtos e serviços. Além disso, o monitoramento contínuo do sentimento dos clientes auxiliará na medição do impacto de mudanças implementadas. Por fim, a capacidade de analisar grandes volumes de dados textuais fornecerá insights valiosos para estratégias de marketing e desenvolvimento de produtos.

* **3.5 Conclusão**

    Ao final, conseguimos desenvolver modelos com alta acurácia na classificação de sentimentos, com o BERT apresentando os melhores resultados. Isso permite que a empresa identifique automaticamente avaliações positivas e negativas, direcionando esforços de melhoria e atendimento com base em dados concretos.

# 4. Pipeline da Solução
* **4.1 Pré-processamento de texto:**

    Limpeza e normalização dos textos das avaliações, incluindo remoção de caracteres especiais, conversão para minúsculas, tokenização e remoção de stopwords para facilitar a análise.

* **4.2 Engenharia de atributos textuais:**

    Transformação do texto em representações numéricas, como vetores de palavras, que podem ser processados pelos algoritmos de aprendizado de máquina.

* **4.3 Tratamento de desbalanceamento de classes:**

    Utilização de class weights para lidar com o desbalanceamento entre avaliações positivas e negativas, garantindo que o modelo não se enviesasse para a classe majoritária.

* **4.4 Definição da variável-alvo (feedback):**

    Criação da variável que indica o sentimento da avaliação (positivo ou negativo) com base nas notas atribuídas pelos clientes.

* **4.5 Divisão estratificada dos dados:**

    Separação do conjunto em treino, validação e teste mantendo a proporção das classes para garantir a representatividade em todas as etapas do processo.

* **4.6 Implementação do modelo BERT:**

    Utilização do modelo pré-treinado BERTimbau, específico para português brasileiro, adaptando-o para a tarefa de classificação de sentimento.

* **4.7 Implementação do modelo LSTM:**

    Desenvolvimento de uma arquitetura de rede neural recorrente para capturar relações sequenciais no texto das avaliações.

* **4.8 Avaliação com métricas: Acurácia, F1, Matriz de Confusão:**

    Utilização de diversas métricas para avaliar o desempenho dos modelos, considerando o desbalanceamento de classes.


# 5. Principais Insights de Negócio
* Avaliações positivas frequentemente mencionam entrega rápida, qualidade do produto e boa relação custo-benefício.

* Comentários negativos costumam apontar problemas com atrasos, defeitos em produtos e dificuldades com o serviço de atendimento.

* O pré-processamento textual, incluindo lematização, melhora significativamente o desempenho dos modelos.

* Modelos contextuais como o BERT apresentam melhor desempenho que arquiteturas sequenciais tradicionais.

* A técnica de balanceamento de classes mostrou-se eficaz para melhorar a identificação de feedbacks negativos.

* Comentários mais curtos tendem a ser mais polarizados (muito positivos ou muito negativos).

* Avaliações neutras (rating 3) são as mais desafiadoras para classificar automaticamente.

* Expressões de temporalidade ("chegou antes", "atrasou", "no prazo") são fortes indicadores do sentimento geral da avaliação.

# 6. Modelagem e Avaliação

* **Arquiteturas testadas:**

    * BERTimbau: Modelo pré-treinado em português brasileiro adaptado para classificação de sentimento.

    * LSTM: Rede neural recorrente com capacidade de captar relações sequenciais no texto.

* **Pré-processamento:**

    * Tokenização e normalização dos textos.

    * Remoção de stopwords e caracteres especiais.

    * Lematização para reduzir palavras à sua forma base.

* **Balanceamento de classes:**

    * Utilização de class_weights para penalizar erros na classe minoritária durante o treinamento.

    * Estratificação na divisão treino/validação/teste.

* **Resultados:**

    * BERTimbau: O modelo apresentou os melhores resultados, com acurácia superior a 92% e F1-score de 90%.

    * LSTM: Desempenho satisfatório com acurácia de 87% e F1-score de 83%.

    * Matriz de confusão: Ambos os modelos têm maior facilidade em classificar corretamente avaliações positivas, mas o BERT demonstra melhor equilíbrio.

# 7. Conclusão e Próximos Passos
    O modelo BERTimbau demonstrou ser a melhor escolha para a classificação de sentimento em avaliações de e-commerce em português brasileiro, superando as demais arquiteturas testadas.

    A comparação entre diferentes arquiteturas de deep learning evidenciou a superioridade dos modelos baseados em transformer para esta tarefa específica.

* **Próximos passos:**

    * Implementar análise de aspectos específicos dentro das avaliações (preço, qualidade, entrega, atendimento).

    * Desenvolver visualizações interativas para acompanhamento em tempo real do sentimento dos clientes.

    * Explorar técnicas de oversampling para melhorar ainda mais o desempenho em casos com poucos exemplos.

    * Criar um sistema de alerta para avaliações muito negativas que requerem atenção imediata.

# 8. Considerações Finais
    Este projeto demonstra a eficácia de técnicas modernas de NLP aplicadas à análise de sentimento em português brasileiro. A abordagem metodológica adotada, desde o pré-processamento textual até a comparação de modelos, permitiu desenvolver uma solução robusta para classificação automática de avaliações de clientes.

    O modelo final baseado em BERT alcançou excelentes resultados, com acurácia superior a 92% e bom equilíbrio entre precisão e recall. Essa ferramenta permitirá que empresas de e-commerce processem grandes volumes de feedback de clientes de forma automática e confiável, direcionando esforços de melhoria para áreas específicas e monitorando o impacto de mudanças implementadas.

    A capacidade de analisar sentimentos em texto não estruturado representa uma vantagem competitiva significativa no cenário atual de e-commerce, onde entender e responder ao feedback dos clientes de forma ágil é fundamental para o sucesso do negócio.
