# 💊 Análise de Gasto de Medicamentos e Insumos Hospitalares por Região do Brasil (2023–2024)

Este projeto analisa dados públicos de compras realizadas por municípios brasileiros com foco em medicamentos e insumos hospitalares. Ele abrange os anos de 2023 e 2024, com o objetivo de gerar insights sobre os padrões de consumo e apoiar o planejamento estratégico em saúde pública.

---

## 🔧 Tecnologias Utilizadas

- **Python** (pandas, numpy, matplotlib, Seaborn, Html)
- **Power BI**
- **Jupyter Notebook**
- **Git e GitHub**

---

## 📁 Estrutura do Projeto

- `dados/` → Base original (.xlsx)
- `notebooks/` → Scripts de limpeza e tratamento de dados
- `dashboard/` → Arquivo Power BI (.pbix)
- `imagens/` → Prints do dashboard
- `README.md` → Documentação do projeto

---

## 🧼 Tratamento e Limpeza dos Dados

Durante a preparação dos dados em Python, as seguintes etapas foram realizadas:

-  **Tamanho inicial do banco de dados:** linhas: 62.159 
-  **Tamanho após o tratamento:** linhas: 35.707

### ✅ Transformações Aplicadas

- **Leitura e concatenação das duas planilhas** referentes a 2023 e 2024 que estavam em abas separadas no arquivo Excel
- Padronização e **tratamento de títulos/nomes de colunas**
- Classificação dos tipos das colunas (ex.: `float`, `int`, `str`, `datetime`)
- Remoção de duplicatas
- Criação das colunas:
  - **`Nome do Produto`** (extração da primeira palavra a partir da coluna Descrição)
  - **`Classificação`** (diferenciação entre medicamentos e insumos hospitalares)
  - **`Região`** (com base no estado do município)
  - **`País`** (todos os dados referem-se ao Brasil, adicionado para fins de modelagem)
- **Tratamento de nulos**:
  - Filtro de CNPJs para obter o nome da instituição com base em registros posteriores da mesma entidade
  - Preenchimento de **linhas vazias** nas colunas instituição e Unidade Fornecida
- **Normalização de casas decimais** para valores unitários (ex.: `0.0` convertido para `0.005`)
- Tratamento de **problemas de encoding** (palavras cortadas ou com caracteres inválidos)
- Padronização de nomes de colunas e categorias
- **Verificação de estatísticas descritivas** do dataset
- Detecção de **outliers com o método IQR (Intervalo Interquartil)**:
  - Apesar de identificar outliers (valores muito baixos ou altos), optou-se por **mantê-los**, considerando que a natureza do dataset (medicamentos) justifica essa variação extrema de preços

---

## 📊 Visualização - Dashboard Power BI
- **Visão geral das compras por região**
- **Gráficos de barras e colunas** para comparar fornecedores e tipos de produtos
- **Indicadores e cartões** com totais agregados e percentuais
- **Segmentações (slicers)** por Estado, município, fornecedor e substância

### 🧮 Medidas DAX criadas:

- **Soma Total de Compras (`Preço Total`)**
- **Preço Médio dos Produtos**  



