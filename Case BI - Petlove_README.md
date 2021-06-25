# README Case BI - Petlove

#### Após consultar as informações do case e analisar a base de dados fiz uso das ferramentas que me foram dadas para explorar os pontos a seguir:

* Foco no grupo de assinantes que possuem o status de assinatura como cancelado.

* Explorar as versões de assinatura que foram presentens nos registros de cancelamento.

* Calcular o Churn da base de dados. 

* Fazer uso de resultados probabilísticos e estatísticas para explorar informações da base de dados. 

* Calcular o intervalo entre a criação da assinatura e o cancelamento. 

* Fazer uso de gráficos e tabelas para trazer informações relevantes. 

* Explorar as idades que mais realizaram cancelamento da assinatura. 

* Exibir os estados e regiões do Brasil que mais foram presentes no grupo de cancelamento. 

#### Fiz uso das seguintes bibliotecas para analisar os dados:

* Pandas, utilizada para manusear e organizar os dados conforme o necessário.

* Numpy, utilizada para cálculos matemáticos e conversões de variáveis.

* Matplotlib, utilizada pra visualização dos dados em forma de gráficos.

* Plotly, utilizada para visualização dos dados de forma dinâmica. 

* datetime, utilizada para converter variáveis do tipo data.


# Armazenamento dos dados

* Optei por armazenar a tabela em uma variável que me permite trabalhar com as informações utilizando métodos da biblioteca pandas.


* Para poder entender melhor os campos da tabela exibi parte do dataframe. 

# Limpando colunas com criptografia

* Essa remoção foi feita para organizar a tabela e remover colunas que não seriam úteis para a análise por estarem criptografadas. 


* Utilizei o método .drop da biblioteca Pandas que remove a coluna escolhida com base em seu nome com inplace verdadeira para manter essa alteração no dataframe. 

# Retirando informações do dataframe

* Explorei alguns valores do dataframe como seu tamanho, a quantidade de assinantes que haviam pausado ou tinham a assinatura ativa e a quantidade de assinantes que haviam cancelado a assinatura utilizando métodos pandas para ter noção do volume dos dados e suas classificações.


* Utilizando métodos pandas trouxe informações sobre os tipos de status presentes no dataframe e suas medidas estatísticas e probabilísticas como quantidade, média, desvio padrão e valores mínimos e máximos.


* Busquei informações sobre os tipos de versões com base na variável status e verifiquei que existiam 3 tipos. Escolhi atribuir a uma variável os registros que possuiam o status de cancelado e a outra variável os de status ativo para poder trabalhar com estes grupos, sem fazer uso do grupo de status pausado. 

# Cálculo do Churn total

* Com base na explicação do case realizei o calculo utilizando o número total de assinantes com status cancelado sobre número total de assinantes ativos. 


* Não inclui o grupo de status pausado pelo fato de que, segundo o case, o churn é o cálculo entre os assinantes com status ativo e os assinantes com status cancelado.


* Churn: 5.924448615673393



# Tempo entre a assinatura e o cancelamento

* Número de dias entre a assinatura e o cancelamento do produto para o grupo de assinantes com status cancelado. 


* Atribuí a duas variáveis os registros da data de criação e data de cancelamento do grupo que possuia status cancelado para calcular o intervalo de dias entre a criação e o cancelamento. 


* Então realizei a subtração de cada campo e trouxe informações descritivas como média do intervalo de dias, desvio padrão e valor mínimo e máximo. 

### Informações descritivas sobre os dias entre a criação e o cancelamento da assinatura do grupo de cancelados

* Utilizando um método pandas .describe() exibi informações estatísticas sobre o intervalo. 


* Quantidade médias de dias do intervalo: 472 dias.


* Porém o desvio padrão apresentou-se alto, portanto o intervalo calculado possui uma grande quantidade de diferentes valores, logo a quantidade média de dias não é totalmente confiável.

# Tipo de versão com mais cancelamentos

* Verificação de quais versões da assinatura possuem maior número de cancelamentos.


* Atribui a uma variável de forma decrescente a quantidade de repetições de cada versão da assinatura no conjunto de status cancelado e criei um dataframe para armazenar essa informação.


