# Entrega 1 — Conhecendo o projeto, o usuário e o problema

**Data:** 13/08/2026  
**Status:** 🟨 em andamento  
**Responsabilidade:** 1 solução consolidada por equipe

## Objetivo da atividade

Reinterpretar o tema do TCC sob a perspectiva de Interação Humano-Computador e construir um **entendimento comum entre os integrantes da equipe**.

A disciplina utiliza preferencialmente o tema do TCC para os exercícios de IHC. Isso vale tanto para TCCs que já preveem uma interface quanto para trabalhos cujo resultado principal é algoritmo, modelo, API, biblioteca, análise de dados, infraestrutura, estudo experimental ou outro artefato técnico.

> **Importante:** a interface projetada na disciplina é um artefato de aprendizagem de IHC. Ela **não se torna automaticamente uma obrigação do TCC**. Sua incorporação ao trabalho de conclusão depende de decisão da equipe e do orientador.

Antes de preencher, leia [`../GUIA_ESCOPO_IHC.md`](../GUIA_ESCOPO_IHC.md).

Nesta primeira semana a equipe **não deve começar desenhando telas**. Primeiro deverá compreender:

- o que o TCC realmente produz;
- quem poderia obter valor dessa contribuição;
- quais pessoas interagem, administram, configuram, interpretam ou são afetadas;
- o que essas pessoas precisam alcançar;
- como atividades relacionadas acontecem hoje;
- problemas, limitações e contexto;
- alternativas existentes;
- qual recorte de interação fará sentido para a disciplina.

Ao final desta entrega, a equipe deve diferenciar:

- **tema do TCC** × **escopo formal do TCC** × **escopo de IHC da disciplina**;
- **objetivo do projeto** × **objetivo do usuário**;
- **problema do usuário** × **solução tecnológica**;
- **fato conhecido** × **hipótese** × **lacuna de conhecimento**;
- **capacidade técnica** × **forma de uso dessa capacidade**;
- **funcionalidade** × **atividade/resultado que o usuário precisa alcançar**;
- **usuário direto** × **stakeholders**.

---

## Como classificar as respostas

Sempre que a resposta fizer uma afirmação sobre usuários, problemas, atividades, necessidades, contexto ou mercado, use:

- **[F] Fato conhecido** — existe evidência/fonte.
- **[H] Hipótese** — afirmação plausível que ainda precisa ser investigada.
- **[?] Não sabemos ainda** — lacuna relevante.

Quando usar `[F]`, informe a origem. Hipóteses prioritárias devem receber IDs (`H01`, `H02`...) e também ser registradas em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

> **Exemplo:** `[H] H01 — DBAs considerariam útil comparar automaticamente o plano atual de execução com uma recomendação produzida pelo algoritmo.`

Uma hipótese explicitada é melhor do que uma suposição escondida.

---

# 0. Identificação do TCC e da equipe

## 0.1 Membros

| Nome completo | Matrícula | GitHub |
|---|---:|---|
| Lucas Kerr do Amaral | 221230329 | Adelgrin |
| Marcela Nalesso | 222220113 | Marcela1204 |

## 0.2 Título atual do TCC

Tecnologias de Machine Learning para Detecção de Intrusões em Redes de Computadores: Uma Pesquisa Exploratória e Experimental

## 0.3 Orientador(a)

Leonardo Anjoletto Ferreira

## 0.4 Qual é o resultado principal atualmente previsto no TCC?

Marque e descreva:

- [ ] sistema/aplicação interativa;
- [ ] algoritmo;
- [X] modelo de IA/ML/LLM;
    - Utilização de modelos de classificação supervisionada para análise dos dados da rede.
- [ ] biblioteca/API/framework;
- [ ] análise de dataset;
- [X] estudo/benchmark/avaliação experimental;
    - Experimento de um sistema inteligente de redes em regime de tempo real.
- [X] infraestrutura/backend;
    - Utilização de sistemas de virtualização.
- [X] componente embarcado/IoT;
    - Processamento e controle de uma plataforma embarcada, para coletar dados dos sensores e processar as informações em tempo real.
- [X] outro: Indicadores.
    - Avaliar através de tabelas, gráficos e evidências o nível de segurança da rede.

## 0.5 O TCC já previa desenvolvimento de interface com usuário?

