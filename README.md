# CardioIA - Fase 1: Batimentos de Dados

**Projeto Acadêmico – FIAP | Curso de Inteligência Artificial**  
**Fase 1 – Batimentos de Dados**  
**Aluno:** Lucas Yuji Nakayama Hirano / RM: 563420

**Objetivo:** Preparar bases de dados numéricos, textuais e visuais para alimentar os módulos inteligentes do CardioIA (plataforma de cardiologia moderna com IA, IoT, Visão Computacional e NLP).

Nesta fase, coletamos e organizamos dados cardiológicos fundamentais, seguindo princípios de **Governança de Dados** e atenção a **viés** (ex.: representatividade populacional, anonimato, qualidade e limitações éticas). Esses dados serão a base para fases futuras de modelagem, triagem, diagnóstico e monitoramento remoto.

## Estrutura do Repositório

- `data/` → Dataset numérico (CSV)
- `assets/` → Textos (.txt) e imagens (ou .zip das imagens)
- `README.md` → Esta documentação

## Parte 1 – Dados Numéricos (IoT / Dados Clínicos)

**Dataset escolhido:** Heart Disease UCI (Cleveland Database) – versão popular e limpa do Kaggle  
**Origem:**  
- Fonte principal: UCI Machine Learning Repository (1988) – https://archive.ics.uci.edu/dataset/45/heart+disease  
- Versão utilizada: https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset   
**Tipo:** Dados reais (anônimos) coletados em hospitais americanos  
**Arquivo:** `data/heart_disease_cleveland.csv`
  **Link público para download completo:**  
[https://drive.google.com/file/d/SEU_ID_AQUI/view?usp=sharing](https://drive.google.com/file/d/SEU_ID_AQUI/view?usp=sharing)  
*(Substitua pelo seu link real do Google Drive / OneDrive – marque como "Qualquer pessoa com o link")*

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

**Arquivo:** `assets/ecg_images.zip` (compactado para facilitar upload)

**Link público para download completo das imagens:**  
[https://drive.google.com/drive/folders/SEU_ID_FOLDER_AQUI?usp=sharing](https://drive.google.com/drive/folders/SEU_ID_FOLDER_AQUI?usp=sharing)  
*(Ou link direto do .zip – marque acesso público)*

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

