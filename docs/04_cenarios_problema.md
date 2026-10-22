# Entrega 4 — Cenários de análise/problema

**Data:** 08/09/2026   
**Status:** `🟩 concluída`  
**Responsabilidade:** 1 solução completa por integrante

## Objetivo da atividade

Descrever situações atuais em que o usuário tenta alcançar um objetivo e encontra dificuldades. O cenário de análise/problema deve tornar visível **o contexto, os atores, as ações e as rupturas**, sem antecipar a interface que será projetada.

> **Regra central:** cenário de problema é a “história do problema”. Se o texto já diz “o sistema mostra”, “o aplicativo resolve” ou descreve botões/telas futuras, provavelmente está misturando problema com solução.

Sempre que possível, o cenário deve aprofundar uma **situação concreta já registrada na Entrega 1**.

### Quando o TCC não possuía interface

O cenário continua sendo uma história de **problema/atividade humana**, não uma história do futuro sistema. Descreva como o profissional realiza hoje uma atividade semelhante ou como lida atualmente com dados, resultados, configurações, logs, decisões e limitações que o tema do TCC pretende apoiar.

Exemplo: em vez de “o DBA abre o novo dashboard e executa o algoritmo”, descreva “o DBA precisa investigar uma consulta lenta, reúne informações em ferramentas distintas, compara planos manualmente e tem dificuldade para estimar o impacto de uma mudança”.

A interface da disciplina aparecerá somente depois, nos cenários de interação.

Se o integrante escolher um novo problema/situação, explique por que ele passou a ser relevante e indique a evidência que motivou sua inclusão.

## Cenário C01 — Alerta de tráfego anômalo durante operação

**Autor(a):** Lucas Kerr - 22.123.032-9   
**Persona(s) relacionada(s):** P01   
**Necessidade relacionada:** R01   
**Situação concreta da Entrega 1 relacionada:** H14 H20 H26   
**Hipóteses ainda presentes:** H14 H26   

**Origem do cenário:** aprofunda a situação concreta da Entrega 1 (4.5, H14), em que Thiago percebe lentidão nos servidores Web durante o plantão noturno e não consegue decidir se é pico legítimo ou ataque. 

### 1. Cenário inicial

Thiago, analista de SOC nível 2, está no plantão noturno escrevendo a análise de uma ocorrência anterior quando o IDS registra uma sequência de conexões classificadas como suspeitas a partir de um mesmo segmento de rede. Thiago abre o console e encontra milhares de linhas de log, misturando as classificações do modelo com o restante do tráfego. Ele não sabe se está diante de um pico legítimo de acessos ou de uma varredura/DoS. Para descobrir, alterna entre o console, consultas manuais e seus próprios scripts para reunir origem, destino, serviço e volume de cada conexão. Enquanto não consegue decidir, a lentidão continua e ele não sabe dizer à operação se alguém deve agir.

### 2. Questões de refinamento

Use os tipos de questões/taxonomia definidos na aula. As perguntas devem revelar informações **ainda ausentes** do cenário, não repetir o que já foi respondido.

| #   | Questão                                                                                              | Por que precisa ser respondida                                                                                                                                   | Fonte/forma de obter resposta                                                                                                           |
| --- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Q1  | O que Thiago estava fazendo e o que acontece com essa tarefa quando ele a interrompe?                | O cenário inicial começa no alerta e ignora o custo da interrupção e da retomada, que o contexto de uso aponta como frequente                                    | Entrega 03, seção 3 (ambiente físico do SOC: interrupções frequentes) e jornada, etapas 1 e 7. Verificação na Entrega 07                |
| Q2  | O que exatamente Thiago precisa decidir — e o que fica fora da sua alçada?                           | Sem essa delimitação, o cenário sugere que ele “resolve” a lentidão, o que contradiz o recorte (ele interpreta e encaminha; não contém)                          | Entrega 01, quadro “limite entre detectar, interpretar e conter”; Entrega 03, quadro “Onde termina a análise e onde começa a contenção” |
| Q3  | Que informação ele precisa reunir para julgar a classificação, e onde cada uma está hoje?            | Revela a dispersão do contexto entre ferramentas — o problema H13                                                                                                | Entrega 01 (4.3, H13, H30); Entrega 03, jornada etapa 3. Verificação na Entrega 07                                                      |
| Q4  | O comportamento do IDS pode ter mudado por causa de uma alteração na configuração? Como ele saberia? | Liga o cenário ao trabalho: se o classificador ativo mudou, o que Thiago vê mudou de origem — e ele não tem como atribuir a mudança a uma causa | Entrega 03, seção 3; H27                                                                           |
| Q5  | Depois de decidir, como Thiago passa o caso a quem age e ao próximo turno?                           | O cenário inicial termina na indecisão e não mostra o que acontece com o registro — que é lido por outras pessoas                                                | Entrega 03, jornada etapas 5–7; H18 e H31                                                                                               |
| Q6  | O que acontece se ele errar em cada direção?                                                         | Torna explícito que o erro custa nos dois sentidos, o que justifica tratar A02 como atividade crítica                                                            | Entrega 01, 4.4 (tabela de erros) e H12                                                                                                 |