- [X] Sim, a interface já faz parte do TCC.
- [ ] Parcialmente; existe alguma interação, mas ainda não está bem definida.
- [ ] Não. O TCC é predominantemente técnico e não previa interface.

**Explique o que está formalmente previsto no TCC:** Desenvolvimento de um sistema de detecção de intrusão baseado em algoritmos de classificação supervisionada, com visualização em dashboard para gerenciamento e monitoramento da segurança de rede.

> Esta resposta serve para separar o compromisso do TCC do projeto da disciplina. Mesmo quando a opção for **não**, a equipe irá definir uma interface para exercitar IHC.

---

# 1. Entendendo a contribuição do projeto

## 1.1 Explique o TCC em uma frase, sem citar linguagem de programação, framework ou banco de dados.

Propomos um sistema inteligente de segurança de redes que identifica e alerta invasões cibernéticas em tempo real, para garantir máxima precisão do tráfego de dados analisado.

## 1.2 Qual situação, atividade ou problema do mundo real motivou o TCC?

> <b>[F]</b> O avanço das redes de computadores e a crescente digitalização de serviços têm ampliado significativamente a exposição de sistemas a ameaças cibernéticas. Esse crescimento é acompanhado por um aumento expressivo no volume de dados trafegados, que passou de aproximadamente 16 GB por usuário ao mês em 2017 para cerca de 50 GB mensais em 2022. Esse cenário contribui diretamente para a ampliação da superfície de ataque, refletindo no aumento da quantidade e da sofisticação de ameaças, como negações de serviço, varreduras de rede e acessos não autorizados.
- Fonte: A. Thakkar e R. Lohiya, “A survey on intrusion detection system: feature selection, model, performance measures, application perspective, challenges, and future research directions,” Artificial Intelligence Review, vol. 54, pp. 4529–4593, 2021. doi: 10.1007/s10462-021-10037-9)

> <b>[F]</b> Os impactos de falhas de segurança tornam-se cada vez mais críticos, sendo que mais de 14 bilhões de registros de dados foram vazados desde 2013, além de prejuízos financeiros significativos, como os 29,8 bilhões de dólares perdidos em golpes telefônicos apenas no ano de 2020.
- Fonte: Z. Azam, M. M. Islam e M. N. Huda, “Comparative Analysis of Intrusion Detection Systems and Machine Learning-Based Model Analysis Through Decision Tree,” 2023. doi: 10.1109/2023.3296444

> <b>[F]</b> Um dos maiores desafios atuais da segurança em redes está relacionado aos ataques de Zero−Day, que exploram vulnerabilidades ainda desconhecidas pelos sistemas de defesa. Por não possuírem assinaturas previamente registradas, esses ataques são difíceis de identificar por métodos tradicionais, funcionando como ameaças invisíveis até que sejam descobertas.
- Fonte: W. S. Admass, Y. Y. Munaye e A. A. Diro, “Cyber security: State of the art, challenges and future directions,” 2023. doi: 10.1016/2023.10031

> <b>[F]</b> Casos reais, como a Operação Aurora, demonstram o potencial destrutivo dessas ameaças, incluindo roubo
de dados sensíveis e comprometimento de infraestruturas críticas.
- Fonte: W. S. Admass, Y. Y. Munaye e A. A. Diro, “Cyber security: State of the art, challenges and future directions,” 2023. doi: 10.1016/2023.10031

## 1.3 Qual é a **capacidade/contribuição central** produzida pelo TCC?

Detectar tentativas de invasão cibernética em uma rede de computadores em tempo real, reduzindo a dimensionalidade dos dados sem perder precisão.

## 1.4 O que se espera que esteja diferente **para pessoas, organizações ou processos** se essa contribuição for bem-sucedida?

- [F] Eficiência no monitoramento em tempo real: Adoção de modelos de baixo tempo de inferência (como Decision Tree com tempo de teste de ~0,003s) viabiliza a detecção instantânea em redes de alto tráfego.  (Fonte: Texto dos Autores do TCC)
- [H] Redução do tempo de resposta a incidentes (MTTR): A consolidação dos eventos em um painel modular e visual permitirá que equipes de cibersegurança identifiquem a origem e o tipo de ataque sem precisar analisar logs brutos.
- [H] Viabilidade operacional em hardware limitado: A otimização para plataformas embarcadas reduz os custos de infraestrutura para monitoramento de redes e ambientes de IoT.

## 1.5 O que é mérito técnico/científico do TCC e o que seria uma possível aplicação prática?

