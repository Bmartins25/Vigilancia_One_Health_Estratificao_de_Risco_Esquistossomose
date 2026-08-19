
# Vigilância One Health e Estratificação de Risco da Esquistossomose

## Visão Geral

Este repositório contém o framework computacional para o desenvolvimento de uma **abordagem integrada One Health para vigilância e estratificação do risco de transmissão da esquistossomose em diferentes contextos africanos**.

O projeto integra **dados epidemiológicos, ambientais, moleculares, malacológicos, programáticos e geoespaciais**, buscando avaliar se a combinação dessas diferentes dimensões permite identificar comunidades e territórios com maior risco de transmissão da esquistossomose.

Todo o pipeline analítico é desenvolvido em **Python**, contemplando análise estatística, aprendizado de máquina, análise espacial, vigilância molecular por DNA ambiental (**eDNA**), avaliação das estratégias de Tratamento Massivo (**MDA**) e modelagem integrada de risco.

> **Pergunta de pesquisa:**
> É possível desenvolver uma abordagem integrada de vigilância One Health, baseada em dados epidemiológicos, ambientais, moleculares e espaciais, capaz de estratificar o risco de transmissão da esquistossomose em diferentes contextos africanos?

---

## Abordagem One Health

O projeto considera que a transmissão da esquistossomose resulta da interação entre diferentes componentes:

### Saúde humana

* Prevalência da infecção;
* idade e sexo;
* resultados diagnósticos;
* intensidade da infecção;
* comportamento de contato com água;
* histórico de tratamento antiparasitário;
* participação em campanhas de Tratamento Massivo.

### Ambiente

* Corpos hídricos;
* temperatura da água;
* pH;
* turbidez;
* condutividade;
* oxigênio dissolvido;
* precipitação;
* vegetação;
* uso do solo;
* condições de água e saneamento.

### Moluscos hospedeiros

* Espécies de moluscos;
* abundância e densidade;
* distribuição geográfica;
* presença ou ausência de infecção;
* resultados moleculares.

### Vigilância molecular

* DNA ambiental (eDNA);
* extração de DNA;
* concentração e qualidade do DNA;
* resultados de PCR/qPCR;
* valores de Ct/Cq;
* número de replicatas positivas;
* identificação molecular de *Schistosoma* spp.

### Território e programas de saúde

* Distribuição geográfica dos casos;
* escolas e comunidades;
* pontos de contato com água;
* densidade populacional;
* distância dos corpos hídricos;
* cobertura do Tratamento Massivo;
* mobilização comunitária;
* participação das escolas e profissionais de saúde.

A integração dessas dimensões permitirá estimar o **risco territorial de transmissão da esquistossomose**.

```text
EPIDEMIOLOGIA
      │
      ├─────────────┐
      │             │
AMBIENTE            │
      │             │
      ├─────────────┤
      │             │
DADOS MOLECULARES   │
      │             │
      ├─────────────┤
      │             │
MOLUSCOS            ├──► MODELO INTEGRADO ONE HEALTH
      │             │
      ├─────────────┤
      │             │
DADOS GEOESPACIAIS  │
      │             │
      ├─────────────┘
      │
TRATAMENTO MASSIVO
                    │
                    ▼
          RISCO DE TRANSMISSÃO
                    │
        ┌───────────┼───────────┐
        ▼           ▼           ▼
      BAIXO      MODERADO      ALTO
                                │
                                ▼
                           MUITO ALTO
```

---

## População do Estudo

A estrutura inicial considera aproximadamente:

**1.500 crianças**

Os dados serão organizados hierarquicamente:

```text
Criança
   ↓
Escola
   ↓
Comunidade
   ↓
Distrito
   ↓
País
```

Essa estrutura permite investigar simultaneamente fatores individuais e características contextuais ou territoriais.

---

## Dimensões dos Dados

### 1. Dados Epidemiológicos

Incluem:

* Número de crianças avaliadas;
* idade;
* sexo;
* escola/comunidade;
* resultado do exame para esquistossomose;
* método diagnóstico;
* intensidade da infecção;
* outras parasitoses intestinais;
* histórico de tratamento antiparasitário;
* participação anterior em campanhas de Tratamento Massivo;
* número de doses;
* período desde a última administração.

### 2. Exposição e Fatores de Risco

Incluem:

* Contato com rios, lagos, lagoas e canais;
* frequência de contato;
* finalidade do contato;
* distância entre residência/escola e corpos hídricos;
* acesso à água potável;
* condições de saneamento;
* disponibilidade e utilização de latrinas;
* práticas de higiene;
* atividades econômicas familiares relacionadas à água;
* conhecimento sobre esquistossomose;
* percepção de risco.

### 3. Estratégia de Tratamento Massivo

Inclui:

* População-alvo;
* calendário das campanhas;
* frequência de administração;
* medicamento utilizado;
* cobertura programática;
* número de crianças elegíveis;
* número efetivamente tratado;
* recusas e ausências;
* dificuldades de implementação;
* histórico das campanhas;
* mobilização comunitária;
* participação das escolas;
* participação dos profissionais de saúde;
* mecanismos de monitoramento.

