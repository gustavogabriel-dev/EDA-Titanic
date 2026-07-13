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
- Crianças tiveram vantagem sobre adultos? O sexo importou entre elas?
- A distribuição de idade difere entre sobreviventes e não sobreviventes?
- Existe um padrão mais fino de sobrevivência por faixa etária?

**Combinações de fatores**
- Sexo e classe combinados explicam melhor a sobrevivência?
- A vantagem de ser criança se mantém em todas as classes sociais?
- O porto de embarque, combinado com a classe, ainda influencia a sobrevivência?
- O padrão de sobrevivência por idade e sexo se mantém em diferentes classes?

**Família e composição do grupo**
- O tamanho da família influenciou a sobrevivência? Existe um "ponto ideal"?
- Viajar sozinho fez diferença? De forma igual para homens, mulheres e crianças?
- `sibsp` (irmãos/cônjuge) e `parch` (pais/filhos) têm efeitos diferentes entre si?

**Fatores econômicos**
- A tarifa paga influenciou a sobrevivência?
- Existem outliers relevantes na tarifa? O que eles representam?
- A tarifa "por cabeça" discrimina melhor do que a tarifa bruta?
- Pagar mais dentro da mesma classe trouxe vantagem?

**Localização e contexto**
- O porto de embarque influenciou a sobrevivência, isoladamente ou como variável de confusão?
- A idade dos passageiros varia entre classes e portos?

**Qualidade e estrutura dos dados**
- Os dados faltantes em `age` seguem algum padrão (viés por classe/sexo)?
- Existe multicolinearidade entre variáveis numéricas?
- As linhas duplicadas representam um problema real?

**Engenharia de atributos**
- É possível combinar sexo e idade numa única variável (`sex_age_score`) que discrimine melhor a sobrevivência?

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

Projeto orientado pelo professor Miguel Mochizuki.
