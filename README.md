# 🎮 Xbox Game Pass Subscriptions Sales — Dashboard & Análise de Vendas

Este repositório contém o projeto de análise de dados e dashboard interativo desenvolvido no **Microsoft Excel** (`Vendas.xlsx`), focado no acompanhamento de vendas de assinaturas do **Xbox Game Pass**, passes de temporada adicionais (*EA Play* e *Minecraft Season Pass*) e impacto de cupons promocionais ao longo de 2024.

---

## 📋 Visão Geral do Projeto

O objetivo desta planilha é consolidar a base transacional de assinantes, responder a perguntas estratégicas de negócio por meio de **Tabelas Dinâmicas** e apresentar os resultados de forma visual e intuitiva em um **Dashboard** executivo com identidade visual inspirada na marca Xbox.

### 📊 Principais Números da Base
* **Total de Registros:** 295 assinantes (`Subscriber ID` 3231 a 3525)
* **Período Analisado:** Janeiro a Dezembro de 2024
* **Faturamento Total Líquido:** $ 7.633,00
* **Planos Comercializados:** `Core` (101), `Ultimate` (98) e `Standard` (96)
* **Modalidades de Assinatura:** `Monthly` (139), `Quarterly` (85) e `Annual` (71)

---

## 🗂️ Estrutura da Planilha

O arquivo `Vendas.xlsx` está organizado em **4 abas principais**, seguindo boas práticas de modelagem e separação de camadas:

| Aba | Descrição |
| :--- | :--- |
| **`Dashboard`** | Painel visual executivo (*Xbox Game Pass Subscriptions Sales*) com indicadores-chave, gráficos e segmentadores de dados (*Slicers*) para filtragem dinâmica. |
| **`Cálculos`** | Camada intermediária contendo **Tabelas Dinâmicas** (`tbl_annual_total`, `tbl_easeasonpass_total`, `Tabela dinâmica3`) e funções `GETPIVOTDATA` que respondem às perguntas de negócio e alimentam o dashboard. |
| **`B̳ases`** | Base de dados estruturada como Tabela oficial do Excel (`Tabela1`), contendo os 295 registros de vendas, preços, add-ons e descontos aplicados. |
| **`A̳ssets`** | Guia de estilo e recursos visuais do projeto, contendo a paleta de cores oficial em hexadecimal (`#9BC848`, `#22C55E`, `#2AE6B1`, `#5BF6A8`, `#E8E6E9`), logos e ícones utilizados na interface. |

---

## 🧾 Dicionário de Dados (`B̳ases`)

| Coluna | Tipo | Descrição |
| :--- | :--- | :--- |
| `Subscriber ID` | Numérico | Identificador único do assinante. |
| `Name` | Texto | Nome completo do cliente. |
| `Plan` | Categórico | Nível do plano contratado (`Core`, `Standard`, `Ultimate`). |
| `Start Date` | Data | Data de início da assinatura (2024). |
| `Auto Renewal` | Booleano (`Yes`/`No`) | Indica se a renovação automática está ativada. |
| `Subscription Price` | Moeda | Valor base do plano contratado ($5, $10 ou $15). |
| `Subscription Type` | Categórico | Ciclo de cobrança (`Monthly`, `Quarterly`, `Annual`). |
| `EA Play Season Pass` | Booleano (`Yes`/`No`) | Indica contratação adicional do passe EA Play. |
| `EA Play Season Pass Price` | Moeda / Texto | Valor do passe EA Play ($30 quando contratado ou `-`). |
| `Minecraft Season Pass` | Booleano (`Yes`/`No`) | Indica contratação adicional do passe Minecraft. |
| `Minecraft Season Pass Price` | Moeda | Valor do passe Minecraft ($20 quando contratado ou $0). |
| `Coupon Value` | Moeda | Valor do desconto aplicado via cupom promocional. |
| `Total Value` | Moeda | Receita líquida final da venda (`Assinatura + Add-ons - Cupom`). |

---

## 💡 Perguntas de Negócio Respondidas (`Cálculos`)

A aba de cálculos estrutura análises específicas para apoiar a tomada de decisão comercial:

1. **Faturamento por Ciclo e Renovação Automática:** Comparação do volume financeiro gerado entre assinantes que mantêm o `Auto Renewal` ativo versus inativo (ex.: no recorte trimestral, assinaturas com renovação automática geram **$ 1.502** contra **$ 806** sem renovação automática).
2. **Receita de Add-on — EA Play Season Pass:** Levantamento do faturamento gerado pelo passe adicional do EA Play segmentado por tipo de plano (concentrado nos assinantes do plano `Ultimate`).
3. **Receita de Add-on — Minecraft Season Pass:** Levantamento do faturamento gerado pelo passe adicional do Minecraft segmentado por tipo de plano (`Standard` e `Ultimate`).

---

## 🛠️ Recursos e Técnicas Utilizadas (Excel)

* **Tabelas Estruturadas (`Tabela1`):** Garante integridade referencial e expansão automática do intervalo de dados.
* **Tabelas Dinâmicas & Segmentação de Dados (*Slicers*):** Permitem fatiar os indicadores por tipo de assinatura (`Subscription Type`) e planos.
* **Fórmulas Dinâmicas (`GETPIVOTDATA` / `INFODADOSTABELADINÂMICA`):** Extração segura de totais consolidados das tabelas dinâmicas para os cartões e resumos.
* **UI/UX Design em Planilhas:** Uso de guia de estilo dedicado (`A̳ssets`) com paleta de cores temática e ícones personalizados para melhor legibilidade executiva.

---

## 🚀 Como Utilizar

1. Faça o download do arquivo `Vendas.xlsx` neste repositório.
2. Abra o arquivo utilizando o **Microsoft Excel** (recomendado versão 2019, 2021 ou Microsoft 365 para suporte completo às segmentações de dados e recursos visuais).
3. Caso adicione novos registros na aba **`B̳ases`**, vá até a guia **Dados > Atualizar Tudo** (`Ctrl + Alt + F5`) para recalcular automaticamente as Tabelas Dinâmicas e o Dashboard.

---

## 👤 Autor

Desenvolvido por **[Seu Nome](https://github.com/seu-usuario)** — Projeto de Análise de Dados & Business Intelligence com Excel.