Um dos indicadores utilizados poderá ser:

```text
Cobertura MDA = crianças tratadas / crianças elegíveis
```

### 4. Dados Ambientais

Para cada ponto de amostragem poderão ser analisados:

* Coordenadas geográficas;
* tipo de corpo hídrico;
* utilização pela população;
* frequência de utilização;
* sazonalidade;
* temperatura da água;
* pH;
* turbidez;
* condutividade;
* oxigênio dissolvido;
* vegetação;
* condições das margens;
* atividades humanas;
* proximidade das escolas e comunidades.

### 5. eDNA e Vigilância Molecular

A vigilância molecular poderá incluir:

* Ponto de coleta;
* data e hora;
* volume de água;
* condições ambientais;
* método de filtração;
* tipo de filtro;
* conservação;
* resultado da extração de DNA;
* concentração e qualidade;
* PCR/qPCR;
* Ct/Cq;
* replicatas positivas;
* espécie-alvo;
* controles positivos e negativos.

### 6. Moluscos Hospedeiros

Incluem:

* Espécie;
* local de captura;
* coordenadas;
* quantidade encontrada;
* período da coleta;
* características ambientais;
* presença ou ausência de infecção;
* método diagnóstico;
* resultados moleculares;
* densidade estimada.

### 7. Dados Geoespaciais

Incluem:

* Coordenadas das escolas;
* coordenadas das comunidades;
* localização dos corpos hídricos;
* localização dos casos;
* locais positivos para eDNA;
* distribuição dos moluscos;
* distância escola–água;
* distância residência–água;
* densidade populacional;
* cobertura vegetal;
* uso do solo;
* precipitação.

### 8. Dados Qualitativos e Programáticos

Poderão incluir:

* Percepção dos profissionais de saúde;
* percepção dos professores;
* percepção das comunidades;
* dificuldades na implementação do Tratamento Massivo;
* adesão;
* barreiras culturais e logísticas;
* conhecimento sobre esquistossomose;
* percepção dos corpos hídricos;
* estratégias locais de prevenção;
* acesso ao diagnóstico;
* acesso ao tratamento;
* articulação entre saúde e educação.

---

## Estratégia Analítica

O projeto considera três níveis principais de análise.

### Risco Individual

Estimativa da probabilidade de uma criança apresentar infecção:

```text
P(Esquistossomose | indivíduo + exposição + ambiente + contexto)
```

### Circulação Ambiental

Avaliação de evidências de circulação de *Schistosoma* a partir de:

```text
eDNA + moluscos infectados + características ambientais
```

### Risco Territorial de Transmissão

Integração das diferentes dimensões One Health:

```text
P(Alto risco de transmissão |
    epidemiologia +
    ambiente +
    eDNA +
    moluscos +
    geografia +
    Tratamento Massivo)
```

Os territórios poderão ser classificados em:

```text
BAIXO
MODERADO
ALTO
MUITO ALTO
```

---

## Análise Estatística

O pipeline contempla:

### Estatística Descritiva

* Média;
* desvio-padrão;
* mediana;
* intervalo interquartil;
* mínimo e máximo;
* coeficiente de variação;
* frequências;
* proporções.

### Estatística Inferencial

Dependendo da distribuição e natureza das variáveis:

* Teste de Mann–Whitney;
* teste Qui-quadrado;
* teste exato de Fisher;
* Odds Ratio;
* intervalo de confiança de 95%;
* Cohen's *d*.

### Modelagem Multivariada

A regressão logística poderá ser utilizada para estimar associações ajustadas:

```text
logit[P(Y=1)] =
β0 +
β1 Exposição +
β2 MDA +
β3 Saneamento +
β4 eDNA +
β5 Moluscos +
β6 Ambiente +
...
```

Os resultados poderão ser apresentados por meio de **Odds Ratios ajustados e respectivos intervalos de confiança de 95%**.

---

## Análise Multinível

Como as crianças estão agrupadas em escolas, comunidades, distritos e países, serão considerados métodos capazes de incorporar essa estrutura hierárquica.

```text
Crianças
   ⊂
Escolas
   ⊂
Comunidades
   ⊂
Distritos
   ⊂
Países
```

Essa abordagem permitirá distinguir fatores individuais de efeitos contextuais e territoriais.

---

## Machine Learning

O pipeline inicial contempla:

* Regressão Logística;
* Random Forest;
* Gradient Boosting.

Outros algoritmos poderão ser incorporados durante o desenvolvimento.

### Métricas de Avaliação

Os modelos poderão ser comparados utilizando:

* ROC-AUC;
* PR-AUC;
* acurácia;
* sensibilidade;
* especificidade;
* valor preditivo positivo;
* valor preditivo negativo;
* F1-score;
* Brier Score;
* matriz de confusão;
* curva de calibração.

---

## Comparação Incremental One Health

Um dos principais objetivos analíticos será avaliar se a integração das diferentes dimensões aumenta a capacidade de estratificação do risco.

