# Entrega 5 — Análise de tarefas: HTA, GOMS e CTT

**Data:** 13/09/2026     
**Status:** `🟩 concluída`     
**Responsabilidade:** cada integrante modela pelo menos 1 HTA, 1 GOMS e 1 CTT. As três técnicas podem abordar a mesma funcionalidade ou funcionalidades distintas, conforme a orientação da disciplina.

## Objetivo da atividade

Modelar tarefas importantes sob perspectivas complementares: decomposição hierárquica (HTA), estrutura de metas/métodos/operações (GOMS) e relações temporais entre tarefas (CTT). O diagrama deve ser acompanhado de interpretação textual.

## Para projetos cujo TCC não previa interface

Modele **tarefas humanas relacionadas ao uso da contribuição técnica**, e não a implementação interna do algoritmo. Exemplos de boas tarefas para análise:

- investigar uma consulta de baixo desempenho;
- configurar uma análise e selecionar parâmetros;
- submeter um dataset e verificar sua validade;
- acompanhar uma execução demorada;
- comparar dois resultados/modelos;
- interpretar uma recomendação e decidir se a aceita;
- localizar uma execução anterior usando busca/filtros;
- gerar e compartilhar um relatório;
- administrar papéis/permissões quando isso for parte do trabalho real;
- revisar um alerta e registrar uma decisão.

Um CRUD pode gerar tarefas relevantes, mas “cadastrar usuário” só merece modelagem se tiver significado no domínio (papéis, validações, riscos, permissões, dependências).

## Seleção das tarefas

| ID | Tarefa | Persona/cenário de origem | Frequência/criticidade | Autor responsável |
|---|---|---|---|---|
| T01 | Decidir se a configuração atual do IDS deve ser mantida, ajustada ou revertida | Vanessa / Cenário 02 | Alta | Marcela Nalesso |



> Priorize tarefas necessárias para que o usuário alcance objetivos centrais. Não desperdice a modelagem em ações triviais isoladas, como “clicar em login”, se o objetivo relevante é maior. Da mesma forma, não modele o funcionamento interno do algoritmo como se fosse uma tarefa humana.

---

## HTA — T01 {{nome da tarefa}}

**Autor(a):** {{nome — matrícula}}

### Descrição da tarefa

{{objetivo, ponto de início, conclusão esperada, contexto}}

### Diagrama

![HTA T01](../assets/05_tarefas/hta_t01.svg)

### Decomposição e planos

| ID | Objetivo/operação | Plano/ordem | Problema ou decisão de design observada |
|---|---|---|---|
| 0 | {{objetivo principal}} | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |

**Verificação do HTA:**

- O objetivo 0 representa uma meta do usuário?
- As subtarefas são necessárias e suficientes?
- Os **planos** indicam ordem, alternativa, repetição ou condição?
- A decomposição parou em nível útil para projeto de interação?

---

## GOMS — T02 {{nome da tarefa}}

**Autor(a):** {{nome — matrícula}}

### Goal

`G0: {{meta do usuário}}`

### Métodos, operadores e regras de seleção

- **Method M1:** {{...}}
  - Operators: {{perceber, apontar, clicar, digitar, decidir... conforme o nível adotado}}
- **Method M2:** {{...}}
  - Operators: {{...}}
- **Selection Rule SR1:** usar M1 quando {{condição}}; usar M2 quando {{condição}}.

> Não chame qualquer passo de “método”. Em GOMS, métodos são sequências alternativas capazes de atingir uma meta; regras de seleção explicam quando escolher entre eles.

---

## CTT — T03 {{nome da tarefa}}

**Autor(a):** {{nome — matrícula}}

### Descrição

{{...}}

### Diagrama

![CTT T03](../assets/05_tarefas/ctt_t03.svg)

### Legenda e relações temporais usadas

| Operador/relação | Significado no diagrama | Exemplo no modelo |
|---|---|---|
| {{...}} | {{...}} | {{...}} |

Identifique, quando aplicável, tarefas de usuário, sistema, interação e tarefas abstratas. Verifique se concorrência, escolha, habilitação, desabilitação e repetição estão representadas corretamente segundo a notação adotada em aula.

---

## HTA — T01: Decidir se a configuração atual do IDS deve ser mantida, ajustada ou revertida

**Autor(a):** Marcela Nalesso - 22.222.011-3   

### Descrição da tarefa

Vanessa, como administradora responsável pela operação do IDS e pela estabilidade da infraestrutura, inicia a tarefa quando observa aumento de alertas, ruído operacional e comportamento anômalo na rede. O objetivo é confirmar se o cenário exige manter a configuração atual, ajustar parâmetros do pipeline ou reverter uma alteração recente. A tarefa se conclui quando a decisão é tomada com base em diagnóstico, avaliação de impacto e validação do efeito sobre a operação da rede.

### Diagrama

