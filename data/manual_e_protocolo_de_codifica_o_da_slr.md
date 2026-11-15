# Manual e Protocolo de Codificação — Revisão Sistemática da Literatura (SLR)

## 1. Diagnóstico e Revisão das Planilhas

Após a inspeção da pasta de trabalho `corpus_110_estudos.xlsm` e da matriz em CSV (`matriz_extracao_110_estudos.csv`), constatou-se a seguinte estrutura:

* **Volume do Corpus:** 110 estudos primários selecionados (`SLR-00002` a `SLR-02744`), publicados entre **2016 e 2026**.
* **Arquitetura das Abas/Tabelas:**
  1. `CORPUS_CARACTERIZACAO`: Contém os metadados bibliográficos essenciais extraídos das bases de busca (Scopus, IEEE Xplore, ACM Digital Library).
  2. `DICIONARIO`: Define o esquema conceitual e operacional de **26 variáveis** (metadados + dimensões analíticas + rastreabilidade de evidências).
  3. `matriz_extracao_110_estudos`: Arquivo/aba destino destinado ao preenchimento dos dados extraídos de cada artigo.

### Pontos de Atenção e Consistência Identificados na Revisão

1. **Linhagem de Dados (Metadados):** Os campos `Priority`, `Tipo de documento`, `Idioma`, `Keywords` e `Keywords indexadas` constam no `DICIONARIO`, mas não aparecem na visualização resumida de `CORPUS_CARACTERIZACAO` (que exibe 8 colunas básicas). Antes de iniciar a leitura completa, certifique-se de que esses metadados já estejam pré-populados na `matriz_extracao_110_estudos` para evitar retrabalho.
2. **Caracteres Especiais e Codificação:** Em registros oriundos do ACM Digital Library (ex.: `SLR-01765`, `SLR-01771`), há sequências de escape LaTeX nos nomes dos autores (ex.: `B{\""u}del`, `M{\""u}ller`). Recomenda-se higienizar para UTF-8 padrão (`Büdel`, `Müller`) antes da síntese bibliométrica.
3. **Ausência de URLs:** Registros específicos do IEEE Xplore sem vínculo simultâneo na Scopus (`SLR-02738` e `SLR-02744`) possuem o campo `URL` vazio, embora disponham de `DOI` válido. O link pode ser reconstruído via prefixo padrão `https://doi.org/{DOI}`.
4. **Padronização de Domínios:** O `DICIONARIO` descreve o significado dos campos, mas **não estabelece listas fechadas (vocabulário controlado)** para os campos categóricos. Para garantir confiabilidade entre avaliadores (*inter-rater reliability*) e viabilizar análises quantitativas futuras, este documento estabelece o **Livro de Códigos (Codebook)** oficial abaixo.

---

## 2. Livro de Códigos (Codebook) e Regras de Extração

### Bloco A: Controle e Metadados Bibliográficos
*(Campos de identificação e triagem — preenchimento automático ou conferência)*

| Campo | Tipo de Dado | Regra de Preenchimento / Domínio |
| :--- | :--- | :--- |
| **Priority** | Categórico (Único) | `P1` (Alta prioridade / aderência direta aos 3 eixos: BPM + Sustentabilidade/ESG + Compliance/Métricas); `P2` (Média prioridade / aderência parcial); `P3` (Apoio conceitual/bibliométrico). |
| **Study ID** | Texto (Chave) | Identificador imutável no formato `SLR-XXXXX` (ex.: `SLR-00003`). |
| **Título** | Texto | Título original completo. Se houver tradução entre colchetes (ex.: `SLR-00428`), manter apenas o título em inglês. |
| **Autores** | Texto | Formato `Sobrenome Iniciais.; Sobrenome Iniciais.` padronizado em UTF-8. |
| **Ano** | Numérico (AAAA) | Ano de publicação oficial (`2016` a `2026`). |
| **DOI** | Texto | Apenas o identificador (ex.: `10.1016/j.procs.2026.07.078`), sem o prefixo URL. |
| **Periódico / Evento** | Texto | Nome completo do veículo sem abreviações informais. |
| **Tipo de documento** | Categórico (Único) | `Journal Article` \| `Conference Paper` \| `Book Chapter` \| `Review`. |
| **Idioma** | Categórico (Único) | Código ISO ou nome padrão: `English` (predominante). |
| **Bases onde foi encontrado** | Categórico (Múltiplo) | Separado por `; `: `Scopus` \| `IEEE Xplore` \| `ACM Digital Library`. |
| **Keywords** | Texto | Palavras-chave dos autores separadas por `; `. |
| **Keywords indexadas** | Texto | Termos controlados da base separados por `; `. |
| **URL** | Link | URL da base ou `https://doi.org/{DOI}` quando ausente. |

