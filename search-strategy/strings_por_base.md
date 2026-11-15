# Estratégias de busca por fonte bibliográfica

Este documento registra como cada fonte bibliográfica foi consultada durante a Revisão Sistemática da Literatura. As buscas foram realizadas em julho e agosto de 2026, considerando publicações de 2016 a 2026 nos idiomas português e inglês.

---

## Scopus

**Campo:** `TITLE-ABS-KEY`  
**Idioma da expressão:** inglês  
**Data registrada:** 16 de agosto de 2026  
**Registros recuperados:** 1.765

### Expressão utilizada

```text
TITLE-ABS-KEY(
("BPM" OR "business process" OR "process management" OR "process compliance" OR "process performance" OR "process assessment" OR "green BPM" OR "sustainable BPM" OR "sustainable process management")
AND
("ESG" OR "environmental, social and governance" OR "sustainability" OR "socio-environmental" OR "socioenvironmental" OR "climate" OR "climate risk" OR "regulatory compliance" OR "regulatory requirement")
AND
("metric" OR "indicator" OR "measur" OR "evaluat" OR "assess" OR "framework" OR "model")
)
```

---

## ACM Digital Library

**Campo:** `AllField`  
**Idioma da expressão:** inglês  
**Período da consulta:** julho–agosto de 2026  
**Registros exportados:** 1.000

### Expressão utilizada

```text
AllField:((
"BPM" OR "business process" OR "process management" OR "process compliance" OR "process performance" OR "process assessment" OR "green BPM" OR "sustainable BPM" OR "sustainable process management"
)
AND
(
"ESG" OR "environmental, social and governance" OR "sustainability" OR "socio-environmental" OR "socioenvironmental" OR "climate" OR "climate risk" OR "regulatory compliance" OR "regulatory requirement"
)
AND
(
"metric" OR "indicator" OR "measur" OR "evaluat" OR "assess" OR "framework" OR "model"
))
```

---

## IEEE Xplore

**Campo:** `All Metadata`  
**Idioma da expressão:** inglês  
**Período da consulta:** julho–agosto de 2026  
**Ocorrências recuperadas nas rodadas:** 200  
**Registros únicos após deduplicação interna da fonte:** 150

A expressão completa não pôde ser processada de forma estável em uma única consulta pela interface do IEEE Xplore. Por essa razão, a estratégia foi dividida em oito rodadas. Em cada rodada, manteve-se o bloco referente à sustentabilidade/ASG/requisitos regulatórios e o bloco referente a métricas/avaliação, variando-se apenas o termo do bloco relacionado a processos.

### Bloco 2 mantido nas rodadas

```text
("All Metadata":"ESG" OR "All Metadata":"environmental, social and governance" OR "All Metadata":"sustainability" OR "All Metadata":"socio-environmental" OR "All Metadata":"socioenvironmental" OR "All Metadata":"climate" OR "All Metadata":"climate risk" OR "All Metadata":"regulatory compliance" OR "All Metadata":"regulatory requirement")
```

### Bloco 3 mantido nas rodadas

```text
("All Metadata":"metric" OR "All Metadata":"indicator" OR "All Metadata":"measur" OR "All Metadata":"evaluat" OR "All Metadata":"assess" OR "All Metadata":"framework" OR "All Metadata":"model")
```

### Rodadas executadas

1. `BPM` — 13 registros  
2. `business process` — 88 registros  
3. `green BPM` — 3 registros  
4. `process assessment` — 3 registros  
5. `process compliance` — 4 registros  
6. `process management` — 62 registros  
7. `process performance` — 26 registros  
8. `sustainable process management` — 1 registro

A forma geral de cada rodada foi:

```text
("All Metadata":"TERMO_DO_BLOCO_1")
AND
[BLOCO 2 — sustentabilidade/ASG/requisitos regulatórios]
AND
[BLOCO 3 — métricas/avaliação]
```

**Total:** 200 ocorrências.  
**Após deduplicação interna:** 150 registros únicos.

**Observação:** não há registro consolidado de uma rodada separada para `sustainable BPM`. As oito rodadas acima correspondem aos arquivos efetivamente incorporados à consolidação.

---

## SciELO

