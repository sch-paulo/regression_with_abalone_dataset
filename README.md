# Previsão de Idade de Abalone 🐚🔍

Nesta competição, o objetivo foi prever a idade de moluscos (abalones) com base em várias medidas físicas. A determinação da idade do abalone tradicionalmente envolve um processo tedioso de cortar a concha, tingi-la e contar manualmente o número de anéis sob um microscópio. No entanto, pretendemos usar técnicas de aprendizado de máquina para prever a idade usando medidas mais acessíveis, como dimensões da concha e pesos.

## Sobre a Competição

- [Link para a competição](https://www.kaggle.com/c/playground-series-s4e4/overview)
- **Métrica de Avaliação**: Erro Médio Quadrático Logarítmico (RMSLE)
- **Formato de Submissão**: Arquivo CSV com o número de anéis (Rings) previstos para cada id no conjunto de teste

## Métrica de Avaliação

O RMSLE é calculado usando a fórmula:

![image](https://github.com/sch-paulo/regression_with_abalone_dataset/assets/132720763/3b2b070a-1a90-4de7-a4f0-ee9a7a51b528)

Onde:
- *n* é o número total de observações no conjunto de teste
- *y^* é o valor previsto do alvo para a instância *i*
- *y* é o valor real do alvo para a instância *i*

## Informações do Conjunto de Dados

### Atributos

| Nome           | Tipo de Dados | Descrição                                           |
|----------------|---------------|-----------------------------------------------------|
| id             | Discreto      | Identificação única do animal                       |
| Sex            | Nominal       | M (Masculino), F (Feminino), I (Infantil)           |
| Length         | Contínuo      | Comprimento da concha                               |
| Diameter       | Contínuo      | Diâmetro perpendicular ao comprimento               |
| Height         | Contínuo      | Altura com carne na concha                          |
| Whole weight   | Contínuo      | Peso total do abalone                               |
| Whole weight.1 | Contínuo      | Peso da carne                                       |
| Whole weight.2 | Contínuo      | Peso das vísceras após sangramento                  |
| Shell weight   | Contínuo      | Peso da concha após secagem                         |
| Ring           | Contínuo      | Número de anéis (para a idade em anos adicionar 1,5)|

## Notebook

Todo o processo de **importação das bibliotecas e dados**, **análise exploratória univariada e bivariada** e **modelagem** podem ser conferidos em ``abalone_regression.ipynb``.
Foram testados os algoritmos de *CatBoost*, *Decision Tree*, *LightGBM* e *XGBoost*. O modelo de *Decision Tree* obteve o melhor desempenho e por isso foi o escolhido para realizar a previsão dos dados para a submeter a tentativa.

## Resultados

O modelo criado obteve score de **0.15511** e ficou no ranking **1823**.