| Mérito/contribuição técnica | Possível aplicação/valor em uso |
|---|---|
| [H] Monitoramento em tempo real | [H] Garantia de resposta mais rápida a incidentes comparada com sistemas semelhantes |
| [F] Redução de atributos e otimização: Seleção de 16 a 18 features e uso de PCA mantendo acurácia superior a 95% | [H] Processamento leve para ajudar o processamento em tempo real |
| [F] Pipeline modular de ML: Comparativo entre algoritmos (DT, RF, KNN, SVM, LR) para classificação de tráfego | [H] Painel de controle que permite ao analista trocar o algoritmo de detecção conforme o perfil da rede |
| [F] Agrupamento e classificação de ataques: Agrupamento das ameaças nas macrocategorias DoS, Probe, R2L e U2R | [H] Dashboard de segurança com visualização de riscos categorizados e alertas em tempo real |
(Fonte: Texto dos Autores do TCC)
---

# 2. Entendendo as pessoas envolvidas

## 2.1 Quem interage diretamente com o produto, se já existe interface prevista?

Se não houver interface prevista no TCC, escreva `NÃO SE APLICA AO ESCOPO ORIGINAL` e prossiga para 2.2.

[H] Analistas de segurança da informação (SOC), administradores de rede e pesquisadores/gestores de TI.

## 2.2 Quem poderia **usar, configurar, administrar, operar, interpretar ou tomar decisões** a partir da contribuição técnica?

Considere perfis profissionais e stakeholders, não apenas consumidores finais.

| Perfil | Relação com a contribuição | O que faria | Status/evidência |
|---|---|---|---|
| Analista | Gerenciador | Interage diretamente com a interface | [F] |
| Diretor | Contratante | Contrata o serviço e verifica a diminuição em casos de vazamento | [F] |
| Analista de Segurança | Operar e Interpretar | Monitorar o tráfego em tempo real no dashboard, avaliar alertas de invasão e conter ameaças | [H] |
| Administrador de Rede | Configurar e Administrar | Ajustar parâmetros de captura de rede, selecionar algoritmos ativos e configurar a plataforma física/embarcada | [H] |
| Gestor de Segurança | Tomar decisões | Visualizar relatórios consolidados, avaliar taxas de ataque e decidir sobre investimentos em infraestrutura | [H] |
(Fonte: ???)

## 2.3 Existem pessoas afetadas que não usariam a interface diretamente?

| Stakeholder | Como é afetado | Usa interface? | Status/evidência |
|---|---|---|---|
| Contribuintes | Garante a segurança para o uso da rede | Não | Usuário desta mesma rede |
| Usuários finais da rede | Têm seus serviços mantidos (disponibilidade) e seus dados protegidos contra vazamentos | Não | [F] |
| Diretoria / Clientes da empresa | Evitam prejuízos financeiros e danos de reputação decorrentes de sequestro ou vazamento de dados | Não | [F] |
(Fonte: Texto dos Autores do TCC)

## 2.4 Que características desses perfis podem influenciar a interação?

- [H] Analistas de SOC estão acostumados a gerenciar redes com ferramentas similares, para estes casos o sistema implementado é uma melhoria do trabalho já existente.
- [F] Exigência de resposta rápida: O contexto de cibersegurança exige tomar decisões instantâneas para conter ataques em andamento.  
- [H] Familiaridade com palavras técnicas: O usuário compreende conceitos de rede (portas, protocolos, pacotes, flags SYN), mas necessita que esses dados venham pré-processados e visualmente resumidos.
- [H] Muita informação ao mesmo tempo: Sob ataque ativo, a interface deve evitar excesso de dados visuais desnecessários e priorizar alertas de alta severidade.
(Fonte: Texto dos Autores do TCC)
---

# 3. Entendendo objetivos e atividades

## 3.1 O que o usuário está tentando conseguir no mundo real?

- [H] Garantir um acesso mais seguro a uma rede de computadores, e evitar vazamento de dados permitindo uma resposta rápida a incidentes.

- [H] Manter a rede operacional e segura, identificando e mitigando ameaças antes que comprometam a disponibilidade, integridade ou confidencialidade dos dados.

## 3.2 Quais são as atividades mais importantes?

