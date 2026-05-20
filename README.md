# 🔹 Loja Virtual Industrial & Monitoramento SCADA (SFRC)

Este projeto consiste num ecossistema integrado para a **Indústria 4.0**, unindo uma plataforma de e-commerce de componentes industriais a um sistema de monitorização e controlo em tempo real (SCADA).

<div align="center">
  <br/>
  <img src="https://img.shields.io/badge/STATUS%20DO%20PROJETO-CONCLUÍDO-0078D4?style=for-the-badge" alt="Status">
  <br/><br/>
  <h2>🖥️ Loja Virtual & Dashboard SCADA Online</h2>
  <p>Explore a interface de monitoramento industrial em tempo real.</p>
  <a href="https://henrique-lima7.github.io/Loja-Virtual-Industrial-com-Dashboard--SCADA/" target="_blank">
    <img src="https://img.shields.io/badge/VISITAR%20O%20SITE%20AGORA-0078D4?style=for-the-badge&logo=microsoftedge&logoColor=white" alt="Link do Site" height="45">
  </a>
  <br/><br/>
</div>

---

## ⚙️ Sobre o Projeto

O sistema **SFRC (Squad de Alto Desempenho)** foi desenvolvido para simular o ciclo de vida completo de um produto industrial: desde a venda no marketplace até ao fabrico automatizado no chão de fábrica, com monitorização de sensores críticos.

---

## 🗺️ Fluxo de Funcionamento

| Etapa | Módulo / Arquivo | Descrição da Operação |
| :--- | :--- | :--- |
| **🔹 1** | **Marketplace** (`index.html`) | Interface para compra de componentes. Se o stock baixar de um nível crítico, uma Ordem de Produção (OP) é gerada automaticamente via API. |
| **🔹 2** | **Backend** (`main.py`) | Desenvolvido em **FastAPI**, gere as rotas, a base de dados e a comunicação integrada entre os módulos. |
| **🔹 3** | **Simulador CLP** (`simulador_clp.py`) | Script Python que atua como um controlador lógico programável, processando as ordens pendentes e gerando telemetria realística. |
| **🔹 4** | **Dashboard SCADA** (`dashboard.html`) | Painel de controlo com gráficos em tempo real (Chart.js), visualização de ativos e botões de comando operacional (Emergência/Reset). |
| **🔹 5** | **Autenticação** (`login.html`) | Sistema de acesso seguro via **Firebase** com distinção de acessos entre Perfil de Cliente e Perfil de Operador. |

---

## 🚀 Funcionalidades em Destaque

* 📈 **Reposição Automática:** Botão no Dashboard que identifica produtos com stock baixo (< 50 unidades) e inicia a produção em lote de forma autônoma.
* 📈 **Telemetria Avançada:** Monitorização em tempo real de Temperatura, Vibração, Consumo Energético e Ciclo de Máquina através de painéis gráficos.
* 📈 **Interrupção de Emergência:** Comando remoto de segurança que trava o simulador Python instantaneamente via protocolo HTTP.
* 📈 **Identificação de Ativos:** O sistema deteta o ID do produto em linha e carrega dinamicamente a imagem e a respectiva ficha técnica industrial.

---

## 🛠️ Tecnologias Utilizadas

<div align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
  <img src="https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black" />
</div>

<br/>

* **Linguagem:** Python 3.10+
* **Framework Web:** FastAPI (Uvicorn)
* **Base de Dados:** MySQL
* **Frontend:** HTML5, CSS3, JavaScript (ES6+)
* **Gráficos:** Chart.js
* **Autenticação:** Firebase Realtime Database
* **Automação de E-mail:** Make.com (Webhooks)

---

## 🔧 Como Executar

### 1. Preparar a Base de Dados
Crie a estrutura no seu MySQL local e execute o comando para preparar a tabela de telemetria:
```sql
CREATE DATABASE sfrc_db;
USE sfrc_db;

ALTER TABLE maquinas_telemetria ADD COLUMN produto_id INT;
