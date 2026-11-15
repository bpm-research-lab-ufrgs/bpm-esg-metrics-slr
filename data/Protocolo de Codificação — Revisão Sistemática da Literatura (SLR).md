# Protocolo de Codificação — Revisão Sistemática da Literatura (SLR)

Este documento define o esquema de extração de dados para os **110 estudos** da planilha `matriz_extracao_110_estudos`.

---

## 1\. Metadados Bibliográficos (Conferência)

Campos pré-preenchidos a partir da triagem (`CORPUS_CARACTERIZACAO`). Devem apenas ser conferidos e padronizados:

| Campo | Formato / Padrão | Regra de Conferência |
| :---- | :---- | :---- |
| **Study ID** | `SLR-XXXXX` | Identificador único imutável (ex.: `SLR-00003`). |
| **Título** | Texto | Título original em inglês (remover traduções entre colchetes, ex.: `SLR-00428`). |
| **Autores** | `Sobrenome I.; ...` | Padronizar caracteres especiais para UTF-8 (ex.: corrigir `M{\""u}ller` para `Müller`). |
| **Ano** | `AAAA` | Ano oficial de publicação (`2016` a `2026`). |
| **DOI** | Texto | Apenas o identificador (ex.: `10.1016/j.procs.2026.07.078`), sem `https://doi.org/`. |
| **Periódico / Evento** | Texto | Nome completo do veículo de publicação. |
| **Fonte** | Lista (`;` ) | `Scopus` \| `IEEE Xplore` \| `ACM Digital Library`. |
| **Keywords** | Lista (`;` ) | Palavras-chave dos autores separadas por `;` . |
| **URL** | Link | URL da base ou preencher com `https://doi.org/{DOI}` quando vazio (ex.: `SLR-02738`). |

---

## 2\. Campos Analíticos (Extração na Leitura)

### `Research_Type`

* **Regra:** Valor único (estratégia metodológica predominante).  
* **Domínio:**  
  * `Empirical - Case Study`: Estudo de caso único ou múltiplo em organização/setor real.  
  * `Empirical - Survey / Quantitative`: Questionário, modelagem estatística (PLS-SEM) ou dados secundários.  
  * `Empirical - Qualitative / Delphi`: Entrevistas, grupos focais ou painéis Delphi.  
  * `Design Science / Artifact Development`: Proposição de framework, arquitetura, algoritmo, linguagem ou ferramenta.  
  * `Conceptual / Theoretical`: Ensaio teórico, taxonomia ou modelo conceitual sem artefato computacional ou coleta empírica.  
  * `Secondary Study (SLR / Bibliometric)`: Revisão sistemática, mapeamento sistemático ou bibliometria.

### `Industry`

* **Regra:** Valor único (ou separado por `;`  se multissetorial).  
* **Domínio:**  
  * `Cross-Industry / Domain-Agnostic`: Aplicável a qualquer setor ou sem contexto específico.  
  * `Manufacturing & Heavy Industry`: Manufatura, plásticos, mineração, metalurgia, indústria florestal.  
  * `Construction & Built Environment`: Construção civil, megaprojetos, BIM e edificações.  
  * `Energy, Oil & Gas`: Energia elétrica, óleo e gás, eficiência energética industrial.  
  * `Agriculture & Food`: Agronegócio, agricultura inteligente, cadeias de alimentos.  
  * `Financial Services & Banking`: Bancos, finanças, previdência, microfinanças.  
  * `Logistics & Supply Chain`: Transporte, logística multimodal, cadeia de suprimentos.  
  * `Public Sector, Healthcare & Education`: Governo, saúde, instituições de ensino superior (HEIs).  
  * `IT & Software Engineering`: Desenvolvimento de software, TI verde, computação em nuvem.

### `BPM_Approach`

* **Regra:** Múltipla escolha permitida; separar categorias com `;` .  
* **Domínio:**  
  * `Process Modeling & Notation`: Extensões de BPMN, UML, linguagens visuais, modelagem de contexto/recursos.  
  * `Process Mining & Analytics`: Descoberta de processos, *conformance checking* em logs, análise preditiva.  
  * `Process Redesign & Optimization`: Reengenharia (BPR), Lean/Green BPM, *workflow patterns*, simulação.  
  * `Compliance & Governance`: *Compliance checking*, gestão de requisitos regulatórios, auditoria de processos.  
  * `Process Execution & Automation`: Motores de fluxo (ex.: Camunda), RPA, integração com ERP/S-ERP.  
  * `BPM Maturity & Strategy`: Maturidade em BPM, gestão de mudanças, alinhamento estratégico, fatores humanos.  
  * `Emerging Tech in BPM`: IA/LLMs, Blockchain, IoT/Digital Twins ou Zero-Knowledge Proofs (ZKP).

### `Sustainability_Scope`