![HTA T01](../assets/05_tarefas/hta_t02.svg)

### Decomposição e planos

| ID | Objetivo/operação | Plano/ordem | Problema ou decisão de design observada |
|---|---|---|---|
| 0 | Decidir se a configuração atual do IDS deve ser mantida, ajustada ou revertida | 1 > 2 > 3 > 4 > 5 | Vanessa precisa diagnosticar, avaliar risco e validar a decisão antes de agir. |
| 1 | Identificar que a operação do IDS está fora do comportamento esperado | 1.1 > 1.2 | O desvio deve ser confirmado antes de qualquer ajuste. |
| 1.1 | Verificar aumento de alertas e ruído operacional | 1 | O sinal inicial é relevante, mas não é suficiente para justificar uma mudança. |
| 1.2 | Comparar o comportamento atual com a linha de base da rede | 1 | A comparação evita decisões baseadas em anomalias isoladas ou temporárias. |
| 2 | Revisar o estado atual do pipeline | 2.1 || 2.2 || 2.3 | A causa do problema pode estar no algoritmo, na infraestrutura ou no comportamento recente do ambiente. |
| 2.1 | Verificar desempenho do algoritmo ativo | 2 | O algoritmo pode estar gerando falsos positivos ou classificações inadequadas. |
| 2.2 | Verificar carga e estabilidade da infraestrutura | 2 | A infraestrutura pode estar degradada mesmo quando o algoritmo está funcional. |
| 2.3 | Consultar o histórico recente do tráfego e dos alertas | 2 | O histórico ajuda a distinguir variação legítima de comportamento de falha operacional. |
| 3 | Avaliar impacto de uma possível mudança | 3.1 || 3.2 || 3.3 | A decisão precisa considerar risco, reversibilidade e efeito sobre a operação. |
| 3.1 | Comparar o modelo atual e o modelo candidato | 3 | A análise entre alternativas reduz a chance de ajustar o sistema pela causa errada. |
| 3.2 | Avaliar o efeito da mudança sobre analistas e operação da rede | 3 | As mudanças impactam diretamente o trabalho de investigação e a estabilidade do trânsito. |
| 4 | Decidir a ação de configuração | 4.1 [] 4.2 [] 4.3 [] 4.4 | A alternativa escolhida depende do diagnóstico e do risco estimado. |
| 4.1 | Manter a configuração atual | 4 | Manter é apropriado quando o comportamento está estável e aceitável. |
| 4.2 | Ajustar parâmetros do pipeline ou classificador ativo | 4 | O ajuste é adequado quando o problema é de calibração e não de falha estrutural. A troca é relevante quando a qualidade de detecção do modelo atual é insuficiente.  |
| 4.3 | Reverter a alteração e reavaliar | 4 | A reversão é preferível quando a alteração piorou o ambiente ou aumentou ruído. |
| 5 | Validar a decisão após a mudança | 5.1 > 5.2 > 5.3 > 5.4 | A validação confirma se a ação teve o efeito desejado e se a equipe foi informada. |
| 5.1 | Registrar o que mudou, quando e por quê | 5 | O registro cria rastreabilidade e suporte para análise posterior. |
| 5.2 | Monitorar o resultado após a alteração | 5 | A confirmação do efeito é essencial para saber se a decisão foi correta. |

**Verificação do HTA:**

- O objetivo 0 representa uma meta do usuário? Sim. Vanessa precisa decidir de forma fundamentada se deve manter, ajustar ou reverter a configuração do IDS.
- As subtarefas são necessárias e suficientes? Sim. Elas cobrem diagnóstico, revisão do pipeline, avaliação de impacto, tomada de decisão e validação final.
- Os **planos** indicam ordem, alternativa, repetição ou condição? Sim. Há sequência principal, paralelismo nas verificações e escolha explícita entre alternativas de ação.
- A decomposição parou em nível útil para projeto de interação? Sim. A estrutura chega ao nível de decisão e validação operacional, que é útil para definir requisitos de interface e informação.

---

## GOMS — T02: Decidir se a configuração atual do IDS deve ser mantida, ajustada ou revertida

**Autor(a):** Marcela Nalesso - 22.222.011-3   

### Goal

`G0: decidir se a configuração atual do IDS deve ser mantida, ajustada ou revertida`

### Métodos, operadores e regras de seleção

- **Method M1:** Diagnosticar que a operação saiu do esperado
  - **Selection Rule SR1:** usar M1 quando houver aumento de alertas, ruído operacional e sinais de que o sistema saiu do comportamento esperado
  - Operators:
    - M1.1: Verificar aumento de alertas e ruído operacional
    - M1.2: Comparar o comportamento atual com o comportamento normal da rede
    - M1.3: Verificar se a causa é do ambiente, do pipeline ou do classificador
