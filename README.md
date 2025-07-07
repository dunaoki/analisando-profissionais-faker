# analisando-profissionais-faker

Esse repositorio foi criado com nomes faker conforme a lei n 13.709/2018 (LGPD)

# 📊 Análise de Atendimentos por Profissionais de Saúde (17h às 21h)

Este repositório contém uma análise exploratória de dados dos atendimentos realizados por profissionais de saúde , com foco específico no período entre **17h e 21h**.

## 🔍 Objetivo

O objetivo principal é identificar:
- Quais profissionais atuaram no período das 17h às 21h;
- Quantas vezes cada profissional atendeu nesse intervalo;
- Visualizar os resultados em gráficos claros e informativos.

## 🛠️ Ferramentas Utilizadas

- **Python 3**
- **Pandas** para manipulação dos dados
- **Matplotlib** para criação dos gráficos
- **Jupyter Notebook** (ambiente de análise)
- **FPDF** + **Pillow** para montagem do relatório em PDF

## 📁 Estrutura dos Dados

As colunas consideradas após limpeza dos dados:

- `data_atendimento` – Data e hora do atendimento
- `profissional` – Nome do profissional de saúde
- Demais colunas auxiliares foram excluídas para clareza da análise

### 3. Anonimização dos Dados

Por questões éticas e legais, os nomes dos profissionais foram substituídos por identificadores fictícios.

**Código exemplo:**

```python
python
import random

nomes_reais = df['profissional'].unique()
nomes_ficticios = [f"Dr(a). Nome {i}" for i in range(len(nomes_reais))]
df['profissional'] = df['profissional'].map(dict(zip(nomes_reais, nomes_ficticios)))

```

## 🧼 Pré-processamento

1. Conversão de colunas de data (`datetime`)
2. Extração da hora do atendimento (`.dt.hour`)
3. Filtro aplicado para selecionar apenas registros entre 17h e 21h
4. Agrupamento por profissional e contagem de atendimentos

## 📈 Resultados

- Foi gerado um gráfico de barras com:
  - Quantidade absoluta de atendimentos por profissional
  - Porcentagem relativa
  - Identificação visual clara dos profissionais mais ativos

📎 O relatório completo em PDF pode ser acessado no arquivo:  
[`Relatorio_Pesquisa_Saude_Garopaba_Alta_Qualidade.pdf`](Relatorio_Pesquisa_Saude_Garopaba_Alta_Qualidade.pdf)

## 🧠 Observações

- Dois profissionais não apareceram inicialmente na análise por problemas na padronização dos nomes (valores nulos ou inconsistentes).
- A análise considera somente os atendimentos com hora registrada corretamente.

## 📌 Próximos passos (opcional)

- Cruzar com dados de tipo de atendimento ou unidade
- Análise por dia da semana
- Dashboards interativos (ex: Power BI ou Streamlit)

---

> Desenvolvido por [Eduardo Watanabe] — Projeto de aprendizado em análise de dados com Python.
