

Projeto Acadêmico – FIAP | Curso de Inteligência Artificial

Aluno: Lucas Yuji Nakayama Hirano
RM: 563420


# CardioIA – Fase 1

Projeto acadêmico de análise de dados cardíacos utilizando técnicas de
Ciência de Dados e Inteligência Artificial.

O objetivo é explorar o dataset Cleveland Heart Disease e imagens de
eletrocardiograma (ECG) para identificar padrões relacionados a
doenças cardíacas.


## Tecnologias utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook


Fase 1 – Batimentos de Dados, o objetivo foi coletar, organizar e documentar três tipos de dados fundamentais que servirão como base para os módulos inteligentes do sistema:
 Dados numéricos clínicos (IoT / dados médicos)

 Dados textuais (NLP)

 Dados visuais de exames cardiológicos (Visão Computacional)

Durante essa etapa também foram considerados princípios de Governança de Dados, incluindo:

anonimização dos dados

identificação de possíveis vieses

qualidade e confiabilidade das fontes

impacto ético do uso de dados em saúde

Esses dados serão utilizados nas próximas fases para treinamento de modelos de IA, análises preditivas e sistemas de suporte à decisão clínica.


## Estrutura do Projeto

cardioIA-fase1
│
├── data/
│   └── heart_disease_cleveland.csv
│
├── assets/
│   └── ecg_images.zip
│
├── notebook.ipynb
└── README.md

Descrição das pastas:

data  dataset numérico em formato CSV

assets  textos médicos e imagens de ECG

README.md  documentação do projeto



## Parte 1 – Dados Numéricos (IoT / Dados Clínicos)

**Dataset escolhido:** Heart Disease UCI (Cleveland Database) – versão popular e limpa do Kaggle  
**Origem:**  
- Fonte principal: UCI Machine Learning Repository (1988) – https://archive.ics.uci.edu/dataset/45/heart+disease  
- Versão utilizada: https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset   
**Tipo:** Dados reais (anônimos) coletados em hospitais americanos  
**Arquivo:** `data/heart_disease_cleveland.csv`
  **Link público para download completo:**  
https://drive.google.com/file/d/12hp4y465-fFobPqWXDLtwL9Qa276EpxA/view

**Variáveis mais relevantes (do ponto de vista clínico e para IA):**
- **age** (idade): Fator de risco clássico – risco de DCV aumenta significativamente após 45–50 anos.
- **sex** (sexo): Homens apresentam maior prevalência em idades mais jovens.
- **trestbps** (pressão arterial em repouso): Hipertensão é um dos principais fatores modificáveis de risco cardiovascular.
- **chol** (colesterol sérico): Níveis elevados contribuem para aterosclerose e eventos coronarianos.
- **thalach** (frequência cardíaca máxima): Indicador de capacidade funcional e reserva cardíaca.
- **oldpeak** (depressão do ST induzida por exercício): Forte preditor de isquemia miocárdica.
- **num/target** (presença de doença): Variável alvo para modelos preditivos.

**Relevância para IA em saúde:**  
Essas variáveis permitem treinar modelos de classificação (ex.: Random Forest, XGBoost, Redes Neurais) para prever risco de doença cardíaca, auxiliar triagem e suporte à decisão clínica. São validadas em guidelines internacionais (ACC/AHA, ESC).

**Governança e Viés:**  
- Dados anônimos e de domínio público (CC BY 4.0).  
- Viés identificado: População majoritariamente americana (branca), década de 1980 → possível under-representation de etnias brasileiras, mulheres e populações atuais (ex.: aumento de obesidade/diabetes). Recomenda-se augmentar com dados brasileiros (DATASUS, cohorts locais) em fases futuras.

## Parte 2 – Dados Textuais (NLP)

**Textos coletados:** Dois artigos científicos em português (contexto brasileiro/SUS)  
**Fontes:** SciELO / BVS (acesso aberto)

1. **texto1.txt** → "Fatores associados às doenças cardiovasculares na população adulta brasileira: Pesquisa Nacional de Saúde, 2019"  
   Origem: https://www.scielosp.org/article/rbepid/2021.v24suppl2/e210013/pt/

2. **texto2.txt** → "Epidemiologia das doenças cardiovasculares em países de Língua Portuguesa"  
   Origem: https://www.scielo.br/j/abc/a/zf43nPqcSNchkvsrrzzs8Vb?lang=pt

**Pasta:** `assets/`

**Como explorar com NLP:**
- Extração de entidades nomeadas (sintomas: dor torácica, dispneia, palpitações; fatores de risco: hipertensão, tabagismo).
- Análise de sentimentos e classificação de tópicos (prevenção vs. tratamento vs. epidemiologia).
- Sumarização automática de literatura científica.
- Mineração de sintomas em relatos de pacientes (futuro chatbot de triagem).

**Relevância para IA na saúde:**  
NLP pode processar prontuários eletrônicos, literatura médica e relatos de pacientes para extrair conhecimento acionável, melhorar triagem remota e gerar resumos para médicos. Textos em português refletem melhor a realidade brasileira (ex.: alta prevalência de HAS no SUS).

## Parte 3 – Dados Visuais (Visão Computacional)

**Tipo de imagens:** Imagens de Eletrocardiogramas (ECGs)  
**Quantidade:** 120 imagens selecionadas (mínimo 100)  
**Origem:** Dataset público no Kaggle – "ECG Images Dataset of Cardiac Patients"  
Link original: https://www.kaggle.com/datasets/evilspirit05/ecg-analysis (ou similar: https://www.kaggle.com/datasets/erhmrai/ecg-image-data)

Arquivo: assets/ecg_images.zip (compactado para facilitar upload)

Link público para download completo das imagens:
https://drive.google.com/file/d/16kwOGAmC1nWkSERaDDC4ibowweKVLTeI/view?usp=sharing

**Análises possíveis com Visão Computacional:**
- Detecção e classificação de arritmias (ex.: normal vs. fibrilação atrial, bloqueios).
- Segmentação de ondas (P, QRS, T) e medição automática de intervalos.
- Identificação de anomalias (elevação ST, inversão de T, ondas Q patológicas).
- Uso de CNNs (ex.: ResNet, EfficientNet) para diagnóstico assistido.

**Importância para projetos de IA em cardiologia:**  
IA em ECG permite laudos rápidos em emergências, monitoramento contínuo via wearables/IoT e triagem em áreas remotas. Reduz tempo de espera e erros humanos.

**Governança e Viés:**  
- Imagens anônimas e públicas.  
- Viés: Dependendo do dataset, pode ser de uma região específica (ex.: Ásia em alguns casos) → validar com ECGs brasileiros no futuro.

## Considerações Finais – Governança de Dados e Ética

- Todos os dados são de fontes públicas e anônimas.  
- Atenção a viés populacional, temporal e geográfico.  
- Próximas fases: limpeza adicional, balanceamento, augmentação e integração com modelos de IA.  
- Impacto esperado: Contribuir para cardiologia inteligente, acessível e preventiva no Brasil.