### 3. Cenário refinado

Reescreva o cenário incorporando as respostas. Marque o conteúdo novo de forma consistente (por exemplo, `**[NOVO: ...]**`).

Thiago, analista de SOC nível 2, está no plantão noturno escrevendo a análise de uma ocorrência anterior quando o IDS registra uma sequência de conexões classificadas como suspeitas a partir de um mesmo segmento de rede. **[NOVO: a análise está pela metade; o que ele já concluiu está anotado em parte no chamado e em parte só na própria memória. Antes de abrir o console, ele precisa decidir se o alerta vale largar o que estava fazendo.]**

**[NOVO: o que Thiago precisa decidir não é como resolver o problema na rede, e sim se aquelas conexões correspondem a um incidente real. A decisão tem três saídas possíveis: descartar como falso positivo, confirmar como incidente e encaminhar, ou marcar como indefinido e continuar investigando. Bloquear ou isolar o segmento não é tarefa dele: cabe à equipe de infraestrutura, a pedido dele.]**

Thiago abre o console e encontra milhares de linhas de log, misturando as classificações do modelo com o restante do tráfego. Ele não sabe se está diante de um pico legítimo de acessos ou de uma varredura/DoS. Para descobrir, alterna entre o console, consultas manuais e seus próprios scripts para reunir origem, destino, serviço e volume de cada conexão. **[NOVO: para julgar, ele precisa saber quem é a origem, se ela já se comunicou antes com aquele destino, se o volume destoa do habitual daquele ativo e se há outras conexões com o mesmo padrão. Cada resposta está num lugar diferente: o console, a captura de pacotes, um script próprio que extrai contagens do log e a memória de turnos anteriores. Ele monta cada consulta à mão e guarda de cabeça o que já viu enquanto passa de uma ferramenta para outra.]** 

**[NOVO: Thiago também nota que, nos últimos dias, o IDS tem marcado como suspeitas conexões que antes passavam como normais. Não sabe se o tráfego mudou ou se alguém alterou a configuração do classificador, e nada do que ele consulta indica qual modelo está ativo nem desde quando. Se muitas ocorrências parecidas não se confirmarem, a suspeita passa a ser o próprio classificador.]** 

Enquanto não consegue decidir, a lentidão continua e ele não sabe dizer à operação se alguém deve agir. **[NOVO: o segmento de onde partem as conexões atende o portal interno usado pelo atendimento, que já está lento. O erro custa nos dois sentidos: se descartar uma varredura real, a atividade pode evoluir sem resposta; se pedir um bloqueio indevido, a infraestrutura pode interromper o tráfego legítimo do portal e parar o atendimento.]** 

### 4. Elementos extraídos