Serão comparados modelos progressivos:

```text
M1 = Epidemiologia

M2 = Epidemiologia
     + Ambiente

M3 = Epidemiologia
     + Ambiente
     + Moluscos

M4 = Epidemiologia
     + Ambiente
     + Moluscos
     + eDNA

M5 = Modelo One Health completo
     + Dados geoespaciais
     + Tratamento Massivo
     + Variáveis programáticas
```

Essa estratégia permitirá avaliar o **ganho incremental de desempenho** proporcionado pela integração One Health.

---

## Validação Geográfica

Para avaliar a capacidade de generalização do modelo entre diferentes contextos africanos, poderá ser utilizada uma estratégia de validação geográfica do tipo **Leave-One-Country-Out**.

Exemplo:

```text
TREINAMENTO

País A
País B
País C
País D

      ↓

VALIDAÇÃO EXTERNA

País E
```

O processo poderá ser repetido utilizando cada país como cenário de validação.

Essa estratégia permite investigar se os padrões identificados pelo modelo permanecem válidos em territórios diferentes daqueles utilizados em seu desenvolvimento.

---

## Índice Integrado de Risco One Health

O projeto também prevê a investigação de um índice integrado:

```text
Risco epidemiológico
        +
Exposição à água
        +
Condições ambientais
        +
Evidência molecular
        +
Moluscos hospedeiros
        +
Vulnerabilidade territorial
        +
Desempenho do MDA
        ↓
ÍNDICE INTEGRADO DE RISCO ONE HEALTH
```

O índice poderá apoiar a identificação e priorização de áreas para vigilância e intervenção.

---

## Estrutura do Repositório

```text
one-health-schistosomiasis/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── synthetic/
│   └── processed/
│
├── src/
│   ├── 00_generate_synthetic_data.py
│   ├── 01_descriptive_statistics.py
│   ├── 02_inferential_analysis.py
│   ├── 03_logistic_regression.py
│   ├── 04_multilevel_model.py
│   ├── 05_machine_learning.py
│   ├── 06_calibration_metrics.py
│   ├── 07_edna_analysis.py
│   ├── 08_mda_analysis.py
│   ├── 09_spatial_analysis.py
│   ├── 10_integrated_one_health_model.py
│   ├── 11_geographic_validation.py
│   └── 12_one_health_risk_index.py
│
├── notebooks/
│   └── exploratory_analysis.ipynb
│
├── outputs/
│   ├── figures/
│   ├── tables/
│   └── maps/
│
└── docs/
    ├── methodology.md
    └── data_dictionary.md
```

---

## Ambiente Python

O pipeline analítico é desenvolvido integralmente em **Python**.

Principais bibliotecas:

```text
pandas
numpy
scipy
statsmodels
scikit-learn
matplotlib
geopandas
shapely
folium
libpysal
esda
```

As dependências poderão ser instaladas utilizando:

```bash
pip install -r requirements.txt
```

---

## Governança e Segurança dos Dados

**Dados individuais reais de saúde não devem ser armazenados neste repositório.**

O GitHub deverá ser utilizado principalmente para:

* Código-fonte;
* documentação;
* dicionários de dados;
* bases sintéticas;
* fluxos analíticos reproduzíveis;
* resultados agregados que não permitam identificação individual.

Dados epidemiológicos reais deverão ser armazenados e processados em ambiente apropriado, observando aprovações éticas, acordos de compartilhamento, requisitos institucionais e normas aplicáveis de proteção de dados.

---

## Estágio Atual

A versão atual representa uma **prova de conceito metodológica**.

Inicialmente, dados sintéticos serão utilizados para:

1. Testar a arquitetura dos dados;
2. validar o pipeline analítico;
3. desenvolver os modelos estatísticos;
4. testar os algoritmos de Machine Learning;
5. avaliar estratégias de estratificação de risco;
6. preparar o framework para posterior aplicação e validação com dados reais.

Resultados provenientes de dados sintéticos **não devem ser interpretados como evidências epidemiológicas ou clínicas reais**.

---

## Contribuição Esperada

O projeto busca desenvolver uma estrutura computacional reproduzível capaz de integrar dados heterogêneos dentro de uma perspectiva One Health para apoiar:

* Vigilância da esquistossomose;
* identificação de hotspots de transmissão;
* estratificação territorial de risco;
* avaliação das estratégias de Tratamento Massivo;
* vigilância ambiental;
* vigilância molecular;
* identificação de áreas prioritárias;
* apoio à tomada de decisão em saúde pública.

---

## Aviso

Este repositório possui finalidade **científica e de desenvolvimento metodológico**.

Os modelos e dados sintéticos disponibilizados não constituem ferramentas diagnósticas clinicamente validadas e não devem ser utilizados isoladamente para diagnóstico ou decisão terapêutica individual.

---

## Licença

A licença do projeto será definida de acordo com os requisitos institucionais, de propriedade intelectual, colaboração científica e governança de dados envolvidos no estudo.
