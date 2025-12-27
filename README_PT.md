# CrisprIaDesign

Este repositório hospeda os scripts de aprendizado de máquina e notebooks interativos utilizados para gerar as designs das bibliotecas de CRISPRi e CRISPRa de próxima geração do laboratório Weissman, conforme detalhado em [Horlbeck et al., eLife 2016](https://elifesciences.org/content/5/e19760). Embora os sgRNAs pré-projetados para genes codificadores de proteínas humanas e de camundongos estejam disponíveis na publicação original, este conjunto de ferramentas foi projetado especificamente para criar bibliotecas personalizadas que visam loci novos, genes não codificadores ou organismos fora do escopo de humanos e camundongos.

O repositório oferece passos detalhados para aplicar os modelos quantitativos exatos usados nas bibliotecas CRISPRi-v2 e CRISPRa-v2, permitindo que pesquisadores predigam a atividade de sgRNAs e construam novas bibliotecas em escala genômica para suas necessidades de pesquisa específicas.

## 📋 Índice

- [Pré-requisitos](#pr-requisitos)
- [Instalação](#instalação)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Guia de Início Rápido](#guia-de-início-rápido)
- [Fluxo de Uso](#fluxo-de-uso)
- [Arquivos de Dados Necessários](#arquivos-de-dados-necessários)
- [Citação](#citação)

## Pré-requisitos

Antes de utilizar este conjunto de ferramentas, certifique-se de ter o seguinte instalado:

- **Python:** Versão 2.7
- **Jupyter Notebook:** Para executar os scripts interativos.
- **Ferramentas Externas:**
  - [ViennaRNA](https://www.tbi.univie.ac.at/RNA/)
  - [Bowtie](http://bowtie-bio.sourceforge.net/index.shtml) (Versão 1.x, não Bowtie2)

## Instalação

1. **Clone o repositório:**
   bash
   git clone https://github.com/your-username/CrisprIaDesign.git
   cd CrisprIaDesign
   

2. **Instale as dependências Python:**
   bash
   pip install biopython scipy numpy pandas scikit-learn pysam bxpython
   
   *Nota: Pode ser necessário instalar `bxpython` especificamente na versão 0.5.0.*

3. **Instale o ScreenProcessing:**
   Esta é uma dependência obrigatória do laboratório Weissman. Instale-a a partir do repositório oficial:
   bash
   git clone https://github.com/mhorlbeck/ScreenProcessing.git
   cd ScreenProcessing
   python setup.py install
   cd ..
   

## Estrutura do Projeto

O repositório contém dois notebooks principais que guiiam você pelo processo de design da biblioteca:

- **`Library_design_walkthrough.ipynb`**: O guia principal. Detalha como aplicar os modelos de aprendizado de máquina estabelecidos para designar sgRNAs para seus loci de interesse.
- **`CRISPRiaDesign_example_notebook.ipynb`**: Um exemplo extendido que demonstra aprendizado de máquina *de novo*, predição de atividade de sgRNA e construção de bibliotecas em escala genômica do zero.

## Guia de Início Rápido

Para replicar o processo exato de design de biblioteca usado para as bibliotecas CRISPRi-v2 e CRISPRa-v2:

1. Inicie o Jupyter Notebook:
   bash
   jupyter notebook
   
2. Abra o arquivo `Library_design_walkthrough.ipynb`.
3. Siga as instruções passo a passo dentro do notebook para carregar os dados, executar as predições e gerar sua biblioteca.

## Arquivos de Dados Necessários

Para executar os scripts, você precisará baixar vários arquivos genômicos grandes. Os arquivos específicos usados para as bibliotecas humanas estão linkados abaixo, mas você pode adaptar o processo para qualquer organismo/assembleia.

**Importante:** Os arquivos necessários para o `Library_design_walkthrough` estão disponibilizados de forma conveniente em um único arquivo [aqui](https://ucsf.box.com/s/s4ds471in2ngjer7okavzf5cqf2ebrqj).

1. **Sequência do Genoma:**
   - Fonte: UCSC Genome Browser
   - Formato: FASTA
   - Exemplo: [hg19](http://hgdownload.cse.ucsc.edu/goldenPath/hg19/bigZips/)

2. **Anotação TSS:**
   - Fonte: FANTOM5
   - Formato: BED
   - Exemplo: [TSS_human](http://fantom.gsc.riken.jp/5/datafiles/phase1.3/extra/TSS_classifier/)

3. **Dados de Cromatina:**
   - Fonte: Projeto ENCODE
   - Formato: BigWig
   - Exemplos:
     - [MNase-seq](https://www.encodeproject.org/files/ENCFF000VNN/)
     - [DNase-seq](https://www.encodeproject.org/files/ENCFF000SVL/)
     - [FAIRE-seq](https://www.encodeproject.org/files/ENCFF000TLU/)

4. **Anotação de Genes:**
   - Fonte: Ensembl (Versão 74 usada para as bibliotecas originais)
   - Formato: GTF

5. **Alias de Genes:**
   - Fonte: HGNC
   - Formato: Tabela

## Citação

Se você utilizar este código ou metodologia, por favor cite a publicação original:

> Horlbeck, M. A., et al. (2016). Compact and highly active next-generation libraries for CRISPR-mediated gene repression and activation. *eLife*, 5, e19760. [DOI: 10.7554/eLife.19760](https://doi.org/10.7554/eLife.19760)
