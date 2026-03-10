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
- Versão utilizada: https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset (ou https://www.kaggle.com/datasets/cherngs/heart-disease-cleveland-uci)  
**Tipo:** Dados reais (anônimos) coletados em hospitais americanos  
**Tamanho:** 303 instâncias (pacientes) × 14 atributos (atende ao mínimo de 100 linhas)  
**Arquivo:** `data/
