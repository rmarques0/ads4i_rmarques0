**Neste projeto, almejamos prever o consumo elétrico industrial da região Sudeste para os próximos 24 meses**

# Conclusões

### Modelagem
Conheci a biblioteca PyCareti há poucos dias, quando me deparei com um compartilhamento dessa no LinkedIn. Achei uma proposta bastante interessante e aproveitei o desafio para colocar em prática esse novo conhecimento. A utilização dessa biblioteca possibilitou automatizar boa parte da modelagem, e principalmente na comparação entre os modelos. Outros modelos mais robustos são possíveis, porém optei por utilizar somente os algorítimos já presentes no pacote. 
[Documentação da biblioteca](https://pycaret.org/guide/)
<br><br>

### Comparação entre modelos
Apesar de disponibilizar vários parâmetros, optei por selecionar os modelos de acordo com o Mean Absolute Error de cada um. Essa ja é uma medida comumente utilizada e ofereceu os melhores resultados diante dos testes realizados. Essa função também já nos possibilita *rankear* os resultados e criar um objeto com os melhores algorítimos.
<br><br>

### Variáveis explicativas
A seleção das variáveis foi realizada em algumas etapas:
1. Comparação da mesma medida consumo industrial da região Sudeste com as demais.
2. Comparação entre o consumo industrial e consumo das outras categorias, somente para a região Sudeste.
3. Matriz de correlação com todas as variáveis do dataset, separadas em subdatasets por região.
4. Expertise e sensibilidade no assunto relacionado.

Na análise das variáveis, percebemos que poucas medidas estão fortemente correlacionadas com o consumo industrial da região Sudeste, são elas: 
- ind_ne (alto), 
- pin_ne (moderado)
- pim_s (alto)

Como resultado do treinamento dos modelos, as variáveis de maior importância, em ordem decrescente, são:
- pim_se
- ind_ne
- data_tidy_month_4
- du
- month
<br><br>

# Resultados
- Como esperado, a Produção Industrial da Região Sudeste tem, obviamente, forte influência no consumo elétrico da categoria. 
- As crises de 2008 e 2020 são situações bem atípicas e refletem um cenário caótico dos perfis de consumo, porém para o ano de 2020 a simulação ficou bem próxima ao realizado.
- Outro ponto que se destaca é a influência do mês de Abril no consumo elétrico industrial. Talvez por influência das temperaturas, ou proximidade com período de férias. Esse ponto deverá ser melhor analizado em passos futuros. 
- Como o consumo elétrico no brasil é bastante influenciado pelo mês do ano (devido a feriados, comemorações, comportamentos em massa), é possivel observar essa influência (moderada) também para o perfil do consumo estudado.
![forecast.png](https://github.com/rmarques0/ads4i_rmarques0/raw/master/forecast.png)
<br><br>

# Próximos passos

Por se tratar de uma análise mais preliminar de um assunto complexo e com inúmetras variáveis passíveis de ser consideradas, já é possivel apontar alguns passos para melhorar a análise.

- Fazer o estudo utilizando um intervalo maior de datas.
- Incorporar informações como: 
  - Estação do ano
  - Índices econômicos:  *PIB, Taxa de Desemprego, IPI – Índice de Produção Industrial, IPPI – Índice de Preços na Produção Industrial, VN (ou IVVN) – Índice de Volume de Negócios, IE (ou INPS) – Índice de Emprego (número de pessoas ao serviço), IR (ou IREM) – Índice de Remunerações,
IHT (ou IHOR) – Índice de horas trabalhadas.*
  - Consumo por setor
- Stadização dos dados: 
  - Sazonalidade
  - Série estacionária
- Testar diferentes técnicas de processamento de dados e modelos de aprendizagem
