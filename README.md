# Análise Exploratória de Dados - Titanic

Análise exploratória de dados (EDA) do clássico dataset do Titanic, investigando quais fatores — sexo, classe social, idade, composição familiar, tarifa paga, porto de embarque, entre outros — influenciaram a taxa de sobrevivência dos passageiros.

Projeto desenvolvido como parte da disciplina de Ciência de Dados, no primeiro semestre do curso de Ciência da Computação (UFPB), sob orientação do professor Miguel Mochizuki.

## Sobre o dataset

Os dados utilizados são o dataset `titanic` embutido na biblioteca `seaborn`, uma versão simplificada e já tratada do dataset original disponibilizado no Kaggle (891 passageiros, 15 colunas).

## Perguntas de pesquisa

A análise foi guiada por perguntas organizadas em blocos temáticos:

**Fatores individuais**
- O sexo do passageiro influenciou a sobrevivência?
- A classe social influenciou a sobrevivência?
- Crianças tiveram vantagem sobre adultos?
- Entre as crianças, o sexo também influenciou na taxa de sobrevivência?
- A distribuição de idade foi diferente entre sobreviventes e não-sobreviventes?
- A sobrevivência varia entre diferentes faixas etárias (não só criança/adulto)?
- Dentro de cada faixa etária, houve alguma diferença na taxa de sobrevivência dependendo do sexo?

**Combinações de fatores**
- Sexo e classe combinados explicam melhor a sobrevivência?
- A vantagem de ser criança se mantém em todas as classes sociais, ou só nas mais altas?
- O local de embarque, quando combinado com a classe social, ainda influencia a sobrevivência?
- A vantagem de sobrevivência por idade e sexo se mantém em diferentes classes sociais?
- Viajar sozinho influenciou a sobrevivência de forma diferente entre homens, mulheres e crianças?
- A tarifa paga variou entre homens e mulheres dentro da mesma classe social?

**Família e composição do grupo**
- O tamanho das famílias influenciou na sobrevivência dos indivíduos?
- Antes de tirar conclusões: os grupos de tamanho de família têm amostra suficiente?
- Viajar sozinho influenciou a sobrevivência, independente do tamanho da família?
- `sibsp` (irmãos/cônjuge) e `parch` (pais/filhos) têm efeitos diferentes entre si na sobrevivência?
- O tamanho ideal de família (o "ponto ideal" observado) se mantém dentro de cada classe social?
- O tamanho da família teve o mesmo efeito para homens e mulheres?

**Fatores econômicos**
- A tarifa paga (`fare`) influenciou a sobrevivência?
- A tarifa tem outliers relevantes? O que eles representam?
- A tarifa "por cabeça" (`fare` dividido pelo tamanho da família) discrimina melhor do que a tarifa bruta?
- A tarifa média variou entre as diferentes classes sociais?
- Passageiros que pagaram tarifas mais altas dentro da mesma classe tiveram vantagem na sobrevivência?

**Localização e contexto**
- O local de embarque influenciou na taxa de sobrevivência?
- Qual a composição de classes sociais em cada porto de embarque?
- A idade dos passageiros varia entre as classes sociais?
- A idade dos passageiros também variou por porto de embarque?

**Qualidade e estrutura dos dados**
- Os dados faltantes em `age` estão distribuídos aleatoriamente entre os grupos, ou há um padrão?
- Existe correlação entre as variáveis numéricas que sugere redundância de informação (multicolinearidade)?
- Existem linhas duplicadas no dataset? Isso é um problema real ou uma limitação estrutural dos dados?

**Engenharia de atributos**
- É possível criar variáveis (features) que capturem melhor o padrão de sobrevivência, combinando sexo e idade?

## Principais achados

- **Sexo foi o fator individual mais forte**: mulheres tiveram 74,2% de sobrevivência contra 18,9% dos homens.
- **Classe social teve peso relevante, mas não superou o sexo**: um homem de 1ª classe teve taxa menor que uma mulher de 3ª classe.
- **"Mulheres e crianças primeiro" funcionou como duas regras distintas**: crianças pequenas foram protegidas independente do sexo; a partir da adolescência, a vantagem feminina se torna dominante.
- **Tamanho de família ideal**: famílias pequenas/médias (até 4 pessoas) tiveram vantagem; famílias muito grandes ou viajar sozinho reduziram a sobrevivência.
- **Tarifa e classe estão fortemente ligadas à sobrevivência**, inclusive quando normalizadas por pessoa.
- **Porto de embarque é uma variável de confusão**: seu efeito aparente é explicado pela composição de classes sociais em cada porto.
- **Dados faltantes em `age` não são aleatórios**: concentram-se mais na 3ª classe, sugerindo viés na coleta original.

## Tecnologias utilizadas

- Python 3
- Jupyter Notebook
- pandas
- seaborn
- matplotlib
- numpy

## Estrutura do projeto

```
.
├── eda_titanic.ipynb   # Notebook principal com toda a análise
└── README.md
```

## Como executar

```bash
# clonar o repositório
git clone <url-do-repo>
cd <nome-do-repo>

# criar ambiente virtual (opcional, mas recomendado)
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# instalar dependências
pip install pandas seaborn matplotlib numpy jupyter

# abrir o notebook
jupyter notebook eda_titanic.ipynb
```

## Status

🚧 Em desenvolvimento — algumas seções ainda podem receber ajustes e refinamentos.

## Autor

Gustavo — estudante de Ciência da Computação (UFPB)
