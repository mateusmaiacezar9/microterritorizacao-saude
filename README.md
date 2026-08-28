# Sistema de Microterritorização e Gestão de Equipes de Saúde (UBS)

## 📌 Contexto e Justificativa
Este projeto nasceu de uma necessidade real na gestão da Atenção Básica de Saúde no município de Sarandi, Paraná. O desafio original consistia na validação precisa de endereços de cidadãos para direcioná-los à Equipe de Saúde da Família (ESF) correta, evitando sobrecarga em agendas médicas de certas unidades, esvaziamento em outras e conflitos de agendamento na ponta (recepção e Agentes Comunitários de Saúde).

A evolução das ferramentas utilizadas ilustra a jornada de melhoria contínua da aplicação:
1. **Google My Maps:** Utilizado inicialmente de forma geométrica, porém a imprecisão espacial gerava erros frequentes e divergências no endereçamento.
2. **Planilha em LibreOffice Calc:** Uma tentativa descentralizada onde faixas numéricas de ruas eram cadastradas. No entanto, por ser um arquivo editável local, o uso incorreto por operadores corrompia fórmulas, exigindo resgates constantes da versão original.
3. **Aplicação Web Estática (Rede Interna / Windows Server):** Migração para um ambiente web hospedado na intranet para travar edições indevidas. Porém, com alta rotatividade de pessoal e redimensionamentos populacionais frequentes entre as microáreas (somando dezenas de ACSs distribuídos em unidades de saúde), a dependência do setor de TI/manutenção para alterações manuais tornou-se um gargalo operacional.

---

## 🎯 Objetivo do Projeto
Desenvolver uma aplicação web centralizada, eficiente e segura para a consulta de microterritorização em unidades básicas de saúde, permitindo:
- **Consulta Pública e Rápida:** Atendimento ágil para funcionários da recepção e suporte à população.
- **Gestão Descentralizada por Unidade:** Autonomia para que cada UBS atualize suas próprias faixas de ruas e microáreas de forma controlada.
- **Segurança da Informação e Privacidade (LGPD):** Proteção dos dados pessoais dos servidores.

---

## 🔒 Arquitetura de Segurança e Privacidade (*Privacy by Design*)
Para proteger a integridade e a privacidade dos Agentes Comunitários de Saúde (ACSs) contra abordagens indevidas ou exposição pública excessiva na internet:
- **Visão Pública (Anônima):** O cidadão ou recepcionista que pesquisa um endereço visualiza apenas a **UBS de referência** e a **Equipe de Saúde da Família** correspondente. O nome do ACS permanece oculto.
- **Visão Autenticada (Por Unidade):** Cada UBS possui um login genérico e seguro de acesso restrito (ex: `ubs.nome_da_unidade`). Ao logar, o funcionário tem acesso à informação completa, incluindo o nome do ACS responsável pela microárea.
- **Painel Administrativo Master:** Controle centralizado para gerenciamento de unidades, credenciais e integridade do banco de dados de ruas.

---

## 🛠️ Tecnologias Previstas
- **Backend:** Python (FastAPI / Flask)
- **Banco de Dados:** SQLite (leve, embarcado e ideal para intranets municipais)
- **Frontend:** HTML5, CSS (Tailwind/Bootstrap) e JavaScript (Vanilla)
- **Versionamento:** Git & GitHub

---
*Projeto desenvolvido no âmbito acadêmico / extensionista para otimização da gestão pública de saúde.*
