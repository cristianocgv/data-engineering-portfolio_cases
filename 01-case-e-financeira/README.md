# Case 01 - Consolidação de Dados para E-Financeira

## 📋 Objetivo

Este projeto apresenta um case de Engenharia de Dados desenvolvido para consolidar informações financeiras destinadas ao processo de geração da **E-Financeira**.

O objetivo foi construir uma camada Gold consolidando dados provenientes de diferentes sistemas Core Banking, disponibilizando informações padronizadas, consistentes e prontas para consumo por processos regulatórios.

> **Observação:** Este projeto utiliza dados fictícios e estruturas anonimizadas, preservando informações confidenciais.

---

# Contexto do Problema

As informações necessárias para geração da E-Financeira estavam distribuídas entre diferentes sistemas Core Banking.

Cada sistema possuía suas próprias estruturas de dados, tornando necessário consolidar informações financeiras em uma única visão.

Para isso, foi necessário realizar cruzamentos entre diferentes domínios de dados, como:

- Cadastro de clientes
- Contas
- Saldos
- Movimentações financeiras
- Rendimentos
- Relacionamento entre titulares

Após as transformações, os dados foram disponibilizados na camada **Gold**, pronta para consumo.

---

# Arquitetura da Solução

```text
                Core Banking 1
                      │
                      │
                Camada Silver
                      │
                Regras de Negócio
                      │
                Camada Gold
                      │
          Sistema Consumidor
```

---

# Tecnologias Utilizadas

- Databricks
- Apache Spark
- PySpark
- SQL
- Delta Lake
- Git

---

# Regras de Negócio

Durante o processamento foram implementadas regras para:

- Consolidação de informações provenientes de diferentes sistemas Core Banking.
- Padronização de cadastros.
- Consolidação de movimentações financeiras.
- Cálculo do saldo do último dia do período.
- Consolidação dos valores de débitos.
- Consolidação dos valores de créditos.
- Identificação de movimentações entre contas de mesma titularidade.
- Consolidação dos rendimentos.
- Geração da camada Gold para consumo.

---

# Modelo da Camada Gold

| Campo | Descrição |
|--------|-----------|
| COOP | Cooperativa |
| CPF_CNPJ | Documento do cliente |
| RELACAO_DECLARADO | Relação do titular |
| OPERACAO | Número da operação |
| TIPO_CONTA | Tipo da conta |
| VLR_ULTIMO_DIA | Saldo no último dia |
| VLR_TOTAL_DEBITOS | Total de débitos |
| VLR_TOTAL_DEBITOS_MESMA_TITUL | Débitos entre contas do mesmo titular |
| VLR_TOTAL_CREDITOS | Total de créditos |
| VLR_TOTAL_CREDITOS_MESMA_TITUL | Créditos entre contas do mesmo titular |
| VLR_PGTO_ACUMULADOS | Rendimentos acumulados |
| ANO_MES_CAIXA | Competência |

---

# Resultado

A solução permitiu consolidar dados financeiros provenientes de diferentes sistemas em uma estrutura padronizada, garantindo qualidade, consistência e rastreabilidade das informações utilizadas em processos regulatórios.

---

# Próximos Arquivos

Este projeto também contém:

- 📄 Massa de dados fictícia
- ⚙️ Pipeline PySpark
- 📊 Exemplo da camada Gold