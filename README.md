# Sistema de Microterritorização e Gestão de Equipes de Saúde (UBS)

## 📌 Contexto e Justificativa
Este projeto nasceu da vivência prática do desenvolvedor atuando como Agente Comunitário de Saúde (ACS) na **UBS Monterey**, no município de Sarandi, Paraná. A necessidade surgiu para solucionar um problema crítico e sistêmico enfrentado diariamente na rotina da unidade: a imprecisão na identificação da unidade e da equipe responsável pelo atendimento do cidadão.

### A Evolução do Problema e das Soluções
* **A Falha Geográfica (Google My Maps):** O uso de ferramentas tradicionais de mapas falhava drasticamente na ponta. Um exemplo clássico ocorria na **Rua Ladário, número 600**: o sistema visual do My Maps apontava para a área azul (UBS Monterey), mas na realidade o endereço pertencia à **UBS Oriental**. A imprecisão espacial chegava a **2 quilômetros de desvio**.
* **A Planilha Frágil (LibreOffice Calc):** Uma tentativa anterior utilizou faixas numéricas de ruas cadastradas em planilha. Contudo, por ser um arquivo editável localmente, o uso incorreto por operadores acabava corrompendo fórmulas, exigindo resgates constantes da versão original.
* **A Versão Web na Rede Interna:** Para resolver o problema da edição acidental, a planilha foi convertida em uma página web simples hospedada na pasta compartilhada do Windows Server da rede municipal, acessada via favoritos no navegador. Embora tenha travado as edições indevidas, gerou um novo gargalo: com a alta rotatividade de pessoal e o redimensionamento constante de áreas, qualquer alteração dependia exclusivamente de intervenções manuais do desenvolvedor (técnico de manutenção).
* **O "Efeito Cascata" do Erro:** 
  - *A "Ping-Pong" de Unidades:* Pacientes eram mandados da UBS Oriental para a Monterey e vice-versa, gerando irritação justificada.
  - *O Limite do GMUS:* O sistema oficial (GMUS) não exibia a microárea a menos que o paciente já tivesse sido cadastrado antes.
  - *O Conflito Interno:* Buscas ativas e pedidos de visitas domiciliares feitos por ACSs eram direcionados pela recepção (baseada em mapas falhos) para médicos de outras equipes. Isso gerava atritos entre profissionais, recusas de atendimento cruzado, atrasos no cuidado ao paciente e retrabalho operacional severo.

---

## 🎯 Objetivo e Beneficiados do Projeto
Desenvolver uma aplicação web centralizada, segura e autônoma para a gestão de microterritorização, gerando impactos diretos:
- **Para o Cidadão:** Fim da peregrinação entre unidades erradas e garantia de acolhimento ágil e correto desde a recepção.
- **Para a Recepção e Unidade de Saúde:** Agilidade extrema no balcão e fim dos conflitos de agenda entre equipes médicas.
- **Para Outros Setores (CAPS, SAE/CTA, CRAS, CREAS):** Capacidade de realizar encaminhamentos e buscas ativas diretamente para a UBS e equipe correta apenas com base no endereço.
- **Para a Gestão Municipal:** Distribuição equitativa de pacientes, dados exatos sobre a demanda demográfica e superação das limitações dos grandes softwares burocráticos.

---

## 🔒 Arquitetura de Segurança e Privacidade (*Privacy by Design*)
Para proteger a integridade dos Agentes Comunitários de Saúde (ACSs) contra exposição excessiva na internet aberta, o sistema opera sob níveis de acesso:
- **Visão Pública (Anônima):** Qualquer usuário externo na internet que pesquisa um endereço visualiza apenas a **UBS de referência** e a **Equipe de Saúde da Família** correspondente.
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
