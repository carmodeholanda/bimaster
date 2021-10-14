<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->
# Avaliação de técnicas de predição na determinação de preços de bens industriais

#### Alunos: [Fernando Nahid Leitão](https://github.com/fernandonahid) , [Adriano Gonçalves da Silva](https://github.com/adrianogo) e [Leonardo Carmo de Holanda](https://github.com/carmodeholanda)
#### Orientadora: [Manoela Kohler](https://github.com/manoelakohler)

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->

---

### Resumo

As aquisições de bens industriais são fundamentais para a garantia da funcionalidade de equipamentos, fábricas e unidades operacionais das mais diversas empresas. Diferentemente de materiais mais simples ou de consumo, os bens industriais não possuem seus preços divulgados e muitas vezes não fazem parte de catálogos padronizados. Desta forma, uma correta predição dos preços de bens industriais é fundamental para o desenvolvimento das empresas, seja através do correto planejamento dos dispêndios, seja através da melhora da qualidade das negociações comerciais.

O projeto consiste na aplicação de técnicas de data mining e machine learning em bases de dados de aquisições de bens industriais afim de se avaliar os modelos de predição mais aderentes. Por fim, com base nos resultados alcançados o presente projeto prevê avaliar também quais modelos poderiam ser utilizados na automatização dos processos de determinação de preços de bens industriais nas empresas a partir das características de cada base.

### Abstract 

The  industrial goods purchase are essential to guarantee the equipments, factories and operational plants functionality of the most diverse companies. Unlike simpler or  consumer goods, industrial goods do not have their prices published and are often not part of standardized catalogues. In this way, a correct industrial goods prices prediction is essential for the companies development, either through the correct expenditures planning, or through the commercial negotiations quality improvement.

This project consists in the application of data mining and machine learning techniques in  industrial goods acquisitions databases in order to evaluate the most adherent prediction models. Finally, based on the results achieved, this project also intends to evaluate which models could be used to automate industrial goods determining price processes in companies based on the each base characteristics.

### 1. Introdução