* Utilizando métodos pandas foi possível exibir a quantidade de diferentes versões que estão presents no grupo de cancelamento.


* Exibi um gráfico usando as ferramentas da biblioteca plotly com a quantidade de versões que possuiam somente um cancelamento, dois cancelamentos e três cancelamentos, maior valor até então. Por fim trouxe as versões que possuiam o maior número de cancelamentos.


# Idade predominante no grupo de status cancelado

* Verificação do intervalo de idade do grupo que cancelou a assinatura.


* Então eu segui atribuindo a uma variável as datas de aniversário dos assinantes que haviam cancelado a assinatura. Realizei o cálculo da idade dos assinantes usando a biblioteca pandas, atribui a uma variável e trouxe informações descritivas como média, desvio padrão e valores minimos e maximos das idades. 


* Com base no intervalo entre as idades dos assinantes organizei as idades em 7 grupos e trouxe informações descritivas para cada um deles. Realizei o cálculo da porcentagem correspondente a cada faixa de idade sobre o total de registros com cancelamento e armazenei em uma variável. 


* Utilizando a biblioteca matplotlib exibi um gráfico com as faixas de idade e a porcentagem correspondente a cada uma dentro do grupo com status cancelado.


* Média de idade de um assinante com status cancelado: 53 anos.


* Pelo fato do desvio padrão ter se apresentado relativamente alto deve-se levar em conta que o valor da média de idade não é muito confiável.

#### Primeira faixa de idade entre 18 e 29 anos

* Total de 49 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 27 anos.

* Representa 9.7029% do grupo de cancelamentos.

#### Segunda faixa de idade entre 30 e 39 anos

* Total de 82 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 34 anos.

* Representa 16.2376% do grupo de cancelamentos.

#### Terceira faixa de idade entre 40 e 49 anos

* Total de 83 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 44 anos.

* Representa  16.4356% do grupo de cancelamentos.

#### Quarta faixa de idade entre 50 e 59 anos

* Total de 100 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 54 anos.

* Representa  19.8019% do grupo de cancelamentos.

#### Quinta faixa de idade entre 60 e 69 anos

* Total de 85 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 64 anos.

* Representa  16.8316% do grupo de cancelamentos.

#### Sexta faixa de idade entre 70 e 79 anos

* Total de 94 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 74 anos.

* Representa 18.6138% do grupo de cancelamentos.

#### Sétima e última faixa de idade entre 80 e 99 anos

* Total de 12 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 80 anos.

* Representa 2.3762% do grupo de cancelamentos.

### Organizando todo o conjunto de dados por faixas de idade

* Inicialmente armazenei em uma variável as datas de aniversário de todos os clientes.


* Realizei o cálculo da idade de cada um dos clientes e armazenei em uma variável.


*  Resolvi calcular a porcentagem de cancelamentos sobre o total de assinantes com base na faixa de idade, então atribui a uma variável todas as datas de aniversário dos assinantes, calculei a idade de cada um, separei os registros em grupos com base na idade e também trouxe informações descritivas sobre cada um deles.


* Calculei a porcentagem de cada um com base no total de registros correspondentes a sua faixa de idade, exibi uma tabela com os grupos e as porcentagens de cada um e também um gráfico usando a biblioteca plotly com a porcentagem de cada faixa com base no total de assinantes de cada grupo. 

#### Primeira faixa de idade entre 18 e 29 anos

* Total de 811 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 27 anos.

* Representa 6.0419% do total de assinantes nesta faixa de idade.

#### Segunda faixa de idade entre 30 e 39 anos

* Total de 1774 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 34 anos.

* Representa 4.6223% do total de assinantes nesta faixa de idade.

#### Terceira faixa de idade entre 40  e 49 anos

* Total de 1830 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 44 anos.

* Representa 4.5355% do total de assinantes nesta faixa de idade.

#### Quarta faixa de idade entre 50 e 59 anos

* Total de 1825 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 54 anos.

* Representa 5.4794% do total de assinantes nesta faixa de idade.

#### Quinta faixa de idade entre 60 e 69 anos

* Total de 1778 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 64 anos.