| Elemento             | Evidência no cenário                                                                                                                                                                                                                                                                   |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ator(es)             | Thiago (P01, analista SOC L2, plantão noturno); equipe de infraestrutura, que executa a ação; operação, que aguarda a resposta; analista do próximo turno.                                                                                                                             |
| objetivo(s)          | Decidir se as conexões sinalizadas correspondem a um incidente real e **encaminhar** a quem precisa agir; não interromper um serviço legítimo por engano; deixar o caso compreensível para quem vem depois                                                                             |
| Contexto             | Plantão noturno no SOC, com uma tarefa em andamento interrompida pelo alerta; portal do atendimento lento enquanto a decisão não sai; pressão da operação por uma resposta.                                                                                                            |
| Recursos/informações | Console com logs crus; classificações do modelo misturadas ao restante do tráfego; captura de pacotes; *scripts* próprios; memória de turnos anteriores. **Ausentes:** histórico do ativo, comportamento habitual da origem, indicação de qual classificador está ativo e desde quando |
| Ações                | Interromper a tarefa anterior; abrir o console; montar consultas manuais por origem, destino, serviço e volume; comparar com o que conhece do ambiente; decidir; abrir chamado para a infraestrutura; avisar a operação; retomar a tarefa; escrever a passagem de plantão              |
| Problemas/rupturas   | Contexto da conexão disperso em várias ferramentas e guardado de memória; impossibilidade de saber se a mudança de comportamento vem do tráfego ou da configuração; tarefa interrompida difícil de retomar; fundamento da decisão não fica registrado                                  |
| Consequências        | Decisão demorada enquanto o portal segue lento; risco de descartar um ataque real ou de pedir um bloqueio que interrompe o atendimento; passagem de plantão incompleta, que torna Thiago um gargalo; suspeita sobre o classificador que não chega a Vanessa com informação suficiente  |

### 5. Implicações para as próximas entregas

- Decompor A02 (investigar uma conexão sinalizada) desde a chegada do alerta até o encaminhamento, com atenção ao ponto de decisão: o que Thiago confronta, com quais informações e quando consulta alguém. Considerar as três saídas da decisão (falso positivo, incidente, indefinido).
- Tratar **interrupção e retomada** como parte da tarefa, não como exceção; e tratar **encaminhamento e passagem de plantão** como subtarefas cujo produto é lido por outra pessoa.
- Verificar com analistas reais: (a) quais ferramentas usam hoje e em que ordem; (b) se reunir o contexto da conexão é de fato o ponto mais custoso; (c) se a saída do modelo basta para o julgamento ou se precisam de histórico e comportamento habitual; (d) como ficam sabendo hoje de uma mudança de configuração; (e) o que registram na passagem de plantão.
- Este cenário é a origem do sinal que inicia o cenário de Vanessa. A análise de tarefas deve mapear **o que Thiago sabe e o que Vanessa precisa receber** quando a suspeita recai sobre o classificador.
- **Fora desta análise:** a execução da contenção, que ocorre fora do recorte.

## Cenário C02 — Configurar pipeline e validar desempenho

**Autor(a):** Marcela Nalesso - 22.222.011-3   
**Persona(s) relacionada(s):** P02   
**Necessidade relacionada:** R02   
**Situação concreta da Entrega 1 relacionada:** H05, H10, H18   
**Hipóteses ainda presentes:** H05 e H10

### 1. Cenário inicial

Vanessa, administradora de infraestrutura e da plataforma de SOC, recebe uma notificação de que a rede vem apresentando mais alertas do que o habitual e que a qualidade das ocorrências detectadas mudou após a atualização dos parâmetros de monitoramento. Como responsável pelo pipeline de captura e pelo classificador ativo, ela precisa verificar se o algoritmo em uso continua adequado ao comportamento real da rede, se a carga de processamento está equilibrada e se a operação permanece estável. O problema é que essa validação não depende de um único dado: ela exige comparar indicativos de desempenho, histórico operacional e comportamento atual do tráfego para decidir se a alteração foi benéfica ou se o ambiente passou a produzir falso alarmes e ruído para a equipe. A decisão não é simplesmente técnica; ela impacta diretamente a confiabilidade da detecção e a qualidade do trabalho dos analistas que acompanham a rede.

### 2. Questões de refinamento

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
|---|---|---|---|
| Q1 | Que tipo de mudança no pipeline exige a intervenção da administradora? | Ajuda a delimitar quando a pessoa não é apenas operadora, mas responsável por configurar o sistema. | Entrega 1 e Entrega 3: H05 e persona P02. |
| Q2 | Como ela percebe que o sistema está fora do esperado sem depender de dados técnicos excessivos? | Revela a necessidade de indicadores claros e contexto de desempenho para tomada de decisão. | Entrega 3, persona P02, análise concorrencial. |
| Q3 | Quais impactos uma configuração inadequada pode causar na rede? | Aponta para a consequência operacional e para a gravidade do erro. | Entrega 1: H10 e contexto de uso. |
| Q4 | O que precisa ser comparado para que a escolha do algoritmo seja confiável? | Define a necessidade de dados de comparação e histórico de desempenho. | Entrega 1, Entrega 3 e cenário operacional do IDS. |