Quando se fala de aquisição de bens industriais, existem uma infinidade de opções e tipos de bens que podem ser fornecidos pelos mais diversos mercados fornecedores. Inicialmente para a realização desse projetos, foram selecionadas [3 bases](https://github.com/fernandonahid/Projeto-Final/blob/main/1%20-%20BASES%20DE%20DADOS%20(CSV).zip) representativas de bens industriais com características típicas desse tipo de fornecimento, porém diferentes umas das outras. Essas bases representam de uma forma geral a grande maioria dos tipos de bens industriais:

- Base 1 – Base representativa de itens com características técnicas simples, normalmente associadas a dimensões, pesos, materiais comuns ao mercado fornecedor e sem muita complexidade na fabricação, que ocorre na maioria das vezes em série contínua. Essa base possui inicialmente 2921 itens com pelo menos 12 atributos de características técnicas no catálogo.
- Base 2 – Base representativa de itens com características técnicas específicas, mas muitas vezes padronizadas. Esses itens são normalmente associados a bens operacionais, tais como equipamentos de pequeno porte, bens comuns a vários segmentos da indústria, entre outros. Possuem características técnicas similares entre fornecedores, e sua fabricação se dá através de linha de produção ou categoria. Essa base possui inicialmente 8018 itens com pelo menos 21 atributos de características técnicas no catálogo.
-	Base 3 – Base representativa de itens com características técnicas extremamente complexas, normalmente associadas a equipamentos de grande porte, com características exclusivas e com fabricação através de montagem individual. Essa base possui inicialmente 343 itens com pelo menos 28 atributos de características técnicas no catálogo.

As bases selecionadas passaram por 3 etapas de tratamento com objetivo de torna-las mais efetivas e aptas a serem utilizadas por algoritimos de data mining e machine learning. A primeira etapa de tratamento teve como objetivo um tratamento inicial e um pré-processamento das bases, contemplada em pequenos ajustes e exclusões. Na segunda etapa, as bases passaram por tratamento de missing values e análise de impacto de cada atributo. Por fim, na terceira etapa foram feitas reduções de dimensionalidade, análise de balanceamento, tratamento de outliers, transformações e ajustes adicionais.

As bases tratadas foram submetidas a diversos modelos de predição através do uso de algoritimos de classificação, de regressão e de redes neurais, aprendidos ao longo do presente curso. Foram utilizados modelos distintos, tanto em algoritimos de Python quanto operadores do Rapidminer. Por fim os resultados obtidos foram comparados a fim de se obter os modelos mais aderentes a cada tipo de base típica representativa do mercado de bens industriais e possibilitar o desenho de um roteiro de automatização sugerido para cada uma.

### 2. Modelagem

#### 2.1. Etapa 1 - Pré-processamento e tratamento incial dos dados

Para a [etapa 1](https://github.com/fernandonahid/Projeto-Final/blob/main/2%20-%20ETAPA%201%20-%20POWERBI.pbix) de tratamento dos dados, optou-se pela utilização do powerquery do powerbi pela facilidade de utilização. Nessa etapa, todas as 3 bases receberam os seguintes tratamentos:

- Descaracterização e modificação de dados sensíveis;
- Atualização dos preços para mesma data base;
-	Exclusão de moedas estrangeiras da amostra;
-	Padronização das unidades de medidas;
-	Acerto e transformação dos atributos numéricos;
-	Tratamento estatístico;
-	Retirada de outliers através de intervalo de confiança (80%);
-	Eliminação de atributos não necessários ao projeto.

#### 2.2. Etapa 2 – Tratamento de missing values e análise de impacto de atributo no resultado (peso) 

Para a [etapa 2](https://github.com/fernandonahid/Projeto-Final/blob/main/3%20-%20ETAPA%202%20-%20RAPIDMINER.zip) de tratamento dos dados, optou-se pela utilização do Rapdminer. Nessa etapa, todas as 3 bases receberam os seguintes tratamentos:

-	Exclusão de atributos com problemas ou irrelevantes para o modelo, como por exemplo com quase nenhum preenchimento ou com um valor único;
-	Tratamento dos missing values através da exclusão de algumas linhas dos modelos, através de substituição por valor específico ou por valor mais comum (average);
-	Análise de impacto dos atributos (peso).

Os resultados das análises de impacto dos atributos (peso) para as bases 1, 2 e 3 podem ser visualizados nos figuras 1, 2 e 3 respectivmente. Os atributos (linhas da figura) que se apresentam tachados foram excluídos na etapa posterior de tratameto, etapa 3.

| ![image](https://user-images.githubusercontent.com/90539237/136080307-942ccf9e-e938-4a2d-a0f3-b5eb021710db.png) | 
|:--:| 
| `Figura 1 – Base 1 - Análise de impacto de atributo (peso)` |

| ![image](https://user-images.githubusercontent.com/90539237/136080405-9c3f5f77-f4f6-4346-9a41-d50260d1050e.png) | 
|:--:| 
| `Figura 2 – Base 2 - Análise de impacto de atributo (peso)` |

| ![image](https://user-images.githubusercontent.com/90539237/136080425-b48208a7-b3e7-486d-982b-5b7729c34fb9.png) | 
|:--:| 
| `Figura 3 – Base 3 - Análise de impacto de atributo (peso)` |

#### 2.3. Etapa 3 – Redução de dimensionalidade, tratamento de outliers, balanceamento, transformações e ajustes adicionais

Para a [etapa 3](https://github.com/fernandonahid/Projeto-Final/blob/main/4%20-%20ETAPA%203%20-%20RAPIDMINER.zip) de tratamento dos dados, optou-se pela utilização do Rapdminer. Nessa etapa, todas as 3 bases receberam os seguintes tratamentos:

-	Exclusão dos atributos de menor impacto na análise de peso da etapa anterior, conforme figuras 1, 2 e 3 (Redução de dimensionalidade);
-	Remoção de outliers por "Outilier Distance" e "Univariate Outlier Detection". Optou-se por retirar os outliers da interseção entre outliers detectados por "Outlier Distance" com "Univariate Outlier Detection" de score maior que 1.5;
-	Teste de modelos para balanceamento das bases, mas que em geral, pelas características das bases, não trouxe alterações significativas;
-	Discretização, transformações e normalizações necessárias para se obter a base final desejada.

### 3. Resultados

#### 3.1. Modelos automatizados em Rapidminer

Após todo tratamento efetuado nas etapas anteriores do estudo, optou-se por utilizar a ferramenta Rapidminer e seus operadores para análise preditiva. A resposta ao estudo dos melhores modelos para as bases de forma individualizada não foi satisfatória, pois a personalização necessária causou uma enorme dificuldade de comparação em cada base e entre as bases, causando muito impacto na capacidade conclusiva do estudo. Dessa forma, foram utilizados os [modelos automatizados](https://github.com/fernandonahid/Projeto-Final/blob/main/5%20-%20PREDI%C3%87%C3%83O%20-%20RAPIDMINER.zip.001) de análise da ferramenta Rapidminer. Essa escolha foi necessária pois, por se tratar de um estudo comparativo, o presente trabalho necessitava de padronização dos modelos.

As figuras 4, 5 e 6 abaixo apresentam os resultados obtidos com diferentes operadores, em termos de acurácia, para cada uma das 3 bases. A acurácia foi avaliada através da divisão em classes, por frequência, em 5, 10 e 20 partes. Pode se perceber que a base 1 possui melhor resultado quando comparado com as demais, sendo a base 3 a de pior resultado.

| ![image](https://user-images.githubusercontent.com/90539237/136123924-c0cfe3cf-b967-4d87-86dd-0aa90973f4b3.png) | 
|:--:| 
| `Figura 4 – Base 1 - Resultados de acurácia por modelo de classificação` |

| ![image](https://user-images.githubusercontent.com/90539237/136123942-4cc0a4bd-0737-4b34-9904-3a3c18b94668.png) | 
|:--:| 
| `Figura 5 – Base 2 - Resultados de acurácia por modelo de classificação` |

| ![image](https://user-images.githubusercontent.com/90539237/136123950-ed54ab88-5bc4-4145-96ed-e353440588d8.png) | 
|:--:| 
| `Figura 6 – Base 3 - Resultados de acurácia por modelo de classificação` |

Já a figura 7 na sequência, apresenta os resultados obtidos para o erro relativo quando da não utilização de classes, para diferentes operadores. Novamente pode se perceber que a base 1 possui melhor resultado quando comparado com as demais, sendo a base 3 a de pior resultado.

| ![image](https://user-images.githubusercontent.com/90539237/137057703-4772f060-c997-4a3a-a216-eb8d348aaf6c.png) | 
|:--:| 
| `Figura 7 – Erro relativo por modelo de predição` |

#### 3.2. Modelo de rede Neural em Python 

Adicionalmente ao modelo utilizado em Rapidminer optou-se por avaliar as bases do estudo também, quanto a resposta preditiva, através de um [algoritimo de redes neurais](https://github.com/fernandonahid/Projeto-Final/blob/main/6%20-%20PREDI%C3%87%C3%83O%20-%20REDE%20NEURAL%20PHYTON.zip) em Python. Para melhor padronização e comparação, o modelo adotado, também procurou dividir as basese em 5, 10 e 20 classes. Foram utilizados modelos simplificados de redes neurais, com 2 camadas, normalmente associadas a quantidade de variáveis disponíveis em cada base. O treinamento ocorreu através de 500 épocas e em 80% da amostras, sendo os outros 20% separados para teste.

A figura 8 apresenta os resultados obtidos para o modelo de rede neural adotado:

| ![image](https://user-images.githubusercontent.com/90539237/137059769-3eb284b4-ce02-4135-9792-dab7d5edf2f4.png) | 
|:--:| 
| `Figura 8 – Acurácia obtida no modelo de redes neurais em Python` |

#### 3.3. Modelo de regressão em Python 

Por fim, um [arquivo Python](https://github.com/fernandonahid/Projeto-Final/blob/main/7%20-%20PREDI%C3%87%C3%83O%20-%20REGRESS%C3%83O%20PHYTON.zip) com diferentes modelos de regressão foi adotado para avaliar a resposta da predição para cada base. Em geral os modelos foram avaliados por regressão linear múltipla, e otimizado através da retirada de variáveis não relevantes, ou seja, sem impacto nos resultados.

Posteriormente também foi feita a análise considerando modelos de regressão polinomial múltipla. A figura 9 apresenta os resultados de R2 ajustado obtidos para os modelos de regressão. Importante ressaltar que a figura 9 apenas ilustra os resultados obtidos, sem críticas e análises mais profundas aos resultados obtidos, que serão feitas nas conclusões (optou-se por colocar na figura 9 apenas o resultado da regressão polinomial de 3º grau).

| ![image](https://user-images.githubusercontent.com/90539237/137063726-14406969-d5c6-4711-864e-20af0fb907e0.png) | 
|:--:| 
| `Figura 9 – Resultados dos modelos de regressão em Python` |

### 4. Conclusões

Através dos resultados obtidos no item 3 deste projeto pode se chegar as seguintes conclusões:

1) As classificações padronizadas são importantes para divisão das bases através dos seu atributos de maior relevância. Com base nos resultados obtidos para as classificações padronizadas no presente projeto pode se perceber que os modelos baseados em algoritimos de classificação, como os de árvores, regressão logística e bayesiano, foram eficientes em classificar, com resultados equivalentes aos demais modelos.  Embora os resultados obtidos sejam compatíveis com os demais modelos,  a classificação em geral, baseada nesses modelos, não foi altamente acertiva.

2) Os modelos baseados em aprendizado supervisionado, como support vector machine e fast large margin obtiveram resultados ruins para classificação, porém bem acertivos (support vector machine), baixo erro relativo, quando em predição sem classificação. Esse resultado é compatível com as bases, uma vez que as mesmas apresentam um alto índice de erro e dificultam a classificação, porém possuem muita quantidade de dados (bases 1 e 2) o que constuma resultar em boas respostas quando da aplicação de modelos de aprendizado.

3) Em geral os modelos de redes neurais foram os que melhor funcionaram nas bases de preços de bens industriais, quando tratadas em massa (deep learning no Rapidminer e o modelo em Python). Isso ocorreu tanto para modelos de classificação quanto para sem classificação. As redes neurais foram capazes, devido ao seu aprendizado, de capturar de forma mais sensível as variações que ocorrem no modelo e que nem sempre estão relacionadas a uma ou outra característica técnica, como por exemplo, variações do mercado fornecedor. Importante ressaltar que para que os modelos de rede neural funcionem bem, as bases devem ter bastante dados e o tratamento de outliers e estatístico é fundamental.

4) Os modelos de regressão, talvez tenham sido os modelos bem sensíveis e capazes de capturar particularidade das bases. Embora tenham sido acertivos, numa primeira análise, não é possível concluir que sua utilização foi satisfatória, pois em geral, os modelos de regressão linear não foram capazes de capturar pontos extremos ou específicos e as regressões polinomias podem ter produzido um efeito de adequação da curva aos pontos, em casos extremos ou específicos, de baixa quantidade de pontos e que podem conter erros os vícios nos valores.  
 
Com base nas conclusões do presente trabalho recomenda-se os seguitnes tratamentos e etapas de forma padronizada para as bases::

1) Base 1 – Base representativa de itens com características técnicas simples, normalmente associadas a dimensões, pesos, materiais comuns ao mercado fornecedor e sem muita complexidade na fabricação: a) Limpeza eficiente da base, retirando duplicidades e erros, o que para esse tipo de base costuma ser mais fácil; b) Uso de regressão para casos em que se deseja obter uma equação típica para servir de ferramenta de análise ou nos casos de estimativa rápida do valor; c) Por fim para predição eficiente e rápida, o uso de redes neurais típicas (modelos padronizados).
    
2) Base 2 – Base representativa de itens com características técnicas específicas, mas muitas vezes padronizadas, normalmente associados a bens operacionais, tais como equipamentos de pequeno porte, bens comuns a vários segmentos da indústria, entre outros: a) Modelos de classificação para divisão em categorias similares; b) Uso de regressão para casos de estimativa de preços manual; c) Uso de redes neurais, tomando cuidado em tratar os dados, seja dividindo em classes, seja retirando outliers, para se obter um resultado mais eficiente. 

3) Base 3 – Base representativa de itens com características técnicas extremamente complexas, normalmente associadas a equipamentos de grande porte, com características exclusivas e com fabricação através de montagem individual: a) Geração e manutenção de base de dados manual e com análise técnica de especialista; b) Uso de classificação ou regressão para obter as variáveis de maior impacto (trabalho a ser feito em cada análise) c) Para predição o uso de rede neural apenas em bases boas e a regressão supervisionada por especialistas em todos os outros casos.

---

Matrícula:  192.671.055 / 192.671.008 / 192.671.058

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
