# Documentação de Requisitos - Sistema de Gestão Territorial e UBS

Este documento apresenta a especificação completa dos **Requisitos Funcionais (RFs)** e **Requisitos Não Funcionais (RNFs)** levantados para o sistema de gestão territorial e direcionamento de unidades de saúde.

---

## 1. Requisitos Funcionais (RFs)

* **RF01 - Consulta de Endereço com Direcionamento Inteligente:** O sistema deve fornecer uma interface pública de busca onde o cidadão informe seu endereço (rua e número), cruzando os dados com a base territorial para indicar instantaneamente qual é a UBS de referência, a equipe de saúde (ESF) responsável e o agente (ACS) vinculado.
* **RF02 - Ocultação de Dados Sensíveis na Visão Pública:** O sistema deve ocultar dados cadastrais sensíveis, restritos ou informações internas de controle nos resultados exibidos na interface pública, garantindo a privacidade e a conformidade com as normativas de proteção de dados (LGPD).
* **RF03 - Autenticação e Acesso de Funcionários:** O sistema deve exigir autenticação por login e senha para o acesso às áreas administrativas e de cadastro, aplicando controle de acesso baseado em perfis (ex: recepcionistas, enfermeiros, gestores locais e administrador master).
* **RF04 - Matriz de Serviços e Obrigatoriedade de Referência Cruzada:** O sistema deve gerenciar uma matriz de serviços vinculada às unidades de saúde, exigindo que qualquer alteração de território ou cadastro de atendimento cruze obrigatoriamente as informações de rua, faixa e unidade correspondente.
* **RF05 - Cadastro Descentralizado Inteligente e Governança de Endereços:** O sistema deve fornecer um painel administrativo para que as equipes e gestores locais cadastrem e gerenciem faixas de ruas, intervalos numéricos, lados (*Par, Ímpar ou Ambos*), Equipes (PSF) e ACSs, eliminando a dependência da TI. O sistema deve conter mecanismos automáticos para prevenção de erros tipográficos (evitando duplicidades como *Campo Grande* vs *Campo Grandi*), validação de sobreposições de faixas e um painel de governança para o Administrador Master.
* **RF06 - Gestão de Usuários, Auditoria e Controle Master Global:** O sistema deve fornecer um painel exclusivo para o Administrador Master contendo controle completo de acessos/permissões de usuários, visão global de auditoria de alterações e poder de alteração irrestrita (editar, corrigir, unificar ou excluir) em qualquer registro do banco de dados.
* **RF07 - Requisitos de Segurança e Criptografia da Aplicação:** O sistema deve implementar criptografia de senhas no banco de dados utilizando algoritmos de alta resistência (ex: *bcrypt*), controle rígido de sessão e proteção contra vulnerabilidades web comuns (como Injeção de SQL e proteção de rotas).
* **RF08 - Emissão de Relatórios Gerenciais e Operacionais de Território:** O sistema deve permitir a geração de relatórios detalhados, contemplando extratos operacionais por microárea ou ACS para conferência em campo pelas equipes de saúde, além de relatórios gerenciais globais (unidades, microáreas e usuários) para o Administrador Master.

---

## 2. Requisitos Não Funcionais (RNFs)

* **RNF01 - Desempenho e Tempo de Resposta:** As consultas de endereço e o cruzamento de faixas numéricas na interface de atendimento devem retornar os resultados em **menos de 1 segundo**.
* **RNF02 - Usabilidade e Responsividade (Mobile-Friendly):** A interface do sistema deve ser totalmente responsiva, adaptando-se perfeitamente a computadores, tablets e smartphones.
* **RNF03 - Arquitetura e Stack Tecnológica:** O sistema deve ser desenvolvido utilizando **Python** com o framework **Flask** para o back-end, estruturado com banco de dados relacional **SQLite**.
* **RNF04 - Manutenibilidade e Legibilidade de Código:** O código-fonte da aplicação deve seguir padrões organizacionais estruturados (separação de responsabilidades), facilitando manutenções corretivas e evolutivas.
* **RNF05 - Disponibilidade e Confiabilidade de Acesso:** O sistema deve estar acessível durante o expediente padrão de atendimento, contando com mecanismos básicos de persistência e suporte a rotinas facilitadas de backup.