* Representa 4.7806% do total de assinantes nesta faixa de idade.

#### Sexta faixa de idade entre 70 e 79 anos

* Total de 1751 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 74 anos.

* Representa 5.3683% do total de assinantes nesta faixa de idade.

#### Sétima faixa de idade entre 80 e 99 anos

* Total de 231 pessoas que se encaixam neste grupo.

* Média da idade de uma pessoa presente neste grupo: 80 anos.

* Representa 5.1948% do total de assinantes nesta faixa de idade.

# Estados e cancelamentos de assinatura

#### Utilizando os estados extraí as seguintes informações do dataset:


* Verificação de qual região do Brasil possui o maior índice de cancelamento.
* Quais são os estados de cada região que mais possuem cancelamentos.
* Percentual de cancelamento de cada estado.
* Percentual de cancelamento por região com base no total de assinaturas por região.

### Organizando os estados por região do Brasil

* Inicialmente armazenei em uma variável a quantidade de repetições por estado no grupo de status cancelado.


* Organizando os estados utilizando a variável criada. Também foi feito o cálculo da porcentagem de aparições de cada região e armazenado em uma variável.


* Então criei um dataframe com os estados e suas repetições, essa informação foi utilizada para a exibição do gráfico.

#### Região sul

* Estado com maior número de cancelamentos dessa região: Rio Grande do Sul

* Número de estados na região: 3

* Representa 10.6930% do grupo de regiões com assinatura cancelada.

#### Região sudeste

* Estado com maior número de cancelamentos dessa região: Minas Gerais
* Número de estados na região: 4
* Representa 12.4752% do grupo de regiões com assinatura cancelada.

#### Região centro oeste

* Estado com maior número de cancelamentos dessa região: Mato Grosso
* Número de estados na região: 4
* Representa 15.8415% do grupo de regiões com assinatura cancelada.

#### Região nordeste

* Estado com maior número de cancelamentos dessa região: Sergipe
* Número de estados na região: 9
* Representa 33.2673% do grupo de regiões com assinatura cancelada.

#### Região norte

* Estado com maior número de cancelamentos dessa região: Tocantins
* Número de estados na região: 7
* Representa 27.7227% do grupo de regiões com assinatura cancelada.

#### Gráfico conforme o estado e o número de repetições dentro do grupo de status cancelado

* Fazendo uso de ferramentas da biblioteca plotly para criar o gráfico com os dados dos estados do grupo de status cancelado.


* Estado com maior número de cancelamentos do Brasil: Rio Grande do Sul


* Região com maior percentual de cancelamento: Nordeste.


* Novamente foi criado um gráfico usando a biblioteca plotly e os dados vindos das porcentagens das regiões do Brasil que existem no grupo de status cancelado.

### Percentual de cancelamentos por região com base no total de assinaturas.

* Por fim a última análise feita foi para verificar o percentual de cancelamentos de cada região com base no total de assinaturas por região também.



* Inicialmente a quantidade de repetições no dataframe para cada estado foi armazenada em uma variável. Em seguida os estados foram separados por região e então foram realizados cálculos das porcentagens de cancelamento por região além da exibição de um gráfico elaborado utilizando a biblioteca plotly com os dados vindos dos percentuais de cancelamento de cada região do Brasil levando em conta o total de assinaturas por região.


#### Região sul

* Estado com maior número de assinaturas: Paraná
* Número de estados da região: 3
* Região com 4.7493% de taxa de cancelamento.

#### Região sudeste

* Estado com maior número de assinaturas: Rio de Janeiro
* Número de estados da região: 4
* Região com 4.3269% de taxa de cancelamento.

#### Região centro oeste

* Estado com maior número de assinaturas: Goiás
* Número de estados da região: 4
* Região com 5.3262% de taxa de cancelamento.

#### Região nordeste

* Estado com maior número de assinaturas: Ceará
* Número de estados da região: 9
* Região com 5.1692% de taxa de cancelamento.

#### Região norte

* Estado com maior número de assinaturas: Tocantins
* Número de estados da região: 7
* Região com 5.2730% de taxa de cancelamento.

* Região com maior percentual de cancelamentos: Centro-Oeste.