---

### Bloco B: Caracterização Metodológica e Contextual

#### 1. `Research_Type` (Tipo de Pesquisa)
*Regra: Selecionar a estratégia metodológica predominante (valor único).*
* `Empirical - Case Study`: Estudo de caso único ou múltiplo em organização/setor real.
* `Empirical - Survey / Quantitative`: Levantamento por questionário, modelagem de equações estruturais (PLS-SEM) ou análise estatística de dados secundários.
* `Empirical - Qualitative / Delphi`: Entrevistas em profundidade, grupos focais ou painéis Delphi.
* `Design Science / Artifact Development`: Proposição de framework, arquitetura, algoritmo, linguagem de modelagem ou ferramenta, com ou sem demonstração/prova de conceito.
* `Conceptual / Theoretical`: Ensaio teórico, taxonomia ou modelo conceitual sem desenvolvimento de artefato computacional ou coleta empírica.
* `Secondary Study (SLR / Bibliometric)`: Revisão sistemática da literatura, mapeamento sistemático ou análise bibliométrica.

#### 2. `Industry` (Setor de Aplicação)
*Regra: Identificar o setor onde a proposta foi aplicada ou avaliada (valor único ou separado por `; ` se multissetorial).*
* `Cross-Industry / Domain-Agnostic`: Aplicável a qualquer setor ou sem contexto setorial específico.
* `Manufacturing & Heavy Industry`: Manufatura discreta, plásticos, mineração, metalurgia, indústria florestal.
* `Construction & Built Environment`: Construção civil, megaprojetos, BIM e edificações.
* `Energy, Oil & Gas`: Energia elétrica, óleo e gás, eficiência energética industrial.
* `Agriculture & Food`: Agronegócio, agricultura inteligente, cadeias de alimentos.
* `Financial Services & Banking`: Bancos, finanças, previdência, microfinanças.
* `Logistics & Supply Chain`: Transporte, logística multimodal, gestão da cadeia de suprimentos.
* `Public Sector, Healthcare & Education`: Governo eletrônico, saúde, instituições de ensino superior (HEIs).
* `IT & Software Engineering`: Desenvolvimento de software, TI verde, computação em nuvem.

---

### Bloco C: Dimensões Analíticas da Pesquisa (BPM, Sustentabilidade e Compliance)

#### 3. `BPM_Approach` (Abordagem de BPM)
*Regra: Múltipla escolha permitida. Separar categorias exatamente por ponto e vírgula e espaço (`; `).*
* `Process Modeling & Notation`: Extensões de BPMN, UML, linguagens visuais, modelagem consciente de contexto ou recursos.
* `Process Mining & Analytics`: Descoberta de processos, verificação de conformidade (*conformance checking*) em logs de eventos, análise preditiva.
* `Process Redesign & Optimization`: Reengenharia (BPR), Lean/Green BPM, padrões de fluxo (*workflow patterns*), simulação de processos.
* `Compliance & Governance`: Verificação de conformidade (*compliance checking*), gestão de requisitos regulatórios, auditoria de processos.
* `Process Execution & Automation`: Motores de fluxo (ex.: Camunda), automação inteligente, RPA, integração com ERP/S-ERP.
* `BPM Maturity & Strategy`: Maturidade em BPM, gestão de mudanças, alinhamento estratégico e fatores organizacionais/humanos.
* `Emerging Tech in BPM`: Aplicação de IA/LLMs, Blockchain, IoT/Gêmeos Digitais ou ZKP (Zero-Knowledge Proofs) integrados a processos.

