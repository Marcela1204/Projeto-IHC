# Entrega 2 — Público-alvo e análise de concorrência

**Data:** 19/08/2026  
**Status:** `🟨 em andamento`      
**Responsabilidade mínima:** cada integrante analisa pelo menos 1 concorrente/interface representativa; a equipe produz síntese comparativa.

## Objetivo da atividade

Compreender soluções do mesmo domínio **e também interfaces familiares ao público-alvo**. O objetivo não é copiar telas, mas identificar convenções, padrões, affordances percebidas, problemas recorrentes, expectativas e oportunidades de design.

> **Concorrente não precisa ser idêntico ao produto.** Pode atuar na mesma área, resolver objetivo semelhante ou disputar a mesma necessidade. Quando não houver concorrente direto, use produtos análogos e softwares que o público já utiliza.

### Para TCCs que não previam interface

Não procure apenas um “concorrente do algoritmo”. Investigue **interfaces profissionais que materializam atividades semelhantes** às que o usuário escolhido precisaria realizar.

Exemplos:

- TCC de banco de dados → consoles de administração, ferramentas para DBA, monitoramento e análise de consultas;
- TCC de LLM/ML → painéis de experimentos, gestão de modelos/datasets, comparação de métricas, revisão de resultados;
- TCC de análise de dados → dashboards, ferramentas de BI, filtros, relatórios e exploração;
- TCC de infraestrutura/API → portais administrativos, observabilidade, logs, gestão de credenciais e uso;
- TCC de cibersegurança → consoles de alertas, triagem, histórico e auditoria.

A pergunta é: **“que convenções esse perfil já conhece para executar tarefas equivalentes?”**

## Entrada obrigatória da Entrega 1

Retome o mapa inicial de alternativas e produtos citado na Entrega 1. Aqui a equipe deixa de trabalhar apenas com impressão inicial e passa a **investigar sistematicamente** cada solução.

| Item citado na Entrega 1 | Tipo | Por que foi citado | Status inicial | Decisão nesta entrega |
|---|---|---|---|---|
| Splunk |Análogo|Referência de mercado em SIEM, agregação de logs e dashboards complexos para analistas|H|Analisar|
| Elastic SIEM |Análogo|Padrão de mercado para visualização de logs; essencial para entender construção de dashboards|H|Analisar|
| Datadog |Análogo|Referência moderna em observabilidade, monitoramento de infraestrutura e alertas em tempo real|H|Analisar|
| Snort |Concorrente|O IDS de rede (NIDS) open-source mais tradicional e conhecido da área, baseado em assinaturas|H|Descartar, não possui interface gráfica nativa relevante para análise de IHC|
| Suricata |Concorrente|Principal alternativa moderna ao Snort; alta performance em inspeção de pacotes|H|Descartar, não possui interface gráfica nativa relevante para análise de IHC|
| Cisco Secure |Cconcorrente/Análogo|Solução corporativa robusta de segurança de rede e detecção de intrusão|H|Descartar, não possui interface gráfica nativa relevante para análise de IHC|
| Zeek |Concorrente|Framework de análise de rede com foco comportamental|H|Descartar, não possui interface gráfica nativa relevante para análise de IHC|
| Wazuh |Concorrente|Ecossistema open-source completo; referência consolidada para visualização de alertas|F|Analisar|
| Clam AV |Análogo|Ferramenta clássica e open-source para detecção de malwares|H|Descartar, não possui interface gráfica nativa relevante para análise de IHC|
| Palo Alto |Análogo|Firewall de Próxima Geração corporativo com IDS/IPS embutido|H|Descartar, não possui interface gráfica nativa relevante para análise de IHC|
| Sophos |Concorrente/Análogo|Plataforma comercial abrangente de firewall e caça a ameaças|H|Descartar, não possui interface gráfica nativa relevante para análise de IHC|
| Windows Defender |Ferramenta Cotidiana|Solução de segurança que quase 100% do público-alvo já utilizou ou conhece|H|Descartar, não possui interface gráfica nativa relevante para análise de IHC|
| Security Onion |Concorrente|Distribuição Linux que agrupa Snort, Suricata, Zeek e Elastic para monitoramento de segurança|H|Descartar, não possui interface gráfica nativa relevante para análise de IHC|
| Fortinet IDS |Concorrente|Solução de detecção de intrusão associada aos appliances líderes de mercado|H|Analisar|