### 3. Cenário refinado

Vanessa é responsável por manter a plataforma de detecção funcionando com estabilidade. Em determinado momento, o ambiente começa a mostrar sinais de que a parametrização atual pode estar desbalanceada: há aumento de alertas, mudança na identificação de anomalias e variação no tempo de resposta do sistema. **[NOVO: A administradora percebe que a configuração atual não está mais refletindo com precisão o comportamento esperado da rede e que a decisão de ajuste não pode ser tomada apenas por observação isolada.]**

Ela então precisa verificar a integridade do pipeline, avaliar se o algoritmo ativo está sendo executado com os parâmetros adequados e analisar se o aumento de alertas é um reflexo de uma mudança real no ambiente ou apenas um efeito de calibração inadequada. **[NOVO: Esse processo exige comparação entre indicadores de desempenho, histórico operacional, carga do equipamento e dados recentes do tráfego, de modo que a decisão tenha suporte e não dependa de suposições.]**

O desafio central não é apenas alterar uma configuração, mas decidir com segurança se a plataforma continua confiável e se a operação da rede não será prejudicada. **[NOVO: Caso a troca de modelo ou o ajuste de limites seja feito sem contexto adequado, a rede pode sofrer queda de desempenho, aumentar falsos positivos e falhar ao sinalizar uma ameaça real.]** Por isso, a atividade exige uma visão de operação e estabilidade, com indicadores que apoiem a avaliação da qualidade do modelo e a confiança na mudança.

### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| Ator(es) | Vanessa, administradora de infraestrutura e da plataforma de SOC; pipeline de detecção; rede em operação; analistas de segurança afetados pelo comportamento do IDS. |
| Objetivo(s) | Validar a configuração atual do IDS, verificar o desempenho do modelo, ajustar parâmetros e confirmar que a operação da rede continua estável. |
| Contexto | Ambiente corporativo com infraestrutura crítica, monitoramento contínuo, operação em tempo real e necessidade de tomada de decisão técnica com impacto operacional. |
| Recursos/informações | Métricas de desempenho do algoritmo, taxa de alertas, histórico de operação, carga do equipamento embarcado, comportamento recente do tráfego e retorno dos analistas sobre a qualidade dos alertas. |
| Ações | Verificar sinais de desbalanceamento, comparar desempenho atual e esperado, ajustar parâmetros, validar a alteração e avaliar se o sistema permanece confiável. |
| Problemas/rupturas | Configuração inadequada, aumento de falsos positivos, instabilidade operacional, dificuldade para avaliar a qualidade do ajuste em tempo real e perda de confiança no sistema. |
| Consequências | Perda de confiabilidade da detecção, aumento do custo operacional, aumento de ruído para a equipe e risco de falha na identificação de ataques reais. |

### 5. Implicações para as próximas entregas

- A próxima análise deve focar na tarefa de ajuste e validação do pipeline do IDS, com atenção especial ao papel de Vanessa como responsável pela configuração.
- É necessário mapear quais métricas de desempenho devem aparecer para apoiar uma decisão segura de mudança de parâmetros ou de classificador.
- A interface futura não pode depender apenas de valores técnicos isolados; é preciso mostrar o impacto da alteração no comportamento real da rede e no contexto operacional.
- A análise de tarefas deve priorizar a comparação entre estados do sistema antes e depois de uma alteração, para permitir validação com menor risco e maior clareza de consequência.

> Repita para C02, C03... com autoria individual.

## Checklist

- [ ] Há um cenário completo por integrante.
- [ ] Cada cenário tem título, ator, objetivo, contexto e problema.
- [ ] O cenário possui origem rastreável na Entrega 1 ou justifica claramente a inclusão de uma nova situação.
- [ ] O texto descreve a situação atual, sem antecipar a solução.
- [ ] Para TCC sem interface original, o cenário descreve uma prática humana plausível relacionada à contribuição técnica, e não “a falta de uma tela”.
- [ ] Questões de refinamento acrescentam informação nova.
- [ ] O refinamento mostra claramente o que foi adicionado/alterado.
- [ ] Cenários são diferentes o suficiente para cobrir objetivos/problemas relevantes.
- [ ] Cada cenário está ligado a persona/necessidade na matriz de rastreabilidade.