#### 4. `Sustainability_Scope` (Escopo de Sustentabilidade / ESG)
*Regra: Selecionar o foco predominante ou combinação (valor único).*
* `Environmental (Green BPM)`: Foco exclusivo ou predominante em emissões de GEE/carbono, consumo de energia, resíduos, água ou economia circular.
* `Social`: Foco em fatores humanos, segurança do trabalhador, ergonomia, responsabilidade social corporativa (CSR) ou inclusão.
* `Governance & Compliance`: Foco em transparência, rastreabilidade, conformidade legal/regulatória (ex.: GDPR), auditoria e gestão de riscos.
* `Triple Bottom Line (TBL) / Holistic ESG`: Abordagem integrada que equilibra explicitamente as dimensões ambiental, social e econômica/governança.
* `SDG-Aligned`: Estudos estruturados explicitamente em torno dos Objetivos de Desenvolvimento Sustentável (ODS/SDGs) da ONU.

#### 5. `Regulatory_Context` (Contexto Regulatório)
*Regra: Valor único obrigatório.*
* `Explicit`: O estudo menciona, modela ou verifica normas, leis, diretrizes ou padrões específicos (ex.: GDPR, GRI, ISO 14001, normas ambientais/setoriais).
* `Implicit / General`: Menciona pressões institucionais, auditoria ou conformidade de forma genérica, sem citar marcos regulatórios específicos.
* `None`: Não aborda aspectos regulatórios ou normativos.

#### 6. `Main_Contribution` (Natureza da Contribuição Principal)
*Regra: Valor único representando o entregável central do artigo.*
* `Framework / Conceptual Model`: Estrutura conceitual, arquitetura de referência ou modelo teórico.
* `Method / Methodology`: Método passo a passo, algoritmo, técnica de otimização ou abordagem de avaliação.
* `Software Tool / Prototype`: Ferramenta implementada, plugin, dashboard ou sistema funcional (ex.: *GaiaTool*).
* `Modeling Language / Extension / Patterns`: Extensão de sintaxe/semântica BPMN, ontologia ou catálogo de padrões (*green patterns*, *compliance patterns*).
* `Empirical Evidence / Synthesis`: Resultados empíricos (fatores críticos, barreiras, impactos) ou síntese da literatura.

---

### Bloco D: Métricas, Operacionalização e Validação

#### 7. `Metric_Present` (Presença de Métricas ou Indicadores)
*Regra: Valor único.*
* `Yes - Quantitative / Formalized`: Apresenta fórmulas matemáticas, KPIs definidos, indicadores GRI/O-LCA ou métricas formalizadas de desempenho/sustentabilidade.
* `Yes - Qualitative / Conceptual`: Discute indicadores ou critérios de avaliação de forma descritiva, sem formalização matemática ou operacional.
* `No`: Não apresenta métricas ou indicadores.

#### 8. `Operationalization_Level` (Nível de Operacionalização)
*Regra: Avalia o quão pronta para uso prático está a proposta do estudo (valor único).*
* `Level 1 - Conceptual`: Apenas definições abstratas, diretrizes gerais ou diagramas de alto nível.
* `Level 2 - Semi-Formal / Structured`: Modelos estruturados, regras lógicas (ex.: LTL, regras fuzzy), matrizes ou frameworks com etapas definidas, mas sem implementação executável.
* `Level 3 - Executable / Implemented`: Artefato implementado em software, algoritmos testados em logs reais/sintéticos, protótipos funcionais ou aplicação direta em operação industrial.