**Estratégia:** busca com a expressão-base em português  
**Período da consulta:** julho–agosto de 2026  
**Registros recuperados:** 1  
**Registros incorporados à base consolidada:** 1

### Expressão utilizada

```text
("BPM" OR "gestão de processos de negócio" OR "gestão por processos" OR "processo de negócio" OR "conformidade de processos" OR "conformidade em processos" OR "desempenho de processos" OR "avaliação de processos" OR "Green BPM" OR "BPM verde" OR "BPM sustentável" OR "gestão sustentável de processos")
AND
("ASG" OR "ambiental, social e governança" OR "ambiental social e governança" OR "sustentabilidade" OR "sustentabilidade corporativa" OR "socioambiental" OR "risco climático" OR "riscos climáticos" OR "risco socioambiental" OR "conformidade regulatória" OR "requisito regulatório" OR "requisitos regulatórios")
AND
("métrica" OR "métricas" OR "indicador" OR "indicadores" OR "mensuração" OR "avaliação" OR "avaliar" OR "aderência" OR "conformidade" OR "framework" OR "modelo" OR "modelos")
```

**Observação:** o campo específico da interface utilizado na consulta não ficou registrado na base consolidada; por isso, não é atribuído retrospectivamente um campo específico.

---

## SBC OpenLib (SOL)

**Estratégia:** busca com a expressão-base em português  
**Período da consulta:** julho–agosto de 2026  
**Registros recuperados:** 2  
**Registros incorporados à base consolidada:** 0

### Expressão utilizada

```text
("BPM" OR "gestão de processos de negócio" OR "gestão por processos" OR "processo de negócio" OR "conformidade de processos" OR "conformidade em processos" OR "desempenho de processos" OR "avaliação de processos" OR "Green BPM" OR "BPM verde" OR "BPM sustentável" OR "gestão sustentável de processos")
AND
("ASG" OR "ambiental, social e governança" OR "ambiental social e governança" OR "sustentabilidade" OR "sustentabilidade corporativa" OR "socioambiental" OR "risco climático" OR "riscos climáticos" OR "risco socioambiental" OR "conformidade regulatória" OR "requisito regulatório" OR "requisitos regulatórios")
AND
("métrica" OR "métricas" OR "indicador" OR "indicadores" OR "mensuração" OR "avaliação" OR "avaliar" OR "aderência" OR "conformidade" OR "framework" OR "modelo" OR "modelos")
```

Os dois registros recuperados foram descartados na verificação preliminar por não apresentarem aderência ao escopo da revisão.

**Observação:** o campo específico da interface utilizado na consulta não ficou registrado na base consolidada; por isso, não é atribuído retrospectivamente um campo específico.

---

## SpringerLink

**Estratégia:** tentativa de busca com a expressão-base em inglês  
**Período da consulta:** julho–agosto de 2026  
**Resultado:** nenhum registro utilizável incorporado à revisão

### Expressão-base considerada

```text
("BPM" OR "business process" OR "process management" OR "process compliance" OR "process performance" OR "process assessment" OR "green BPM" OR "sustainable BPM" OR "sustainable process management")
AND
("ESG" OR "environmental, social and governance" OR "sustainability" OR "socio-environmental" OR "socioenvironmental" OR "climate" OR "climate risk" OR "regulatory compliance" OR "regulatory requirement")
AND
("metric" OR "indicator" OR "measur" OR "evaluat" OR "assess" OR "framework" OR "model")
```

Durante a coleta, a consulta não produziu resultados utilizáveis. Testes simplificados também não retornaram resultados consistentes, razão pela qual nenhum registro da SpringerLink foi incorporado à base consolidada.

**Observação:** como não foi preservado um registro completo da execução final da interface, o documento evita atribuir retrospectivamente um campo específico à SpringerLink.

---

## Consolidação dos resultados

Foram incorporados à base consolidada 1.765 registros da Scopus, 1.000 da ACM Digital Library, 150 registros únicos do IEEE Xplore e um da SciELO, totalizando **2.916 registros**.

Posteriormente, 99 duplicatas entre fontes foram removidas, resultando em **2.817 registros únicos** submetidos à triagem da revisão.

Os dois registros recuperados na SBC OpenLib foram descartados antes da consolidação por não apresentarem aderência ao escopo, e nenhum registro utilizável da SpringerLink foi incorporado.