* **Regra:** Valor único (foco predominante).  
* **Domínio:**  
  * `Environmental (Green BPM)`: Emissões de GEE/carbono, energia, resíduos, água ou economia circular.  
  * `Social`: Fatores humanos, segurança do trabalhador, ergonomia, CSR ou inclusão.  
  * `Governance & Compliance`: Transparência, rastreabilidade, conformidade legal (ex.: GDPR), auditoria e riscos.  
  * `Triple Bottom Line (TBL) / Holistic ESG`: Integração explícita das dimensões ambiental, social e econômica/governança.  
  * `SDG-Aligned`: Estruturado explicitamente em torno dos Objetivos de Desenvolvimento Sustentável (ODS/SDGs).

### `Regulatory_Context`

* **Regra:** Valor único obrigatório.  
* **Domínio:**  
  * `Explicit`: Cita, modela ou verifica normas, leis ou padrões específicos (ex.: GDPR, GRI, ISO 14001).  
  * `Implicit / General`: Menciona pressões institucionais, auditoria ou conformidade de forma genérica.  
  * `None`: Não aborda aspectos regulatórios ou normativos.

### `Main_Contribution`

* **Regra:** Valor único (entregável central do estudo).  
* **Domínio:**  
  * `Framework / Conceptual Model`: Estrutura conceitual, arquitetura de referência ou modelo teórico.  
  * `Method / Methodology`: Método passo a passo, algoritmo, técnica de otimização ou avaliação.  
  * `Software Tool / Prototype`: Ferramenta implementada, plugin, dashboard ou sistema funcional.  
  * `Modeling Language / Extension / Patterns`: Extensão de sintaxe/semântica BPMN, ontologia ou catálogo de padrões.  
  * `Empirical Evidence / Synthesis`: Resultados empíricos (fatores, barreiras, impactos) ou síntese da literatura.

### `Metric_Present`

* **Regra:** Valor único.  
* **Domínio:**  
  * `Yes - Quantitative / Formalized`: Fórmulas matemáticas, KPIs definidos, indicadores GRI/O-LCA ou métricas formalizadas.  
  * `Yes - Qualitative / Conceptual`: Critérios ou indicadores descritivos, sem formalização matemática/operacional.  
  * `No`: Não apresenta métricas ou indicadores.

### `Operationalization_Level`

* **Regra:** Valor único (maturidade prática da proposta).  
* **Domínio:**  
  * `Level 1 - Conceptual`: Definições abstratas, diretrizes gerais ou diagramas de alto nível.  
  * `Level 2 - Semi-Formal / Structured`: Modelos estruturados, regras lógicas (LTL, fuzzy) ou etapas definidas, sem software executável.  
  * `Level 3 - Executable / Implemented`: Software implementado, algoritmos testados em logs, protótipos funcionais ou uso industrial.

### `Empirical_Validation`

* **Regra:** Valor único.  
* **Domínio:**  
  * `Real-World Case Study / Industrial Trial`: Validado em organização real com dados reais.  
  * `Survey / Statistical Dataset`: Validado com amostra estatística de respondentes ou bases corporativas.  
  * `Illustrative Scenario / Simulation`: Validado com exemplo ilustrativo, cenário fictício ou simulação.  
  * `Expert Evaluation (Delphi / Interviews)`: Validado por especialistas externos sem aplicação operacional.  
  * `None`: Sem validação empírica.

---

## 3\. Relevância para RQs e Evidências

| Campo | Domínio / Formato | Regra de Preenchimento |
| :---- | :---- | :---- |
| **RQ1\_Relevant** | `High` \| `Medium` \| `Low` \| `No` | **Abordagens BPM e Tecnologias:** `High` (evidência direta), `Medium` (parcial), `Low` (tangencial), `No` (não aborda). |
| **RQ2\_Relevant** | `High` \| `Medium` \| `Low` \| `No` | **Métricas e Operacionalização:** Mesmo critério acima aplicado a indicadores e nível de implementação. |
| **RQ3\_Relevant** | `High` \| `Medium` \| `Low` \| `No` | **Compliance e Regulação:** Mesmo critério acima aplicado a requisitos regulatórios e conformidade. |
| **Justification\_Evidence** | Texto objetivo | Síntese curta dos achados que justificam a codificação atribuída ao artigo. |
| **Evidence\_Page\_Section** | `Sec. X, p. Y` | Localização exata da evidência no artigo (ex.: `Sec. 4.2, p. 12`). |

---

## 4\. Regras Rápidas de Consistência

1. **Sem células vazias:** Nos campos analíticos, use sempre `None` ou `No` quando o critério não se aplicar.  
2. **Critério conservador:** Em caso de dúvida entre dois níveis (ex.: `Level 2` vs. `Level 3` ou `High` vs. `Medium`), selecione o nível **inferior** e justifique em `Justification_Evidence`.  
3. **Piloto de calibração:** Codifique os **11 primeiros estudos (10%)** e valide a aderência das categorias antes de extrair os demais.