| ID | Atividade/objetivo | Quem realiza | Frequência/criticidade inicial | Status/evidência |
|---|---|---|---|---|
| A01 | Monitoramento | Analista de Segurança | Constante | Análise do tráfego de rede em tempo real para identificar anomalias |
| A02 | Gerenciamento | Analista de Segurança | Constante | Análise de detalhes de um alerta de ataque (origem, categoria DoS/Probe/R2L/U2R) |
| A03 | Configuração | Administrador | Mensalmente | Alternância do modelo de Machine Learning ativo conforme exigência do ambiente |

## 3.3 Qual atividade parece mais frequente? Por quê?

[H] A01, pois os fluxos de pacotes chegam ininterruptamente na infraestrutura e exigem observação contínua de métricas agregadas de saúde da rede

## 3.4 Qual parece mais crítica? Que consequência existe se for mal executada?

[H] A02, Se for mal executada ou demorada, um ataque destrutivo (como exfiltração de dados R2L/U2R) pode se consolidar na rede, gerando vazamento de dados sensíveis ou indisponibilidade total dos serviços.

---

# 4. Entendendo o problema ou processo atual

## 4.1 Como essas atividades são realizadas hoje, antes da interface imaginada na disciplina?

[F] Análise manual/semi-automatizada por meio de logs de rede, ferramentas de captura de pacotes, consoles de linha de comando ou sistemas IDS tradicionais baseados exclusivamente em regras e assinaturas fixas (tais como Snort, Suricata, Cisco Secure, Zeek, Wazuh, ClamAV, Palo Alto, Sophos, Windows Defender, Security Onion e outros)
(Fonte: ???)

## 4.2 O que é difícil, demorado, confuso, repetitivo, arriscado ou pouco transparente?

{{[F/H/?] ...}}

## 4.3 Que informações o profissional precisa interpretar para tomar decisão?

{{[F/H/?] ...}}

## 4.4 O que acontece quando a atividade falha ou quando o resultado é interpretado incorretamente?

{{[F/H/?] ...}}

## 4.5 Conte uma situação concreta.

Escreva uma pequena narrativa com pessoa, objetivo, atividade, contexto, dificuldade e consequência. **Não descreva ainda a futura solução.**

{{[F/H/?] narrativa...}}

## 4.6 Que evidência existe hoje?

| Evidência/fonte | O que sustenta | Limitação |
|---|---|---|
| {{...}} | {{...}} | {{...}} |

---

# 5. Entendendo o contexto de uso

## 5.1 Onde e em quais situações a interação poderia ocorrer?

{{[F/H/?] ...}}

## 5.2 Em quais dispositivos/equipamentos?

{{[F/H/?] ...}}

## 5.3 Existem condições físicas relevantes?

Considere iluminação, ruído, mobilidade, conexão, privacidade, uso compartilhado, interrupções, pressão de tempo etc.

{{[F/H/?] ...}}

## 5.4 Existem fatores sociais ou organizacionais?

Considere papéis, chefias, equipes, permissões, aprovação, responsabilidade profissional, auditoria, turnos e colaboração.

{{[F/H/?] ...}}

## 5.5 Existe necessidade de histórico, rastreabilidade ou auditoria?

{{[F/H/?] ...}}

## 5.6 Um erro pode produzir consequência relevante? Qual?

{{[F/H/?] ...}}

---

# 6. Entendendo mercado e alternativas existentes

> Nesta entrega faça apenas um **levantamento inicial**. A análise aprofundada ocorre na Entrega 2.

## 6.1 Como pessoas resolvem problemas semelhantes hoje?

| Alternativa atual | Quem usa | Para quê | Status/evidência |
|---|---|---|---|
| {{...}} | {{...}} | {{...}} | {{...}} |

## 6.2 Existem produtos que atuam na mesma área, mesmo sem serem equivalentes ao TCC?

{{[F/H/?] ...}}

## 6.3 Quais interfaces profissionais esse público já conhece?

Exemplos possíveis: ferramentas de banco, IDEs, consoles de nuvem, dashboards, plataformas de dados, ferramentas de monitoramento, painéis de IA, sistemas administrativos.

{{[F/H/?] ...}}

## 6.4 O que essas soluções parecem fazer bem?

{{[F/H/?] ...}}

## 6.5 O que parecem fazer mal, dificultar ou não atender?

{{[F/H/?] ...}}

## 6.6 Que padrões de interface ou vocabulário parecem familiares a esse público?

{{[F/H/?] ...}}

---

