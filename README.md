<h1 align="center"> Processo Seletivo - Pesquisador I </h1>
<h2 align="center"> Mateus Pinto da Luz Ligocki Vieira </h2>

<h3> Módulos Utilizados </h3>
- polars v0.18.0 <br>
- pandas v2.0.2 <br>
- numpy v1.24.3 <br>
- scikit-learn v.1.4.0 <br>

<h3> Arquivos Constantes Nesse Repositório </h3>
* Dataset/ <br>
    - Pasta contendo seis arquivos (.npy) com os dados de cinco sensores embarcados em uma máquina e o estado em que a máquina se apresentava no momento de cada coleta <br>
* Script.ipynb <br>
    - Arquivo principal do repositório com o desenvolvimento desta pesquisa <br>
    - Dividido em 5 partes principais, análise exploratória dos dados, engenharia de requisitos, seleção do modelo, análise dos resultados, apresentação dos resultados <br>
* Orientações.pages <br>
    - Arquivo fornecido com orientações sobre o problema <br>

<h3> Abordagem realizada </h3>
<h4> Análise exploratória e tratamento dos dados </h4>
- Utilizou-se uma grande parte do tempo disponível para entender o formato dos dados coletados por cada sensor, quais as característica de cada um dos conjuntos fornecidos e o que poderia ser feito sem saber mais detalhes práticos dos dados. <br>
- Verificou-se se haviam valores NaN, como eles estavam distribuídos nas matrizes e levantou-se hipóteses para tratá-los <br>

<h4> Engenharia de Requisitos </h4>
- Em razão da quantidade de variáveis por conjunto de dados, realizou-se a Análise dos componentes principais, de forma a reduzir o número de variáveis <br>
- Assim, para cada um dos conjuntos fornecidos, primeiro padronizou-se os dados, depois calculou-se os componentes principais <br>
- Agora, sem as variáveis, selecionou-se para cada um dos conjuntos os componentes que explicasse 80% da variância dos dados <br>
- Por fim, compilou-se em uma única matriz os componentes principais selecionados para aplicar ao modelo <br>

<h4> Preparação e seleção do modelo </h4>
- Dividiu-se o conjunto de dados entre treino e teste na proporção 70/30 <br>
- Escolheu-se para tentar resolver o problema da classificação do estado da máquina, tendo como base os dados registrados por sensores, uma estrutura de Random Forests em razão de esse modelo ser relativamente simples do ponto de vista estrutural e computacional <br>
- Realizou-se uma busca randomizada entre um conjunto de parâmetros a fim de se encontrar aqueles que gerassem um melhor resultado <br>
- Nesta etapa, a escolha dos pré-parâmetros foi feita de forma arbitrária e seguiu-se os parâmetros sugeridos pelo Random Search <br>

<h3> Resultado </h3>
Acurácia: 0.6275333333333334 <br>
<br>
Matriz de confusão: <br>
[[1868  301  188  324  327] <br>
 [ 185 2200  380   79  151] <br>
 [ 161  458 1732  203  431] <br>
 [ 319  222  246 1806  459] <br>
 [ 214  210  442  287 1807]] <br>
<br>
Precisão: 0.6297113974778199 <br>
<br>
F1: 0.6271967577920019 <br>

<h3> Considerações sobre os resultados </h3>
    - Esta pesquisa foi feita sem detalhamento sobre a forma de coleta dos dados, onde os sensores estavam inseridos na máquina e quais eram os dados esperados da coleta <br>
    - Assim, a maior dificuldade foi entender o que os valores NaN representavam, se eles eram esperados e uma circustância específica ativava um registro ou se foi alguma falha na coleta <br>
    - A Acurácia do modelo não foi satisfatória, não sendo suficiente para colocar o modelo em produção<br>
- Dos 15.000 registros utilizados na etapada de teste, foram classificados corretamente 9.413 (TP), uma acurácia de 62,75%, com uma precisão de 62,97%<br>

- Para melhorar o desempenho do modelo, primeiro seria necessário entender melhor o que era esperado da coleta de dados e se o tratamento realizado foi coerente (não foram analisados outliers, pois entende-se que a possível existência desses poderia ser esperada); além disso, se fosse decidido continuar com as Random Forests, aumentar o universo de possíveis parâmetros e verificar se é possível melhorar o desempenho do modelo. <br>
- Caso optasse por substituir as Random Forests por outro modelo, sugeriria utilizar um modelo de rede neural, o que já fiz em pesquisas passadas, mas não o fiz agora em razão do tempo necessário para estruturar o número, tamanho e tipo das camadas <br># fiesc
# fiesc
# fiesc
# fiesc
