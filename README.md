# Sistema de Microterritorização e Gestão de Equipes de Saúde (UBS)

## 📌 Contexto e Justificativa
Este projeto nasceu da vivência prática do desenvolvedor atuando como Agente Comunitário de Saúde (ACS) na **UBS Monterey**, no município de Sarandi, Paraná. A necessidade surgiu para solucionar um problema crítico e sistêmico enfrentado diariamente na rotina da unidade: a imprecisão na identificação da unidade e da equipe responsável pelo atendimento do cidadão.

### O Problema Operacional e o "Efeito Cascata"
* **A Falha Geográfica (Google My Maps):** O uso de ferramentas tradicionais de mapas falhava drasticamente na ponta. Um exemplo clássico ocorria na **Rua Ladário, número 600**: o sistema visual do My Maps apontava para a área azul (UBS Monterey), mas na realidade o endereço pertencia à **UBS Oriental**. A imprecisão espacial chegava a **2 quilômetros de desvio**.
* **A "Ping-Pong" de Unidades e a Irritação do Cidadão:** Devido a essas falhas, era comum o paciente ir até a UBS Oriental e ser mandado para a Monterey, ou vice-versa, gerando desgaste e irritação justa na população.
* **O Limite dos Sistemas Oficiais (GMUS):** O sistema oficial (GMUS) muitas vezes não exibe a microárea ou o ACS de referência a menos que o paciente já tenha sido previamente cadastrado por ele, deixando lacunas no primeiro atendimento.
* **O Conflito Interno e o Retrabalho:** Quando um ACS identificava um caso em visita e solicitava agendamento, a recepção — baseada em mapas imprecisos — frequentemente direcionava o paciente para o médico de *outra* equipe. Isso gerava um ciclo de atritos:
  - O médico/enfermeiro estranhava o paciente desconhecido em sua agenda.
  - O profissional de saúde reclamava com a recepção, que por sua vez se desentendia com o ACS.
  - O médico por vezes recusava o atendimento cruzado, exigindo correção manual, o que atrasava ainda mais o cuidado ao paciente.
  - Buscas ativas (vacinação, psicologia, visitas) perdiam tempo valioso transitando por equipes erradas até encontrarem o responsável real.
* **A Planilha Frágil (LibreOffice Calc):** Uma tentativa anterior utilizou faixas numéricas de ruas em planilha local. Contudo, o uso incorreto por operadores corrompia fórmulas, exigindo resgates constantes e gerando dependência técnica contínua.

---

## 🎯 Objetivo e Beneficiados do Projeto
Desenvolver uma aplicação web centralizada e segura para a gestão de microterritorização, gerando impactos diretos em múltiplos níveis da rede pública:
- **Para o Cidadão:** Fim da peregrinação entre unidades erradas e garantia de acolhimento ágil e correto desde a recepção.
- **Para a Recepção e Unidade de Saúde:** Agilidade extrema no balcão e fim dos conflitos de agenda entre equipes médicas.
- **Para Outros Setores (CAPS, SAE/CTA, CRAS, CREAS):** Capacidade de realizar encaminhamentos e pedidos de busca ativa diretamente para a UBS e equipe correta apenas com base no endereço do usuário.
- **Para a Gestão Municipal:** Distribuição equitativa de pacientes por área, dados mais exatos sobre a demanda demográfica real de cada microárea e melhor identificação de necessidades de serviço dentro da unidade.

---

## 🔒 Arquitetura de Segurança e Privacidade (*Privacy by Design*)
Para proteger a integridade dos Agentes Comunitários de Saúde (ACSs) contra exposição excessiva na internet aberta, o sistema opera sob níveis de acesso:
- **Visão Pública (Anônima):** Qualquer usuário externo na internet que pesquisa um endereço visualiza apenas a **UBS de referência** e a **Equipe de Saúde da Família** correspondente, otimizando o fluxo externo sem expor dados pessoais.
- **Visão Autenticada (Login por UBS):** Funcionários da recepção e da unidade utilizam um **login genérico e seguro por UBS** (ex: `ubs.monterey`). Ao logar, a interface libera a visualização completa, incluindo o **nome do ACS responsável** pela microárea.
- **Painel Administrativo Master:** Controle centralizado para gerenciamento de unidades, credenciais e integridade do banco de dados.

---

## 🛠️ Tecnologias Previstas
- **Backend:** Python (FastAPI / Flask)
- **Banco de Dados:** SQLite (leve, embarcado e ideal para intranets municipais)
- **Frontend:** HTML5, CSS (Tailwind/Bootstrap) e JavaScript (Vanilla)
- **Versionamento:** Git & GitHub

---
*Projeto desenvolvido no âmbito acadêmico / extensionista para otimização da gestão pública de saúde.*
