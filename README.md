# 📊 Análise Estatística e Rentabilidade de Planos de Telecomunicações (Megaline)

## 📌 Contexto do Projeto

A empresa de telecomunicações **Megaline** oferece aos seus clientes dois planos pré-pagos principais: **Surf** e **Ultimate**.

Para otimizar os investimentos e ajustar o orçamento de publicidade para o próximo período fiscal, o departamento comercial precisa identificar qual dos dois planos pré-pagos gera maior receita para a empresa.

Para responder a essa demanda de negócio, foi realizada uma análise com base em uma amostra de **500 clientes** da Megaline. Os dados coletados abrangem todo o ano de **2018** e contêm informações detalhadas sobre:

- **Perfil dos Clientes:** idade, cidade de residência e informações cadastrais.
- **Uso de Planos:** plano pré-pago contratado por cada cliente (Surf ou Ultimate).
- **Atividade Operacional:** volume de chamadas telefônicas, quantidade de mensagens SMS enviadas e consumo mensal de dados móveis.

---

## 🎯 Objetivo do Negócio

- **Determinar qual plano pré-pago (Surf ou Ultimate) gera maior receita** total e média para a empresa.
- **Analisar o comportamento de consumo** dos clientes em relação a minutos, mensagens e internet móvel, identificando a influência das mensalidades e das cobranças por excedentes de franquia.
- **Subsidiar decisões comerciais** relacionadas à alocação e ao direcionamento do orçamento de campanhas publicitárias.

---

## 📁 Estrutura do Conjunto de Dados

O estudo utiliza dados do ano de 2018 distribuídos nas seguintes tabelas:

1. **`users` (Usuários):** dados cadastrais dos 500 clientes, incluindo identificação, idade, cidade de residência, data de assinatura e cancelamento do plano.
2. **`calls` (Chamadas):** histórico de chamadas realizadas, com data, duração e identificação do usuário.
3. **`messages` (Mensagens):** registros de SMS enviados, com data e identificação do usuário.
4. **`internet` (Tráfego de Dados):** sessões de acesso à internet móvel, com volume consumido, data e identificação do usuário.
5. **`plans` (Regras dos Planos):** informações sobre mensalidades, franquias e tarifas adicionais de cada modalidade:
   - **Plano Surf:** mensalidade de US$ 20, franquia de 500 minutos, 50 SMS e 15 GB de internet. Tarifas excedentes de US$ 0,03 por minuto, US$ 0,03 por SMS e US$ 10 por GB.
   - **Plano Ultimate:** mensalidade de US$ 70, franquia de 3.000 minutos, 1.000 SMS e 30 GB de internet. Tarifas excedentes de US$ 0,01 por minuto, US$ 0,01 por SMS e US$ 7 por GB.

---

## 🛠️ Etapas do Desenvolvimento

### 1. Pré-processamento e Limpeza

- Conversão de tipos de dados, incluindo datas para `datetime`.
- Tratamento de valores ausentes e inconsistências.
- Arredondamento dos minutos de chamadas e do consumo de internet conforme as regras de faturamento dos planos.

### 2. Engenharia de Atributos e Agregação

- Agrupamento mensal do consumo de cada cliente, considerando minutos de chamadas, mensagens enviadas e gigabytes utilizados.
- Cálculo da **receita mensal por cliente**, somando a mensalidade fixa e os valores adicionais cobrados quando as franquias são ultrapassadas.

### 3. Análise Exploratória e Testes de Hipóteses

- Comparação das distribuições de consumo dos planos Surf e Ultimate, utilizando média, mediana, desvio padrão e variância.
- Criação de gráficos para visualizar padrões de consumo e diferenças entre os grupos.
- Aplicação de **testes t de Student para amostras independentes** para investigar:
  1. Se existe diferença estatisticamente significativa entre a receita média dos usuários dos planos Surf e Ultimate.
  2. Se existe diferença estatisticamente significativa entre a receita média dos usuários da região de NY-NJ e a dos usuários de outras regiões.

---

## 🚀 Tecnologias Utilizadas

- **Python:** linguagem utilizada para desenvolver a análise.
- **Pandas:** limpeza, manipulação e agregação dos dados.
- **NumPy:** operações matemáticas e computação numérica.
- **Matplotlib e Seaborn:** criação de gráficos e visualização das distribuições.
- **SciPy (`scipy.stats`):** aplicação de testes estatísticos de hipóteses.

---

## 📈 Resultados Obtidos e Conclusões

1. Padrões de Consumo dos Clientes

Internet móvel: os clientes do plano Surf apresentam maior ocorrência de cobranças por excedentes de franquia, especialmente no consumo de dados móveis. Já os clientes do plano Ultimate contam com uma franquia maior, de 30 GB, reduzindo a ocorrência dessas cobranças.

Minutos e mensagens: a análise permite comparar o consumo desses serviços com os limites incluídos em cada plano e identificar possíveis cobranças adicionais.

2. Resultados dos Testes Estatísticos

Receita média por plano: o teste de hipótese identificou uma diferença estatisticamente significativa entre a receita média dos usuários dos planos Surf e Ultimate ((p < 0{,}05)).

A receita mensal média dos usuários do plano Ultimate foi de aproximadamente US$ 72,12, enquanto a dos usuários do plano Surf foi de aproximadamente US$ 57,29.

Diferença regional (NY-NJ vs. outras regiões): o teste de hipótese identificou uma diferença estatisticamente significativa entre as receitas médias dos clientes da região metropolitana de NY-NJ e as dos clientes das demais regiões ((p \approx 0{,}0261)). Como o valor-p é inferior ao nível de significância de 0,05, rejeita-se a hipótese nula de igualdade das médias.

3. Recomendação Comercial

Direcionamento de Marketing: com base nos resultados da análise, recomenda-se considerar campanhas publicitárias para o plano Ultimate caso o objetivo seja aumentar a receita média por cliente. O Ultimate apresentou maior receita média mensal por usuário, enquanto o Surf possui uma mensalidade mais acessível e pode gerar receita adicional com cobranças excedentes. A decisão final de investimento também deve considerar os custos operacionais, a aquisição de clientes e o potencial de conversão de cada plano.

📌 Considerações Finais

A análise dos dados dos 500 clientes da Megaline permitiu comparar os padrões de consumo e a receita gerada pelos planos pré-pagos Surf e Ultimate ao longo de 2018.

Os resultados mostraram que o plano Ultimate apresentou maior receita média mensal por usuário, de aproximadamente US$ 72,12, em comparação aos US$ 57,29 do plano Surf. Os testes estatísticos também identificaram diferenças significativas entre as receitas médias dos dois planos e entre os clientes da região de NY-NJ e os das demais regiões.

Com base nesses resultados, o estudo demonstra como a análise exploratória, a visualização de dados e os testes de hipóteses podem apoiar decisões comerciais e o direcionamento de campanhas publicitárias.