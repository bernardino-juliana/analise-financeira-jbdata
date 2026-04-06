# 📊 Análise Financeira - JBData

## 📌 Sobre o projeto
Este projeto tem como objetivo analisar a performance financeira da empresa fictícia **JBData**, utilizando SQL e inteligência artificial para geração de insights.

A proposta central foi explorar uma abordagem menos convencional, demonstrando que nem sempre é necessário o uso de dashboards ou ferramentas tradicionais de visualização para extrair valor dos dados.

---

## 🛠️ Ferramentas utilizadas
- MySQL (modelagem e consultas)  
- VS Code (desenvolvimento)  
- NotebookLM (apoio analítico e geração de insights)  

---
## 📚 Fontes utilizadas na análise

Para enriquecer a interpretação dos dados, o projeto utilizou diferentes tipos de fontes no NotebookLM:

- 📊 Dados estruturados:
  - clientes.csv  
  - receitas.csv  
  - despesas.csv  

- 📖 Referências teóricas:
  - Fundamentos de economia  
  - Administração e gestão  
  - Planejamento financeiro  

- 🌐 Conteúdo de mercado:
  - Artigos e relatórios sobre tendências em dados e negócios  

Essa combinação permitiu não apenas analisar os números, mas também contextualizar os resultados dentro de conceitos financeiros e práticas de mercado.

---

## 🔄 Etapas do projeto

### 1. Criação da base de dados
- Estruturação das tabelas no MySQL  
- Inserção de dados fictícios  

### 2. Análise com SQL
Principais análises realizadas:
- Receita total por período  
- Despesas por categoria  
- Cálculo de lucro líquido  
- Análise de participação das despesas  
- Comparativo entre receitas recorrentes e projetos  
- Ranking de clientes por faturamento  
- Média de despesas por categoria  
- Evolução da receita acumulada ao longo do tempo   

### 3. Geração de insights
Utilização do NotebookLM para:
- Interpretação dos dados  
- Geração de perguntas analíticas  
- Construção do relatório textual  

### 4. Comunicação dos resultados
- Criação de relatório descritivo com os principais insights  
- Desenvolvimento de infográfico com resumo da performance financeira  

---

## 🧠 Abordagem do Projeto

Este projeto foi desenvolvido com o objetivo de questionar a dependência de ferramentas tradicionais como dashboards e visualizações complexas.

A análise foi conduzida utilizando SQL como base principal e inteligência artificial como suporte interpretativo, mostrando que:

- Insights relevantes podem ser obtidos sem o uso de ferramentas visuais avançadas  
- A clareza na análise e na interpretação dos dados é mais importante do que a complexidade das ferramentas  
- O papel do analista de dados está na escolha da abordagem mais adequada para cada contexto  

👉 **Nem sempre o melhor caminho é o mais complexo — e sim o mais eficiente para responder ao problema.**

---

## 📈 Principais insights

- A estrutura de custos da empresa é fortemente concentrada em folha de pagamento, representando a maior parcela das despesas operacionais, o que pode impactar diretamente a margem em cenários de crescimento.

- O lucro líquido apresenta variação ao longo dos períodos, influenciado principalmente pela entrada de receitas pontuais (projetos), evidenciando dependência de ganhos não recorrentes.

- A receita recorrente garante previsibilidade financeira, enquanto projetos aumentam o faturamento no curto prazo, mas trazem maior volatilidade e risco operacional.

- Existe oportunidade de otimização nos custos de marketing e operacionais, visando maior eficiência na alocação de recursos.

- A análise indica a importância de equilibrar crescimento e controle de custos, evitando que o aumento da receita seja acompanhado por uma pressão desproporcional nas despesas.

- A diversificação da base de clientes e o fortalecimento de receitas recorrentes podem contribuir para maior estabilidade financeira e previsibilidade de resultados.
  
---

## 🤖 Uso de IA no projeto
O projeto utilizou o NotebookLM para:
- Exploração de hipóteses  
- Geração de insights  
- Apoio na construção do relatório  

---

## 📷 Visualizações

<img width="2752" height="1536" alt="infografico-jbdata" src="https://github.com/user-attachments/assets/40f9a123-a491-4113-a7eb-7a55dd8c423f" />


---

## 📂 Como executar

### 1. Criar o banco de dados
Abra seu MySQL e execute o script disponível em `/sql` para:
- Criar o banco de dados `jbdata`
- Criar as tabelas (`clientes`, `receitas`, `despesas`)
- Inserir os dados fictícios

---

### 2. Executar as consultas SQL
No mesmo ambiente, execute as queries disponíveis no arquivo `/sql/queries_analise.sql` para gerar:

- Receita total por período  
- Despesas por categoria  
- Lucro líquido  
- Análises complementares (clientes, tipos de receita, médias e acumulados)

---

### 3. Exportar os dados (opcional)
As tabelas podem ser exportadas em CSV utilizando os comandos `INTO OUTFILE`, conforme definido no script.

---

### 4. Análise e interpretação
Os resultados podem ser analisados diretamente no banco de dados ou utilizados como base para interpretação com apoio de IA (NotebookLM), conforme demonstrado no projeto.