# 7. Derivando o escopo de IHC da disciplina

## 7.1 Escolha o caminho do projeto

### Caminho A — TCC já possui interface

Explique qual parte da interface será usada como recorte da disciplina e por que esse fluxo é relevante.

{{...}}

### Caminho B — TCC não possui interface prevista

Faça o exercício de transferência de uso:

> **Imagine que o TCC foi concluído com sucesso e uma empresa, laboratório ou organização quer transformar a contribuição em algo utilizável. Quem precisaria interagir com ela e para quê?**

Responda:

1. quem poderia contratar/adotar a solução? {{...}}
2. quem seria o usuário direto? {{...}}
3. quem administraria/configuraria? {{...}}
4. quem interpretaria resultados? {{...}}
5. quem tomaria decisões? {{...}}
6. quais dados/entradas seriam necessários? {{...}}
7. quais resultados deveriam ser compreendidos? {{...}}
8. que erros/rupturas seriam possíveis? {{...}}

## 7.2 Qual perfil será priorizado no projeto de IHC?

{{...}}

**Por que esse perfil foi escolhido?** {{...}}

## 7.3 Qual objetivo desse usuário será priorizado?

{{...}}

## 7.4 Que interface será explorada na disciplina?

Complete:

> **Para fins da disciplina de IHC, será projetada uma interface que permita a `{{perfil}}` utilizar `{{capacidade/resultado do TCC}}` para `{{objetivo}}`, no contexto de `{{situação}}`.**

{{...}}

## 7.5 Qual é a relação dessa interface com o TCC?

- [ ] Já fazia parte do TCC.
- [ ] É um aprofundamento de algo parcialmente previsto.
- [ ] É uma extensão conceitual criada para a disciplina.
- [ ] É um protótipo demonstrativo de aplicação potencial.
- [ ] Outra: {{...}}.

> **Declaração:** a interface desenvolvida nesta disciplina é um artefato de aprendizagem de IHC baseado no tema do TCC. Sua inclusão ou implementação no TCC somente ocorrerá se isso for posteriormente decidido pela equipe e pelo orientador.

---

# 8. Levantando possibilidades de interação — sem desenhar ainda

A equipe pode registrar possibilidades para investigação. **Não significa que todas serão implementadas.**

Marque apenas as que parecem plausíveis e explique o objetivo correspondente.

| Possibilidade | Pode fazer sentido? | Objetivo/tarefa que justificaria | Evidência atual |
|---|---|---|---|
| Dashboard/visão geral | sim/não/talvez | {{...}} | {{...}} |
| Configuração/parametrização | sim/não/talvez | {{...}} | {{...}} |
| Entrada/upload/seleção de dados | sim/não/talvez | {{...}} | {{...}} |
| Acompanhamento de processamento | sim/não/talvez | {{...}} | {{...}} |
| Relatório/resultados | sim/não/talvez | {{...}} | {{...}} |
| Histórico com busca/filtros | sim/não/talvez | {{...}} | {{...}} |
| Comparação de resultados | sim/não/talvez | {{...}} | {{...}} |
| Explicabilidade/detalhamento | sim/não/talvez | {{...}} | {{...}} |
| Administração/configurações globais | sim/não/talvez | {{...}} | {{...}} |
| Usuários/perfis/permissões | sim/não/talvez | {{...}} | {{...}} |
| CRUD de entidade do domínio | sim/não/talvez | {{...}} | {{...}} |
| Auditoria/logs | sim/não/talvez | {{...}} | {{...}} |
| Alertas/ocorrências | sim/não/talvez | {{...}} | {{...}} |
| Ajuda/documentação | sim/não/talvez | {{...}} | {{...}} |

> **Atenção:** “login + dashboard + CRUD” não é uma solução universal. Cada padrão deve surgir de uma tarefa real.

---

# 9. Benefícios e ações iniciais

## 9.1 Qual benefício concreto o projeto de IHC pretende oferecer?

| Benefício esperado | Problema/necessidade | Usuário | Status/evidência |
|---|---|---|---|
| {{...}} | {{...}} | {{...}} | {{...}} |

## 9.2 Que ações o usuário deverá conseguir realizar?

| ID | O usuário precisa conseguir... | Para alcançar... | Prioridade inicial |
|---|---|---|---|
| F01 | {{ação}} | {{objetivo}} | alta/média/baixa |