#### 9. `Empirical_Validation` (Tipo de Validação Empírica)
*Regra: Valor único.*
* `Real-World Case Study / Industrial Trial`: Validado em ambiente organizacional real com dados reais.
* `Survey / Statistical Dataset`: Validado por meio de amostra estatística de respondentes ou bases de dados corporativas.
* `Illustrative Scenario / Simulation`: Validado por meio de exemplo ilustrativo, cenário fictício ou simulação computacional.
* `Expert Evaluation (Delphi / Interviews)`: Validado por especialistas externos sem aplicação operacional.
* `None`: Sem validação empírica (apenas argumentação teórica ou revisão).

---

### Bloco E: Alinhamento às Questões de Pesquisa (RQs) e Rastreabilidade

*(Nota: Caso as RQs do seu protocolo ainda não estejam fixadas na planilha, utilize a correspondência padrão abaixo baseada na estrutura do dicionário)*:
* **RQ1 (Caracterização & Abordagens BPM):** Como as abordagens de BPM e tecnologias habilitadoras são empregadas para promover a sustentabilidade/ESG?
* **RQ2 (Métricas & Operacionalização):** Quais métricas/indicadores de sustentabilidade são utilizados nos processos de negócio e qual seu nível de operacionalização?
* **RQ3 (Compliance & Contexto Regulatório):** Como os requisitos regulatórios e de conformidade (*compliance*) são integrados e verificados em processos de negócio sustentáveis?

| Campo | Domínio / Formato | Regra de Preenchimento |
| :--- | :--- | :--- |
| **RQ1_Relevant** | `High` \| `Medium` \| `Low` \| `No` | `High`: Responde diretamente com evidências; `Medium`: Contribui parcialmente; `Low`: Menção tangencial; `No`: Não se aplica. |
| **RQ2_Relevant** | `High` \| `Medium` \| `Low` \| `No` | Mesmo critério acima, focado em indicadores, métricas e operacionalização. |
| **RQ3_Relevant** | `High` \| `Medium` \| `Low` \| `No` | Mesmo critério acima, focado em regulação, normas e *compliance checking*. |
| **Justification_Evidence** | Texto estruturado | Resumo objetivo justificando as classificações atribuídas, contendo trechos-chave ou síntese dos achados do artigo. |
| **Evidence_Page_Section** | Texto padronizado | Referência exata da localização no PDF no formato `Sec. X, p. Y` (ex.: `Sec. 4.2, p. 12` ou `Section 3, pp. 45-47`). |

---

## 3. Procedimento Operacional Padrão (SOP) para Extração

1. **Triagem Rápida (`Priority`):** Utilize a coluna `Priority` já atribuída (ou classifique na leitura dinâmica de *Title + Abstract + Conclusion*) para priorizar os estudos `P1`.
2. **Leitura Direcionada:**
   * Para preencher `Research_Type`, `Industry` e `Empirical_Validation` $\rightarrow$ consultar *Methodology / Case Study / Evaluation*.
   * Para preencher `BPM_Approach`, `Sustainability_Scope`, `Main_Contribution` e `Operationalization_Level` $\rightarrow$ consultar *Proposed Approach / Framework / Architecture*.
   * Para preencher `Regulatory_Context` e `Metric_Present` $\rightarrow$ consultar *Indicators / Compliance Rules / Discussion*.
3. **Regra de Desempate e Incerteza:**
   * Na dúvida entre dois níveis de operacionalização ou relevância de RQ, opte pelo nível **mais conservador** (inferior) e registre o motivo em `Justification_Evidence`.
   * Nunca deixe células analíticas em branco: utilize `None` ou `No` conforme o domínio do campo, garantindo que o dataset esteja limpo para análises futuras em Python/R ou Excel.
4. **Calibração (Piloto de 10%):** Codifique inicialmente uma amostra de **11 estudos** (ex.: os 11 primeiros da lista ou estratificados por ano), revise a aderência às categorias deste manual e ajuste eventuais ambiguidades antes de avançar para os 99 restantes.