Se uma hipótese da Entrega 1 for confirmada ou refutada durante esta análise, atualize `H01`, `H02`... em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

## 1. Público-alvo desta análise

Analistas de segurança da informação (SOC), administradores de rede e pesquisadores/gestores de TI.

## 2. Concorrentes diretos/indiretos

### Análise C01 — Fortinet IDS

**Autor(a):** Lucas - 22.123.032-9  
**Tipo:** direto  
**Link oficial:** [Fortinet IDS](https://www.fortinet.com/br/resources/cyberglossary/intrusion-detection-system)  
**Data de acesso:** 27/08/2026

#### Contexto e proposta

O Fortinet IDS (Sistema de Detecção de Intrusões) tem como proposta monitorar continuamente o tráfego de rede para identificar e alertar sobre atividades suspeitas, maliciosas ou desvios de conformidade em tempo real. Integrado ao ecossistema da plataforma Fortinet — como parte dos recursos nativos do sistema FortiOS nos firewalls FortiGate —, ele atua na camada de segurança cibernética preventiva e analítica, fornecendo visibilidade profunda contra ameaças conhecidas e emergentes sem interromper o fluxo operacional, servindo de base essencial para que equipes de TI e SOC reajam rapidamente a potenciais invasões.

#### Funcionalidades relevantes

| Funcionalidade | Como é realizada | Evidência/print                 | Observação de IHC |
| -------------- | ---------------- | ------------------------------- | ----------------- |
| Filtro de origem de conexão | Acesso do dashboard de origens de conexões | `../assets/02_concorrencia/Fortigate_sources.png` | a apresentação permite verificar a origem e destino de cada conexão de dentro da rede |
| Filtro de destino de conexão | Acesso do dashboard de destino de conexões | `../assets/02_concorrencia/Fortigate_Destinations.png` | a apresentação permite verificar os destinos de cada conexão |
| Filtro de sessões de conexão | Acesso do dashboard de sessões de conexões | `../assets/02_concorrencia/Fortigate_sessions.png` | a apresentação permite verificar as sessões de cada dispositivo (conexão iniciada e finalizada) |

#### Experiência do usuário e opiniões

Use avaliações públicas, relatos, estudos, testes próprios ou outra fonte identificável. Não trate opinião isolada como verdade universal.

#### Preço/modelo de negócio

> **(Professor comentou que não é necessário preenchimento)**

#### Padrões e tendências percebidos

{{...}}

#### Pontos positivos, limitações e lições

| Ponto | Evidência | Implicação para nosso projeto |
|---|---|---|
| {{...}} | {{...}} | {{...}} |

---

### Análise C02 — Wazuh Dashboard

**Autor(a):** Marcela Nalesso | RA: 22.222.011-3  
**Tipo:** indireto/análogo  
**Link oficial:** [{{URL}}](https://wazuh.com/)  
**Data de acesso:** 23/08/2026

#### Contexto e proposta

O Wazuh é uma plataforma open-source voltada à segurança de endpoints e monitoramento de ambientes, disponibilizando recursos para análise e visualização de dados de segurança. O Wazuh Dashboard funciona como uma interface central para acompanhamento de eventos, alertas e informações relacionadas aos ativos monitorados. Além disso, é possível que o usuário consiga uma visão geral do ambiente e acessar informações mais específicas para investigação. A ferramenta foi selecionada como interface análoga ao projeto por apresentar uma abordagem consolidada para visualização e investigação de eventos de segurança.

#### Funcionalidades relevantes

| Funcionalidade | Como é realizada | Evidência/print | Observação de IHC |
|---|---|---|---|
|Dashboard de segurança|O usuário acessa dashboards que agregam informações de segurança em diferentes visualizações, permitindo obter uma visão geral do ambiente monitorado|`assets\02_concorrencia\ex_dashboard.png`|A apresentação consolidada reduz a necessidade de consultar diferentes fontes individualmente e favorece a percepção inicial do estado do ambiente|
|Visualização de alertas|Os eventos processados pelo Wazuh são apresentados como alertas, permitindo ao usuário visualizar informações relacionadas às ocorrências detectada|`assets\02_concorrencia\tela_alertas.png`|A organização dos eventos em uma interface específica facilita a identificação de ocorrências que necessitam de investigação|
|Classificação por severidade|Os eventos podem receber níveis de severidade associados às regras que os identificam. O dashboard apresenta informações relacionadas à severidade dos alertas|`assets\02_concorrencia\nivel_severidade.png`|A utilização de níveis de severidade auxilia na priorização das ocorrências, permitindo direcionar a atenção para eventos potencialmente mais relevantes|
|Filtros e consultas|O Wazuh disponibiliza mecanismos de filtragem e consulta, incluindo o Wazuh Query Language (WQL), permitindo restringir os dados apresentados segundo campos e condições específicas|`assets\02_concorrencia\wql1.png` e `assets\02_concorrencia\wql2.png`|A filtragem reduz a quantidade de informação apresentada simultaneamente e permite que o usuário concentre a análise em um subconjunto de eventos|
|Visualização temporal|O dashboard permite representar eventos e informações em visualizações relacionadas ao tempo, incluindo timelines e outros gráficos|`assets\02_concorrencia\visualizacao_tempo.png`|A representação temporal facilita a identificação de concentração, evolução e recorrência de eventos|
|Detalhamento de eventos|A partir das informações agregadas, o usuário pode explorar dados mais específicos dos eventos e alertas para realizar investigações|`assets\02_concorrencia\eventos.png`|A possibilidade de partir de uma visão resumida para informações detalhadas favorece uma abordagem de investigação progressiva|
|Dashboards personalizados|O Wazuh permite criar dashboards e visualizações personalizadas de acordo com as necessidades de monitoramento|`assets\02_concorrencia\personalizacao1.png`, `assets\02_concorrencia\personalizacao2.png` e `assets\02_concorrencia\personalizacao3.png`|A personalização permite adaptar a apresentação das informações às tarefas e prioridades específicas do usuário|

#### Experiência do usuário e opiniões

- <b>G2: Avaliações de Softwares para Empresas
    - Ferramenta avaliada em 4.5 de 5
    - Avaliações Positivas
    ![facilidade_uso](image-3.png)
    ![acessivel](image-4.png)
    ![ciberseguranca](image-5.png)
    ![facilidade](image-6.png)
    ![configuracao](image-7.png)
    - Avaliações Negativas
    ![interface](image-8.png)
    ![amigavel](image-9.png)
    ![complexo](image-10.png)
    ![dificil](image-11.png)
    ![dificil2](image-12.png)
- Reddit: Opiniões Públicas sobre a ferramenta
    - Avaliações Positivas
    ![reddit](image-13.png)
    ![reddit2](image-15.png)
    ![reddit3](image-16.png)
    - Avaliações Negativas
    ![reddit4](image-14.png) 
- Gartner: Reviews do Produto por Usuários
    - Avaliação Positiva da Ferramenta</b>
![Gartner Review](image-2.png)

#### Preço/modelo de negócio

**(Professor comentou que não é necessário preenchimento)**

#### Padrões e tendências percebidos

- **Visão Geral e Navegação**:
    - Se baseia na combinação de visão geral, visualizações gráficas, tabelas, filtros e detalhamento progressivo.
    - Permite ao usuário transitar do panorama geral do ambiente para a investigação de eventos específicos.

- **Dashboards e Indicadores**:
    - Utiliza dashboards para apresentar múltiplos indicadores simultaneamente.
    - Oferece painéis específicos para diferentes atividades de segurança, além de permitir a criação de dashboards personalizados.

- **Filtros e Consultas (WQL)**:
    - Emprega a linguagem WQL (linguagem própria) para combinar condições e realizar buscas específicas.
    - Reduz o volume de informações exibidas ao usuário, facilitando a análise em diferentes áreas da plataforma.

- **Representação Temporal**:
    - Permite a criação de visualizações baseadas em intervalos de tempo.
    - Facilita o acompanhamento da ocorrência, evolução e tendências dos eventos de segurança.

- **Fluxo de Investigação (Visão Geral → Filtragem → Detalhamento)**:
    - Inicia com dados agregados para posterior restrição e aprofundamento de eventos específicos.

#### Pontos positivos, limitações e lições

| Ponto | Evidência | Implicação para nosso projeto |
|---|---|---|
| Positivo: Navegação exploratória contínua | Interatividade dos componentes visuais: gráficos clicáveis que aplicam filtros automáticos no painel | Lição: Nosso IDS não deve exibir predições do modelo de ML como relatórios estáticos. É fundamental permitir que o usuário interaja com as visualizações (ex: clicar no gráfico de tráfego anômalo para filtrar a tabela de eventos) |
| Positivo: Classificação por severidade | O Wazuh utiliza níveis de severidade para os alertas, permitindo estabelecer limites para geração e tratamento de alertas | Lição: O IDS pode utilizar níveis de prioridade ou severidade para auxiliar o usuário a identificar quais detecções devem ser analisadas primeiro |
| Positivo: Análise de Eventos | O Wazuh disponibiliza visualizações temporais para análise de eventos | Lição: A interface pode apresentar a distribuição das detecções ao longo do tempo para facilitar a identificação de picos, recorrências e possíveis incidentes |
| Positivo: Personalização | O usuário pode criar dashboards e visualizações personalizados | Lição: A personalização pode ser considerada caso o escopo do projeto permita diferentes perfis ou necessidades de análise |
| Limitação: Grande quantidade de funcionalidades | A interface reúne uma série de recursos de monitoramento, investigação, configuração, conformidade e administração | Lição: O projeto deve evitar reproduzir a complexidade do Wazuh e priorizar as tarefas diretamente relacionadas ao objetivo do IDS |
| Limitação: Dependência de conhecimento técnico | Recursos como WQL (linguaguem própria da plataforma) oferecem maior capacidade de consulta, mas exigem que o usuário conheça a sintaxe e os campos disponíveis | Lição: A interface do projeto deve priorizar mecanismos de filtragem simples e compreensão direta dos resultados, deixando consultas avançadas como recurso secundário, caso sejam necessárias |

> Repita a subseção para C02, C03... até atender à quantidade da equipe.

## 3. Softwares que o público-alvo usa no cotidiano

Analise interfaces que moldam a expectativa do público, mesmo que não sejam concorrentes.

| Software | Por que o público usa | Padrões relevantes | Prints | O que aprender |
|---|---|---|---|---|
| {{...}} | {{...}} | {{...}} | {{link local}} | {{...}} |

## 3.1 Padrões de interface relevantes ao escopo de IHC

Registre somente padrões encontrados nas soluções analisadas e que possam ter relação com objetivos reais da equipe.

| Padrão observado | Produto(s) | Para qual tarefa serve | Vantagem percebida | Risco/limitação | Aplicável ao nosso escopo? |
|---|---|---|---|---|---|
| dashboard | {{...}} | {{...}} | {{...}} | {{...}} | sim/não/talvez |
| relatório | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |
| histórico + filtros | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |
| administração/CRUD | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |
| comparação de resultados | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |

> O objetivo não é concluir “todo concorrente tem dashboard, então teremos um”. O padrão só será adotado se apoiar uma tarefa rastreável.

## 4. Síntese comparativa da equipe

| Critério | C01 | C02 | Oportunidade para o projeto |
|---|---|---|---|
| Navegação |  |  |  |   
| Feedback/estado |  |  |  |  
| Prevenção/recuperação de erro |  |  |  |  
| Terminologia |  |  |  |  
| Acessibilidade |  |  |  |  
| Eficiência |  |  |  |  

## 5. Recomendações derivadas

Liste recomendações com origem explícita.

- **RC01:** {{recomendação}} — derivada de {{C01/C02/evidência}}.
- **RC02:** {{...}}

## Referências

- Gartner Peer Insights. Wazuh - The Open Source Security Platform. Disponível em: https://www.reddit.com/r/cybersecurity/comments/1d1wzzl/wazuh_pros_and_cons/. Acesso em: 27 ago. 2026 a 31 ago. 2026.

- G2: Avaliações de Software de Empresas. Wazuh. Disponível em: https://www.g2.com/pt/products/wazuh/reviews?qs=pros-and-cons. Acesso em: 27 ago. 2026 a 31 ago. 2026.

- Reddit. Wazuh vale a pena pra minha empresa?. Disponível em: https://www.reddit.com/r/Wazuh/comments/16gkvhh/is_wazuh_worth_it_for_my_company/?tl=pt-br. Acesso em: 27 ago. 2026 a 31 ago. 2026.

- Reddit. Wazuh vale a pena pra minha empresa?. Disponível em: https://www.reddit.com/r/cybersecurity/comments/1d1wzzl/wazuh_pros_and_cons/. Acesso em: 27 ago. 2026 a 31 ago. 2026.

- WAZUH. Wazuh dashboard – User manual. Documentação oficial. Disponível em: https://documentation.wazuh.com/current/user-manual/wazuh-dashboard/navigating-the-wazuh-dashboard.html. Acesso em: 27 ago. 2026 a 31 ago. 2026. 

- WAZUH. Wazuh dashboard – User manual. Documentação oficial. Disponível em: https://documentation.wazuh.com/current/user-manual/wazuh-dashboard/. Acesso em: 27 ago. 2026 a 31 ago. 2026.

- WAZUH. Wazuh dashboard – Components. Documentação oficial. Disponível em: https://documentation.wazuh.com/current/getting-started/components/wazuh-dashboard.html. Acesso em: 27 ago. 2026 a 31 ago. 2026.

- WAZUH. Filtering data using Wazuh Query Language (WQL). Documentação oficial. Disponível em: https://documentation.wazuh.com/current/user-manual/wazuh-dashboard/queries.html. Acesso em: 27 ago. 2026 a 31 ago. 2026.

- WAZUH. Creating custom dashboards. Documentação oficial. Disponível em: https://documentation.wazuh.com/current/user-manual/wazuh-dashboard/creating-custom-dashboards.html. Acesso em: 27 ago. 2026 a 31 ago. 2026.

- WAZUH. Alert management. Documentação oficial. Disponível em: https://documentation.wazuh.com/current/user-manual/manager/alert-management.html. Acesso em: 27 ago. 2026 a 31 ago. 2026.

## Checklist

- [ ] O mapa inicial de alternativas da Entrega 1 foi revisitado e aprofundado.
- [ ] Hipóteses relevantes sobre mercado/padrões foram atualizadas na rastreabilidade quando surgiram evidências.
- [ ] Há pelo menos uma análise completa por integrante.
- [ ] Cada análise contém prints legíveis da interface.
- [ ] Prints mostram telas/estados relevantes, não apenas logos/homepage.
- [ ] Foram analisados concorrentes e/ou interfaces representativas ao público.
- [ ] Em TCC sem interface original, foram investigadas ferramentas profissionais análogas às atividades do usuário escolhido.
- [ ] Padrões como dashboard, relatório, filtros e CRUD foram analisados como soluções para tarefas, não como requisitos automáticos.
- [ ] Opiniões de UX têm fonte.
- [ ] A síntese compara critérios comuns e produz recomendações.
- [ ] Não há “copiar porque o concorrente faz”; há justificativa de adequação ao público/contexto.