## 9.3 Tecnologias/restrições já definidas no TCC

A tecnologia aparece **agora**, depois do entendimento do uso.

| Tecnologia/restrição | Por que existe | Possível impacto na interação |
|---|---|---|
| {{...}} | {{...}} | {{...}} |

---

# 10. Hipóteses e dúvidas prioritárias

| ID | Hipótese/dúvida | Por que importa | Como poderá ser investigada |
|---|---|---|---|
| H01 | {{...}} | {{...}} | Entrega 2/3/7/... |
| H02 | {{...}} | {{...}} | {{...}} |
| H03 | {{...}} | {{...}} | {{...}} |

Registre em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

---

# 11. Síntese da equipe

| Pergunta | Síntese atual |
|---|---|
| Qual é a contribuição central do TCC? | {{...}} |
| O TCC já previa interface? | {{...}} |
| Quem é o usuário prioritário de IHC? | {{...}} |
| O que ele precisa alcançar? | {{...}} |
| Qual problema/atividade será estudado? | {{...}} |
| Como isso acontece hoje? | {{...}} |
| Qual é o contexto de uso? | {{...}} |
| Que interface/recorte será explorado? | {{...}} |
| Como a interface se relaciona ao TCC? | {{...}} |
| Quais pontos ainda são hipóteses? | {{H01...}} |

### Delimitação

**Dentro do escopo de IHC:** {{...}}  
**Fora do escopo de IHC:** {{...}}  
**Dentro do escopo formal do TCC:** {{...}}  
**Interface da disciplina será implementada no TCC?** não definido / sim / não — {{justificativa, se houver}}

---

# 12. Como esta entrega alimenta as próximas

- **Entrega 2:** verifica mercado, concorrentes e interfaces profissionais representativas.
- **Entrega 3:** detalha perfis e contexto.
- **Entrega 4:** aprofunda situações problemáticas.
- **Entrega 5:** modela tarefas centrais.
- **Entrega 6:** experimenta alternativas em baixa fidelidade.
- **Entrega 7:** investiga hipóteses com dados.
- **Entrega 8:** define restrições e metas de usabilidade.
- **Entregas 9–11:** transformam o recorte em modelo de interação e protótipo.
- **Entregas 12–14:** avaliam a interface construída na disciplina.

A Entrega 1 é uma **fotografia inicial do conhecimento**. Ela pode e deve ser revisada quando surgirem evidências.

---

# 13. Relação com INOVA e comunicação do projeto

Prepare uma explicação de até três frases:

1. **Problema/atividade humana:** {{...}}
2. **Contribuição técnica do TCC:** {{...}}
3. **Como uma pessoa poderia utilizar essa contribuição:** {{...}}

Essa síntese ajuda a apresentar o projeto para público não especializado sem reduzir seu mérito técnico.

---

# Checklist de qualidade

- [ ] Está clara a diferença entre tema do TCC, escopo formal do TCC e escopo de IHC.
- [ ] A equipe declarou se o TCC já previa interface.
- [ ] Se não previa, foi derivado um usuário plausível e um objetivo de uso.
- [ ] A interface de IHC não foi apresentada como obrigação automática do TCC.
- [ ] A contribuição do TCC foi descrita sem começar por tecnologias de implementação.
- [ ] Usuários diretos e stakeholders foram diferenciados.
- [ ] Foram considerados profissionais que configuram, administram, interpretam ou decidem, quando pertinente.
- [ ] Objetivo do usuário não foi confundido com objetivo do projeto.
- [ ] Processo/problema atual foi descrito antes da solução.
- [ ] Existe situação concreta de uso/problema.
- [ ] Contexto físico, social/organizacional, dispositivos e consequências de erro foram considerados.
- [ ] Mercado/alternativas existentes foram levantados inicialmente.
- [ ] Possibilidades como dashboard, relatório, histórico, filtros e CRUD foram tratadas como hipóteses de solução, não como requisitos automáticos.
- [ ] Cada possibilidade de interface tem um objetivo/tarefa que poderia justificá-la.
- [ ] Afirmações relevantes estão marcadas `[F]`, `[H]` ou `[?]`.
- [ ] Hipóteses prioritárias receberam IDs e foram para a rastreabilidade.
- [ ] O recorte de IHC é viável para modelar, prototipar e avaliar no semestre.
- [ ] A equipe consegue explicar problema humano → contribuição computacional → forma de uso.