- **Method M2:** Revisar o estado atual do pipeline
  - **Selection Rule SR2:** usar M2 quando a causa do desvio ainda não está clara e a pessoa precisa verificar a saúde do pipeline antes de agir
  - Operators:
    - M2.1: Revisar desempenho do algoritmo ativo
    - M2.2: Revisar carga e estabilidade da infraestrutura
    - M2.3: Comparar histórico recente do tráfego com o estado atual
- **Method M3:** Avaliar impacto da mudança antes de agir
  - **Selection Rule SR3:** usar M3 quando já existe uma possível mudança de parâmetro ou classificador e é necessário estimar impacto antes de aplicar alteração
  - Operators:
    - M3.1: Comparar modelo atual e modelo candidato
    - M3.2: Avaliar efeito sobre analistas e operação da rede
    - M3.3: Verificar se a troca ou ajuste pode ser revertida sem impacto grande
- **Method M4:** Decidir a ação de configuração
  - **Selection Rule SR4:** usar M4 quando o diagnóstico já foi concluído e a decisão de ação precisa ser tomada
  - Operators:
    - M4.1: Manter a configuração atual
    - M4.2: Ajustar parâmetros do pipeline
    - M4.3: Trocar o classificador ativo
    - M4.4: Reverter a alteração e reavaliar
- **Method M5:** Validar e documentar a decisão após a mudança
  - **Selection Rule SR5:** usar M5 quando a alteração foi aplicada e é necessário registrar e acompanhar o efeito para confirmar se a decisão foi correta
  - Operators:
    - M5.1: Registrar a alteração no histórico de configuração
    - M5.2: Registrar motivo, estado anterior e impacto esperado
    - M5.3: Informar os analistas que o comportamento do IDS mudou
    - M5.4: Monitorar o resultado após a alteração


> Não chame qualquer passo de “método”. Em GOMS, métodos são sequências alternativas capazes de atingir uma meta; regras de seleção explicam quando escolher entre eles.

---

## CTT — T03: Decidir se a configuração atual do IDS deve ser mantida, ajustada ou revertida

**Autor(a):** Marcela Nalesso - 22.222.011-3   

### Descrição

Vanessa identifica um desvio no comportamento do IDS, revisa o estado do pipeline, compara alternativas de configuração e decide se a operação deve ser mantida, ajustada ou revertida. A tarefa termina quando a decisão é validada, registrada e comunicada para que a equipe entenda a alternativa adotada e monitorize os efeitos da mudança.

### Diagrama

![CTT T03](../assets/05_tarefas/goms_ctt_t02.svg)

### Legenda e relações temporais usadas

| Operador/relação | Significado no diagrama | Exemplo no modelo |
|---|---|---|
| `>>` | Sequência | `M1 >> M2 >> M3 >> M4 >> M5` |
| `||` | Concorrência/paralelismo | `M2.1 || M2.2 || M2.3` |
| `[]` | Escolha entre alternativas | `M4.1 [] M4.2 [] M4.3 [] M4.4` |
| `>` | Habilitação | a etapa de validação é habilitada somente após a decisão de ação |
| `*` | Repetição | pode ocorrer em ciclos de ajuste e reavaliação |

Os métodos M1 a M5 representam uma sequência principal de execução: primeiro Vanessa diagnostica a anomalia, depois revisa o pipeline, em seguida avalia a mudança, toma a decisão e, por fim, valida o efeito da decisão. O tipo de tarefa varia conforme a etapa: M1 é uma tarefa abstrata e de usuário, M2 envolve interação com o sistema e revisão de dados operacionais, M3 é de interação e avaliação, M4 combina abstração, decisão do usuário e interação com informações do ambiente, e M5 combina interação, usuário e sistema para registrar e monitorar a ação. A relação principal é sequencial, com paralelismo na revisão do pipeline e escolha explícita entre manter, ajustar, trocar ou reverter a configuração.

---

## Síntese da equipe

Quais problemas de interação, oportunidades e requisitos apareceram a partir das modelagens? Quais tarefas irão para o protótipo e para o teste de usabilidade?

## Checklist

- [ ] Cada integrante produziu ao menos 1 HTA, 1 GOMS e 1 CTT.
- [ ] Cada artefato identifica autor e tarefa.
- [ ] Diagramas são legíveis e possuem fonte editável quando possível.
- [ ] HTA contém planos, não apenas árvore de tópicos.
- [ ] GOMS distingue Goals, Operators, Methods e Selection Rules.
- [ ] CTT usa operadores temporais e tipos de tarefa coerentes.
- [ ] Há texto explicando cada diagrama.
- [ ] Tarefas estão ligadas a cenários/personas na rastreabilidade.
- [ ] Em TCC técnico, as tarefas descrevem o que a pessoa faz com a contribuição/resultados, não passos internos do código.
- [ ] CRUDs, relatórios, filtros e atividades administrativas foram escolhidos por relevância ao objetivo do usuário.
