# Sistema de Microterritorização e Gestão de Equipes de Saúde (UBS)

## 📌 Contexto e Justificativa
Este projeto nasceu da vivência prática do desenvolvedor na Atenção Básica de Saúde no município de Sarandi, Paraná. A necessidade surgiu para solucionar um problema crítico enfrentado diariamente na rotina da **UBS Monterey**: a imprecisão na identificação da unidade e da equipe responsável pelo atendimento do cidadão.

### O Problema Operacional
* **A Falha Geográfica (Google My Maps):** O uso de ferramentas tradicionais de mapas falhava drasticamente na ponta. Um exemplo clássico ocorria na **Rua Ladário, número 600**: o sistema visual do My Maps apontava para a área azul (UBS Monterey), mas na realidade o endereço pertencia à **UBS Oriental**. A imprecisão espacial chegava a **2 quilômetros de desvio**, enviando o paciente para a unidade errada, sobrecarregando equipes incorretas e gerando atritos no atendimento.
* **A Planilha Frágil (LibreOffice Calc):** Uma tentativa anterior utilizou faixas numéricas de ruas cadastradas em planilha. Contudo, por ser um arquivo editável localmente, o uso incorreto acabava corrompendo fórmulas, exigindo resgates constantes da versão original e gerando dependência técnica contínua.
* **A Solução Web Atual e o Gargalo:** A migração inicial para uma página web na rede interna travou as edições indevidas, mas a alta rotatividade de pessoal, o redimensionamento de áreas (para equilibrar a população entre os 22 ACSs da UBS Monterey e os 8 de outra unidade) e a dependência do técnico de TI para alterações manuais tornaram-se insustentáveis.

---

## 🎯 Objetivo do Projeto
Desenvolver uma aplicação web centralizada, eficiente e segura para a gestão de microterritorização, permitindo:
- **Resolução de Conflitos Geográficos:** Mapeamento exato por faixas numéricas (par/ímpar) eliminando os erros de distâncias e unidades trocadas.
- **Consulta Ágil e Confiável:** Atendimento rápido para recepção e suporte à população.
- **Gestão Descentralizada por Unidade:** Autonomia para que cada UBS atualize suas próprias faixas de ruas e microáreas através de um painel administrativo seguro.

---

## 🔒 Arquitetura de Segurança e Privacidade (*Privacy by Design*)
Para proteger a integridade dos Agentes Comunitários de Saúde (ACSs) contra exposição excessiva na internet aberta, o sistema opera sob níveis de acesso:
- **Visão Pública (Anônima):** Qualquer usuário externo na internet que pesquisa um endereço visualiza apenas a **UBS de referência** e a **Equipe de Saúde da Família** correspondente, sem expor dados pessoais na web.
- **Visão Autenticada (Login por UBS):** Funcionários da recepção e da unidade (que precisam do dado completo para orientar o fluxo interno) utilizam um **login genérico e seguro por UBS** (ex: `ubs.monterey`). Ao logar, a interface é liberada para exibir o **nome do ACS responsável** pela microárea.
- **Painel Administrativo Master:** Controle centralizado para gerenciamento de unidades, credenciais e integridade do banco de dados.

---

## 🛠️ Tecnologias Previstas
- **Backend:** Python (FastAPI / Flask)
- **Banco de Dados:** SQLite (leve, embarcado e ideal para intranets municipais)
- **Frontend:** HTML5, CSS (Tailwind/Bootstrap) e JavaScript (Vanilla)
- **Versionamento:** Git & GitHub

---
*Projeto desenvolvido no âmbito acadêmico / extensionista para otimização da gestão pública de saúde.*
