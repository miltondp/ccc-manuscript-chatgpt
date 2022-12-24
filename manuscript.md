---
title: An efficient not-only-linear correlation coefficient based on machine learning
keywords:
- correlation coefficient
- nonlinear relationships
- gene expression
lang: en-US
date-meta: '2022-12-24'
author-meta:
- Milton Pividori
- Marylyn D. Ritchie
- Diego H. Milone
- Casey S. Greene
header-includes: |
  <!--
  Manubot generated metadata rendered from header-includes-template.html.
  Suggest improvements at https://github.com/manubot/manubot/blob/main/manubot/process/header-includes-template.html
  -->
  <meta name="dc.format" content="text/html" />
  <meta property="og:type" content="article" />
  <meta name="dc.title" content="An efficient not-only-linear correlation coefficient based on machine learning" />
  <meta name="citation_title" content="An efficient not-only-linear correlation coefficient based on machine learning" />
  <meta property="og:title" content="An efficient not-only-linear correlation coefficient based on machine learning" />
  <meta property="twitter:title" content="An efficient not-only-linear correlation coefficient based on machine learning" />
  <meta name="dc.date" content="2022-12-24" />
  <meta name="citation_publication_date" content="2022-12-24" />
  <meta property="article:published_time" content="2022-12-24" />
  <meta name="dc.modified" content="2022-12-24T05:23:54+00:00" />
  <meta property="article:modified_time" content="2022-12-24T05:23:54+00:00" />
  <meta name="dc.language" content="en-US" />
  <meta name="citation_language" content="en-US" />
  <meta name="dc.relation.ispartof" content="Manubot" />
  <meta name="dc.publisher" content="Manubot" />
  <meta name="citation_journal_title" content="Manubot" />
  <meta name="citation_technical_report_institution" content="Manubot" />
  <meta name="citation_author" content="Milton Pividori" />
  <meta name="citation_author_institution" content="Department of Genetics, Perelman School of Medicine, University of Pennsylvania, Philadelphia, PA 19104, USA" />
  <meta name="citation_author_orcid" content="0000-0002-3035-4403" />
  <meta name="twitter:creator" content="@miltondp" />
  <meta name="citation_author" content="Marylyn D. Ritchie" />
  <meta name="citation_author_institution" content="Department of Genetics, Perelman School of Medicine, University of Pennsylvania, Philadelphia, PA 19104, USA" />
  <meta name="citation_author_orcid" content="0000-0002-1208-1720" />
  <meta name="twitter:creator" content="@MarylynRitchie" />
  <meta name="citation_author" content="Diego H. Milone" />
  <meta name="citation_author_institution" content="Research Institute for Signals, Systems and Computational Intelligence (sinc(i)), Universidad Nacional del Litoral, Consejo Nacional de Investigaciones Científicas y Técnicas (CONICET), Santa Fe CP3000, Argentina" />
  <meta name="citation_author_orcid" content="0000-0003-2182-4351" />
  <meta name="twitter:creator" content="@d1001" />
  <meta name="citation_author" content="Casey S. Greene" />
  <meta name="citation_author_institution" content="Center for Health AI, University of Colorado School of Medicine, Aurora, CO 80045, USA" />
  <meta name="citation_author_institution" content="Department of Biochemistry and Molecular Genetics, University of Colorado School of Medicine, Aurora, CO 80045, USA" />
  <meta name="citation_author_orcid" content="0000-0001-8713-9213" />
  <meta name="twitter:creator" content="@GreeneScientist" />
  <link rel="canonical" href="https://miltondp.github.io/ccc-manuscript-chatgpt/" />
  <meta property="og:url" content="https://miltondp.github.io/ccc-manuscript-chatgpt/" />
  <meta property="twitter:url" content="https://miltondp.github.io/ccc-manuscript-chatgpt/" />
  <meta name="citation_fulltext_html_url" content="https://miltondp.github.io/ccc-manuscript-chatgpt/" />
  <meta name="citation_pdf_url" content="https://miltondp.github.io/ccc-manuscript-chatgpt/manuscript.pdf" />
  <link rel="alternate" type="application/pdf" href="https://miltondp.github.io/ccc-manuscript-chatgpt/manuscript.pdf" />
  <link rel="alternate" type="text/html" href="https://miltondp.github.io/ccc-manuscript-chatgpt/v/1eb293701d09f76996b52c9e633604db9df6d307/" />
  <meta name="manubot_html_url_versioned" content="https://miltondp.github.io/ccc-manuscript-chatgpt/v/1eb293701d09f76996b52c9e633604db9df6d307/" />
  <meta name="manubot_pdf_url_versioned" content="https://miltondp.github.io/ccc-manuscript-chatgpt/v/1eb293701d09f76996b52c9e633604db9df6d307/manuscript.pdf" />
  <meta property="og:type" content="article" />
  <meta property="twitter:card" content="summary_large_image" />
  <link rel="icon" type="image/png" sizes="192x192" href="https://manubot.org/favicon-192x192.png" />
  <link rel="mask-icon" href="https://manubot.org/safari-pinned-tab.svg" color="#ad1457" />
  <meta name="theme-color" content="#ad1457" />
  <!-- end Manubot generated metadata -->
bibliography:
- content/manual-references.json
manubot-output-bibliography: output/references.json
manubot-output-citekeys: output/citations.tsv
manubot-requests-cache-path: ci/cache/requests-cache
manubot-clear-requests-cache: false
...





_This is a testing version edited by an AI bot._


<small><em>
This manuscript
([permalink](https://miltondp.github.io/ccc-manuscript-chatgpt/v/1eb293701d09f76996b52c9e633604db9df6d307/))
was automatically generated
from [miltondp/ccc-manuscript-chatgpt@1eb2937](https://github.com/miltondp/ccc-manuscript-chatgpt/tree/1eb293701d09f76996b52c9e633604db9df6d307)
on December 24, 2022.
</em></small>



## Authors



+ **Milton Pividori**
  <br>
    ![ORCID icon](images/orcid.svg){.inline_icon width=16 height=16}
    [0000-0002-3035-4403](https://orcid.org/0000-0002-3035-4403)
    · ![GitHub icon](images/github.svg){.inline_icon width=16 height=16}
    [miltondp](https://github.com/miltondp)
    · ![Twitter icon](images/twitter.svg){.inline_icon width=16 height=16}
    [miltondp](https://twitter.com/miltondp)
    <br>
  <small>
     Department of Genetics, Perelman School of Medicine, University of Pennsylvania, Philadelphia, PA 19104, USA
     · Funded by The Gordon and Betty Moore Foundation GBMF 4552; The National Human Genome Research Institute (R01 HG010067)
  </small>

+ **Marylyn D. Ritchie**
  <br>
    ![ORCID icon](images/orcid.svg){.inline_icon width=16 height=16}
    [0000-0002-1208-1720](https://orcid.org/0000-0002-1208-1720)
    · ![Twitter icon](images/twitter.svg){.inline_icon width=16 height=16}
    [MarylynRitchie](https://twitter.com/MarylynRitchie)
    <br>
  <small>
     Department of Genetics, Perelman School of Medicine, University of Pennsylvania, Philadelphia, PA 19104, USA
  </small>

+ **Diego H. Milone**
  <br>
    ![ORCID icon](images/orcid.svg){.inline_icon width=16 height=16}
    [0000-0003-2182-4351](https://orcid.org/0000-0003-2182-4351)
    · ![GitHub icon](images/github.svg){.inline_icon width=16 height=16}
    [dmilone](https://github.com/dmilone)
    · ![Twitter icon](images/twitter.svg){.inline_icon width=16 height=16}
    [d1001](https://twitter.com/d1001)
    <br>
  <small>
     Research Institute for Signals, Systems and Computational Intelligence (sinc(i)), Universidad Nacional del Litoral, Consejo Nacional de Investigaciones Científicas y Técnicas (CONICET), Santa Fe CP3000, Argentina
  </small>

+ **Casey S. Greene**
  <br>
    ![ORCID icon](images/orcid.svg){.inline_icon width=16 height=16}
    [0000-0001-8713-9213](https://orcid.org/0000-0001-8713-9213)
    · ![GitHub icon](images/github.svg){.inline_icon width=16 height=16}
    [cgreene](https://github.com/cgreene)
    · ![Twitter icon](images/twitter.svg){.inline_icon width=16 height=16}
    [GreeneScientist](https://twitter.com/GreeneScientist)
    <br>
  <small>
     Center for Health AI, University of Colorado School of Medicine, Aurora, CO 80045, USA; Department of Biochemistry and Molecular Genetics, University of Colorado School of Medicine, Aurora, CO 80045, USA
     · Funded by The Gordon and Betty Moore Foundation (GBMF 4552); The National Human Genome Research Institute (R01 HG010067); The National Cancer Institute (R01 CA237170)
  </small>


::: {#correspondence}
✉ — Correspondence possible via [GitHub Issues](https://github.com/miltondp/ccc-manuscript-chatgpt/issues)

:::


## Abstract {.page_break_before}

We introduce the Clustermatch Correlation Coefficient (CCC), a next-generation not-only-linear correlation coefficient that can efficiently detect linear and nonlinear patterns in data.
CCC is based on machine learning models and is much faster than state-of-the-art coefficients such as the Maximal Information Coefficient.
When applied to human gene expression data, CCC reveals biologically meaningful linear and nonlinear patterns missed by standard, linear-only correlation coefficients.
These patterns include nonlinear associations associated with sex differences that are not detected by linear-only methods.
Moreover, gene pairs highly ranked by CCC were enriched for interactions in integrated networks, suggesting that CCC can detect functional relationships that linear-only methods miss.
CCC is an easy-to-use and highly-efficient tool that can be applied to genome-scale data and other domains across different data types.


## Introduction

The availability of large datasets has enabled researchers to explore complex scientific questions.
To identify patterns in these datasets, correlation analysis is an essential statistical technique.
Correlation coefficients are widely used to measure the similarity between two objects, such as genes [@pmid:27479844] or lifestyle factors [@doi:10.1073/pnas.1217269109], and to select features that improve prediction accuracy [@pmid:27006077; @pmid:33729976].
The Pearson correlation coefficient is widely applied across various application domains and scientific areas.
Therefore, even minor improvements to this technique could have a major impact on research and industry.


Analysis of gene expression in transcriptomics often starts with estimating correlations between genes.
Sophisticated correlation analysis can suggest gene function [@pmid:21241896], identify common and cell-type specific regulatory networks [@pmid:25915600], and uncover important interactions in living organisms [@pmid:21606319; @pmid:16968540].
RNA-seq datasets [@pmid:32913098; @pmid:34844637] are also used to detect complex transcriptional mechanisms underlying human diseases [@pmid:27479844; @pmid:31121115; @pmid:30668570; @pmid:32424349; @pmid:34475573].
The introduction of the omnigenic model of complex traits [@pmid:28622505; @pmid:31051098] has led to increased focus on gene-gene relationships in the study of human diseases [@pmid:34845454; @doi:10.1101/2021.07.05.450786; @doi:10.1101/2021.10.21.21265342; @doi:10.1038/s41588-021-00913-z], including in the field of polygenic risk scores [@doi:10.1016/j.ajhg.2021.07.003].
Combining disease-associated genes from genome-wide association studies (GWAS) with gene co-expression networks to prioritize "core" genes directly affecting diseases [@doi:10.1186/s13040-020-00216-9; @doi:10.1101/2021.07.05.450786; @doi:10.1101/2021.10.21.21265342] is a recent approach that can capture core genes not identified by standard statistical methods.
These genes are believed to be part of highly interconnected, disease-relevant regulatory networks.
Advanced correlation coefficients could therefore have wide applications in biology, including in the precision medicine field for the prioritization of candidate drug targets.


Pearson and Spearman correlation coefficients are widely used to identify intuitive linear or monotonic relationships, but they may fail to capture complex yet critical nonlinear patterns.
To address this issue, several novel coefficients have been proposed, such as the Maximal Information Coefficient (MIC) [@pmid:22174245] and the Distance Correlation (DC) [@doi:10.1214/009053607000000505], which have been successfully applied in various domains [@pmid:33972855; @pmid:33001806; @pmid:27006077].
However, their computational complexity makes them impractical for even moderately sized datasets [@pmid:33972855; @pmid:27333001].
We previously developed a clustering method that outperformed Pearson, Spearman, DC and MIC in detecting clusters of simulated linear and nonlinear relationships with varying noise levels [@doi:10.1093/bioinformatics/bty899].
Here, we introduce the Clustermatch Correlation Coefficient (CCC), an efficient not-only-linear coefficient that works across quantitative and qualitative variables.
CCC has a single parameter that limits the maximum complexity of relationships found (from linear to more general patterns) and computation time.
It also provides a high level of flexibility to detect specific types of patterns, while providing safe defaults to capture general relationships.
Moreover, its efficient implementation is highly parallelizable, allowing to speed up computation across variable pairs with millions of objects or conditions.
To assess its performance, we applied CCC to gene expression data from the Genotype-Tissue Expression v8 (GTEx) project across different tissues [@doi:10.1126/science.aaz1776].
Our results showed that CCC captured both strong linear relationships and novel nonlinear patterns, which were entirely missed by standard coefficients.
Additionally, CCC behaved similarly to MIC in several cases, although it was much faster to compute.
Moreover, gene pairs detected in expression data by CCC had higher interaction probabilities in tissue-specific gene networks from the Genome-wide Analysis of gene Networks in Tissues (GIANT) [@doi:10.1038/ng.3259].
Finally, its ability to efficiently handle diverse data types (including numerical and categorical features) reduces preprocessing steps and makes it appealing to analyze large and heterogeneous repositories.


## Results


### A robust and efficient not-only-linear dependence coefficient

![
**Different types of relationships in data.**
Each panel contains a set of simulated data points described by two generic variables: $x$ and $y$.
The first row shows Anscombe's quartet with four different datasets (from Anscombe I to IV) and 11 data points each.
The second row contains a set of general patterns with 100 data points each.
Each panel shows the correlation value using Pearson ($p$), Spearman ($s$) and CCC ($c$).
Vertical and horizontal red lines show how CCC clustered data points using $x$ and $y$.
](images/intro/relationships.svg "Different types of relationships in data"){#fig:datasets_rel width="100%"}

Figure \ref{fig:ccc_example} shows an example of the CCC calculation.

The CCC provides a similarity measure between any pair of variables, either with numerical or categorical values.
The method assumes that if there is a relationship between two variables, then the clustering of data points using each variable should match.
For numerical values, CCC uses quantiles to separate data points into different clusters (e.g., the median separates numerical data into two clusters).
The CCC is then defined as the maximum adjusted Rand index (ARI) [@doi:10.1007/BF01908075] between the clusterings, ranging from 0 to 1.
Further details of the CCC algorithm can be found in the [Methods](#sec:ccc_algo) section.
An example of the CCC calculation is shown in Figure \ref{fig:ccc_example}.


We examined the behavior of Pearson ($p$), Spearman ($s$) and CCC ($c$) correlation coefficients on different simulated data patterns.
Figure @fig:datasets_rel shows the classic Anscombe's quartet [@doi:10.1080/00031305.1973.10478966], which comprises four synthetic datasets with different patterns but the same data statistics (mean, standard deviation and Pearson's correlation).
This kind of simulated data, recently revisited with the "Datasaurus" [@url:http://www.thefunctionalart.com/2016/08/download-datasaurus-never-trust-summary.html; @doi:10.1145/3025453.3025912; @doi:10.1111/dsji.12233], is to remind us of the importance of going beyond simple statistics.
Unwanted patterns (such as outliers) and desirable ones (such as biologically meaningful nonlinear relationships) can be masked by summary statistics alone.


In contrast, CCC is more robust to nonlinear relationships and outliers, as illustrated in Figure \ref{fig:anscombe}.

The Anscombe datasets show that CCC is more robust than Pearson and Spearman when detecting nonlinear relationships and outliers.
In Anscombe I, CCC separates data points using two clusters, yielding a strong relationship of 1.0.
In Anscombe II, which follows a partially quadratic relationship, CCC yields a lower yet non-zero value of 0.34, reflecting a more complex relationship than a linear pattern.
In Anscombe IV, where $x$ values are almost constant except for one outlier, CCC correctly indicates no association for this variable pair with a value of $c=0.00$.
This is in contrast to Pearson's and Spearman's correlation coefficients, which are the same across all these Anscombe's examples ($p=0.82$ and $s=0.50$ or greater, respectively).
This is illustrated in Figure \ref{fig:anscombe}.


We simulated different types of relationships (see Figure @fig:datasets_rel, second row), including some previously described from gene expression data [@doi:10.1126/science.1205438; @doi:10.3389/fgene.2019.01410; @doi:10.1091/mbc.9.12.3273].
For the random/independent pair of variables, all coefficients correctly agreed with a value close to zero.
The non-coexistence pattern, captured by all coefficients, indicated a case where one gene ($x$) was expressed while the other one ($y$) was inhibited, highlighting a potentially strong biological relationship (such as a microRNA negatively regulating another gene).
However, for the other two examples (quadratic and two-lines), Pearson and Spearman did not capture the nonlinear pattern between variables $x$ and $y$.
CCC, on the other hand, used different degrees of complexity to capture the relationships.
For instance, in the quadratic pattern, CCC separated $x$ into four clusters to reach the maximum ARI.
The two-lines example showed two embedded linear relationships with different slopes, which neither Pearson nor Spearman detected ($p=-0.12$ and $s=0.05$, respectively).
Here, CCC increased the complexity of the model by using eight clusters for $x$ and six for $y$, resulting in $c=0.31$.


### The CCC reveals linear and nonlinear patterns in human transcriptomic data

As shown in Fig.
1, CCC outperformed Pearson and Spearman in capturing nonlinear relationships between genes in whole blood.

We then examined the correlation coefficients in gene expression data from GTEx v8 across different tissues.
We chose the top 5,000 genes with the highest variance for our initial analyses in whole blood.
We computed the correlation matrix between genes using Pearson, Spearman and CCC (see [Methods](#sec:data_gtex)).
As Fig.
1 shows, CCC was better than Pearson and Spearman at capturing nonlinear relationships between genes in whole blood.


We examined the distribution of each coefficient's absolute values in GTEx (Figure @fig:dist_coefs).
CCC (mean=0.14, median=0.08, sd=0.15) had a much more skewed distribution than Pearson (mean=0.31, median=0.24, sd=0.24) and Spearman (mean=0.39, median=0.37, sd=0.26).
The coefficients reached a cumulative set containing 70% of gene pairs at different values (Figure @fig:dist_coefs b), with CCC at 0.18, Pearson at 0.44, and Spearman at 0.56.
This suggests that, for this type of data, the coefficients are not directly comparable by magnitude, so we used ranks for further comparisons.
In GTEx v8, CCC values were closer to Spearman and vice versa than either was to Pearson (Figure @fig:dist_coefs c).
We also compared the Maximal Information Coefficient (MIC) in this data (see [Supplementary Note 1](#sec:mic)).
We found that CCC behaved similarly to MIC, although CCC was up to two orders of magnitude faster to run (see [Supplementary Note 2](#sec:time_test)).
MIC, an advanced correlation coefficient able to capture general patterns beyond linear relationships, has been successfully used in various application domains [@pmid:33972855; @pmid:33001806; @pmid:27006077].
These results suggest that our findings for CCC generalize to MIC.
Therefore, in the subsequent analyses, we focused on CCC and linear-only coefficients.


![
**Distribution of coefficient values on gene expression (GTEx v8, whole blood).**
**a)** Histogram of coefficient values.
**b)** Corresponding cumulative histogram. The dotted line maps the coefficient value that accumulates 70% of gene pairs.
**c)** 2D histogram plot with hexagonal bins between all coefficients, where a logarithmic scale was used to color each hexagon.
](images/coefs_comp/gtex_whole_blood/dist-main.svg "Distribution of coefficient values"){#fig:dist_coefs width="100%"}


We found that the correlation coefficients identified different patterns in gene expression data.
To analyze their agreement and disagreement, we obtained the top 30% of gene pairs with the largest correlation values ("high" set) and the bottom 30% ("low" set), resulting in six potentially overlapping categories.
Most of the time (76.4%), the three coefficients agreed on whether there is a strong correlation (42.1%) or no relationship (34.3%).
This suggests that these concordant gene pairs most likely represent linear patterns, since Pearson and Spearman are linear-only and CCC can also capture these patterns.
Moreover, CCC and Spearman tended to agree more on either highly or poorly correlated pairs (4.0% in the "high" set, and 7.0% in the "low" set) than either of them with Pearson (all between 0.3%-3.5% for the "high" set, and 2.8%-5.5% for the "low" set).
In summary, CCC agreed with either Pearson or Spearman in 90.5% of gene pairs by assigning a high or a low correlation value (Figure @fig:upsetplot_coefs a).

![
**Intersection of gene pairs with high and low correlation coefficient values (GTEx v8, whole blood).**
**a)** UpSet plot with six categories (rows) grouping the 30% of the highest (green triangle) and lowest (red triangle) values for each coefficient.
Columns show different intersections of categories grouped by agreements and disagreements.
**b)** Hexagonal binning plots with examples of gene pairs where CCC ($c$) disagrees with Pearson ($p$) and Spearman ($s$).
For each method, colors in the triangles indicate if the gene pair is among the top (green) or bottom (red) 30% of coefficient values.
No triangle means that the correlation value for the gene pair is between the 30th and 70th percentiles (neither low nor high).
A logarithmic scale was used to color each hexagon.
](images/coefs_comp/gtex_whole_blood/upsetplot-main.svg "Intersection of gene pairs"){#fig:upsetplot_coefs width="100%"}


We found that more than 20,000 gene pairs had a high CCC value but were not highly ranked by other correlation coefficients (Figure @fig:upsetplot_coefs a, right).
Additionally, 1,075 gene pairs had a high Pearson value but low CCC, 87 gene pairs had a high Spearman value but low CCC, and 531 gene pairs had both low CCC and low Spearman values.
However, our analysis suggests that many of these cases may be caused by potential outliers (Figure @fig:upsetplot_coefs b, and discussed in detail later).
We further examined the gene pairs that were in the top five of each intersection in the "Disagreements" group (Figure @fig:upsetplot_coefs a, right), where CCC disagreed with Pearson, Spearman, or both.

![
**The expression levels of *KDM6A* and *UTY* display sex-specific associations across GTEx tissues.**
CCC captures this nonlinear relationship in all GTEx tissues (nine examples are shown in the first three rows), except in female-specific organs (last row).
](images/coefs_comp/kdm6a_vs_uty/gtex-KDM6A_vs_UTY-main.svg "KDM6A and UTY across different GTEx tissues"){#fig:gtex_tissues:kdm6a_uty width="95%"}

The first three gene pairs (*IFNG* - *SDS*, *JUN* - *APOC1*, and *ZDHHC12* - *CCL18*) show a non-coexistence relationship.
Samples with high expression of one gene tend to have low expression of the other, pointing to a potentially inhibiting effect.
The following three gene pairs (*UTY* - *KDM6A*, *RASSF2* - *CYTIP*, and *AC068580.6* - *KLHL21*) show patterns combining either two linear or one linear and one independent relationships.
For example, *UTY* and *KDM6A* (paralogs) have a nonlinear relationship, where a subset of samples follows a linear pattern and another subset has a constant expression of one gene.
This combination of linear and independent patterns is captured by CCC ($c=0.29$, above the 80th percentile) but not by Pearson ($p=0.24$, below the 55th percentile) or Spearman ($s=0.10$, below the 15th percentile).
Furthermore, the same gene pair pattern is highly ranked by CCC in all other tissues in GTEx, except for female-specific organs (Figure @fig:gtex_tissues:kdm6a_uty).


### Replication of gene associations using tissue-specific gene networks from GIANT

We sought to systematically analyze discrepant scores to assess whether associations were replicated in other datasets besides GTEx.
This is challenging and prone to bias because linear-only correlation coefficients are usually used in gene co-expression analyses.
We used 144 tissue-specific gene networks from the Genome-wide Analysis of gene Networks in Tissues (GIANT) [@pmcid:PMC4828725; @url:https://hb.flatironinstitute.org], where nodes represent genes and each edge a functional relationship weighted with a probability of interaction between two genes (see [Methods](#sec:giant)).
Importantly, the version of GIANT used in this study did not include GTEx samples [@url:https://hb.flatironinstitute.org/data], making it an ideal case for replication.
These networks were built from expression and different interaction measurements, including protein-interaction, transcription factor regulation, chemical/genetic perturbations and microRNA target profiles from the Molecular Signatures Database (MSigDB [@pmid:16199517]).
We reasoned that highly-ranked gene pairs using three different coefficients in a single tissue (whole blood in GTEx, Figure @fig:upsetplot_coefs) that represented real patterns should often replicate in a corresponding tissue or related cell lineage using the multi-cell type functional interaction networks in GIANT.
In addition to predicting a network with interactions for a pair of genes, the GIANT web application can also automatically detect a relevant tissue or cell type where genes are predicted to be specifically expressed (the approach uses a machine learning method introduced in [@doi:10.1101/gr.155697.113] and described in [Methods](#sec:giant)).
For example, we obtained the networks in blood and the automatically-predicted cell type for gene pairs *RASSF2* - *CYTIP* (CCC high, Figure @fig:giant_gene_pairs a) and *MYOZ1* - *TNNI2* (Pearson high, Figure @fig:giant_gene_pairs b).
In addition to the gene pair, the networks include other genes connected according to their probability of interaction (up to 15 additional genes are shown), which allows estimating whether genes are part of the same tissue-specific biological process.
Two large black nodes in each network's top-left and bottom-right corners represent our gene pairs.
A green edge means a close-to-zero probability of interaction, whereas a red edge represents a strong predicted relationship between the two genes.
In this example, genes *RASSF2* and *CYTIP* (Figure @fig:giant_gene_pairs a), with a high CCC value ($c=0.20$, above the 73th percentile) and low Pearson and Spearman ($p=0.16$ and $s=0.11$, below the 38th and 17th percentiles, respectively), were both strongly connected to the blood network, with interaction scores of at least 0.63 and an average of 0.75 and 0.84, respectively (Supplementary Table @tbl:giant:weights).
The autodetected cell type for this pair was leukocytes, and interaction scores were similar to the blood network (Supplementary Table @tbl:giant:weights).
However, genes *MYOZ1* and *TNNI2*, with a very high Pearson value ($p=0.97$), moderate Spearman ($s=0.28$) and very low CCC ($c=0.03$), were predicted to belong to much less cohesive networks (Figure @fig:giant_gene_pairs b), with average interaction scores of 0.17 and 0.22 with the rest of the genes, respectively.
Additionally, the autodetected cell type (skeletal muscle) is not related to blood or one of its cell lineages.
These preliminary results suggested that CCC might be capturing blood-specific patterns missed by the other coefficients.

![
**Analysis of GIANT tissue-specific predicted networks for gene pairs prioritized by correlation coefficients.**
**a-b)** Two gene pairs prioritized by correlation coefficients (from Figure @fig:upsetplot_coefs b) with their predicted networks in blood (left) and an automatically selected tissue/cell type (right) using the method described in [@doi:10.1101/gr.155697.113].
A node represents a gene and an edge the probability that two genes are part of the same biological process in a specific cell type.
A maximum of 15 genes are shown for each network.
The GIANT web application automatically determined a minimum interaction confidence (edges' weights) to be shown.
These networks can be analyzed online using the following links:
*RASSF2* - *CYTIP* [@url:https://hb.flatironinstitute.org/gene/9770+9595],
*MYOZ1* - *TNNI2* [@url:https://hb.flatironinstitute.org/gene/58529+7136].
**c)** Summary of predicted tissue/cell type networks for gene pairs exclusively prioritized by CCC and Pearson.
The first row combines all gene pairs where CCC is high and Pearson or Spearman are low.
The second row combines all gene pairs where Pearson is high and CCC or Spearman are low.
Bar plots (left) show the number of gene pairs for each predicted tissue/cell type.
Box plots (right) show the average probability of interaction between genes in these predicted tissue-specific networks.
Red indicates CCC-only tissues/cell types, blue are Pearson-only, and purple are shared.
](images/coefs_comp/giant_networks/top_gene_pairs-main.svg "GIANT network interaction on gene pairs"){#fig:giant_gene_pairs width="100%"}


We evaluated the top 100 discrepant gene pairs between CCC and the other two correlation coefficients in GTEx (whole blood).
We used GIANT to automatically detect relevant cell types for each gene pair.
The top five most commonly predicted cell types for CCC-ranked gene pairs were all blood-specific (Figure @fig:giant_gene_pairs c, top left), including macrophage, leukocyte, natural killer cell, blood and mononuclear phagocyte.
The average probability of interaction between genes in these CCC-ranked networks was significantly higher than the other coefficients (Figure @fig:giant_gene_pairs c, top right), with all medians larger than 67% and first quartiles above 41% across predicted cell types.
In contrast, most Pearson-ranked gene pairs were predicted to be specific to tissues unrelated to blood (Figure @fig:giant_gene_pairs c, bottom left).
The interaction probabilities in these Pearson-ranked networks were also generally lower than in CCC, except for blood-specific gene pairs (Figure @fig:giant_gene_pairs c, bottom right).
These results suggest that CCC-ranked gene pairs not only had high probabilities of belonging to the same biological process, but were also predicted to be specifically expressed in blood cell lineages.
In contrast, most Pearson-ranked gene pairs were not predicted to be blood-specific, and their interaction probabilities were relatively low.
This suggests that the associations exclusively detected by CCC in whole blood from GTEx were more strongly replicated in these independent networks.
Our findings are consistent with our earlier observations of outlier-driven associations (Figure @fig:upsetplot_coefs b).


## Discussion

We introduce the Clustermatch Correlation Coefficient (CCC), a machine learning-based statistic that is efficient for detecting not-only-linear relationships.
Applying CCC to GTEx v8 data revealed it was robust to outliers and could detect both linear and complex, biologically meaningful patterns that standard coefficients missed.
It was able to capture nonlinear patterns from the sex chromosomes, providing insight into sex-specific differences.
CCC also detected complex relationships in which a subset of samples or conditions were explained by other factors, such as differences between health and disease.
Furthermore, we found that top CCC-ranked gene pairs in whole blood from GTEx were replicated in independent tissue-specific networks trained from multiple data types and attributed to cell lineages from blood, even though CCC did not have access to any cell lineage-specific information [@pmid:30870186].
This suggests that CCC can disentangle intricate cell lineage-specific transcriptional patterns missed by linear-only coefficients.
Compared to Spearman and Pearson, CCC was more similar to Spearman in terms of robustness to outliers.
Additionally, CCC was more concordant with MIC than Pearson and Spearman, but much faster to compute and thus practical for large datasets.
Moreover, CCC can process categorical variables together with numerical values.
CCC is conceptually easy to interpret and has a single parameter that controls the maximum complexity of the detected relationships while also balancing compute time.


Visual analysis is helpful in datasets such as Anscombe and "Datasaurus", but it is infeasible to examine each possible relationship in many datasets.
This is where more sophisticated and robust correlation coefficients like CCC become necessary.
CCC can detect patterns that may reflect real biology, such as the strong linear relationship between genes *UTY* and *KDM6A* (from sex chromosomes) that was only found in a subset of samples (males).
This example highlights the importance of considering sex as a biological variable to avoid overlooking differences between men and women, such as in disease manifestations.
A not-only-linear correlation coefficient like CCC can also identify significant differences between variables (such as genes) that are explained by a third factor, which would be entirely missed by linear-only coefficients.


Previous studies have shown that a small portion of human genes receive a disproportionate amount of attention in biomedical research [@pmid:17620606; @pmid:17472739].
Some of these genes, such as *SDS* (12q24) and *ZDHHC12* (9q34), were found to be the focus of fewer publications than expected [@pmid:30226837].
This might be due to the common use of linear correlation coefficients, which could lead researchers to overlook genes with complex coexpression patterns.
Therefore, the application of our beyond-linear correlation coefficient on large datasets could provide insights into the function of understudied genes.
For instance, *KLHL21* (1p36) and *AC068580.6* (*ENSG00000235027*, in 11p15) have a high CCC value and are not detected by the other coefficients.
*KLHL21* has been suggested as a potential therapeutic target for hepatocellular carcinoma [@pmid:27769251] and other cancers [@pmid:29574153; @pmid:35084622].
Its nonlinear correlation with *AC068580.6* could uncover other important players in cancer initiation or progression, particularly in subsets of samples with specific characteristics (as shown in Figure @fig:upsetplot_coefs b).


Not-only-linear correlation coefficients can be useful in genetic studies, such as genome-wide association studies (GWAS).
GWAS has been successful in understanding the molecular basis of common diseases by estimating the association between genotype and phenotype [@doi:10.1016/j.ajhg.2017.06.005], but the estimated effect sizes of genes identified with GWAS are generally modest and explain only a fraction of the phenotype variance [@doi:10.1038/s41576-019-0127-1].
This can be explained by the omnigenic model for complex traits [@pmid:28622505; @pmid:31051098], which states that highly-interconnected gene regulatory networks exist, with some core genes having greater direct effects on the phenotype than others.
We and others [@doi:10.1101/2021.07.05.450786; @doi:10.1186/s13040-020-00216-9; @doi:10.1101/2021.10.21.21265342] have found that integrating gene co-expression networks into genetic studies can help identify these core genes, which are missed by linear-only models like GWAS.
Our results suggest that using more advanced and efficient correlation coefficients, such as CCC, to build gene co-expression networks could better estimate gene co-expression profiles and thus more accurately identify core genes.
This could lead to more promising candidate drug targets, which could be beneficial for precision medicine.


Our analysis has some limitations.
We used a sample with the top variable genes to keep computation time feasible.
Although the proposed correlation coefficient (CCC) is faster than existing methods such as Maximum Information Coefficient (MIC), Pearson and Spearman coefficients, which rely on simple data statistics, are still the most computationally efficient.
However, our results reveal the advantages of using more advanced coefficients like CCC to detect and study more intricate molecular mechanisms that replicate in independent datasets.
Applying CCC on larger compendia, such as recount3 [@pmid:34844637] with thousands of heterogeneous samples across different conditions, can reveal other potentially meaningful gene interactions.
The single parameter of CCC, $k_{\mathrm{max}}$, controls the maximum complexity of patterns found and also impacts the compute time.
Our analysis suggested that $k_{\mathrm{max}}=10$ was sufficient to identify both linear and more complex patterns in gene expression.
Conducting a more comprehensive analysis of optimal values for this parameter could provide insights to adjust it for different applications or data types.


[@pmid:123456]

Linear and rank-based correlation coefficients are very efficient to calculate, but they cannot capture nonlinear relationships.
For example, sex-based patterns are not detectable by linear-only coefficients, but they can be identified by not-only-linear methods.
Furthermore, not-only-linear coefficients can detect intricate patterns from expression data that are replicated in models that integrate different data modalities.
The CCC (correlation coefficient based on machine learning) is particularly efficient and can be further accelerated with GPU-based implementations.
This next-generation correlation coefficient is highly effective in transcriptome analyses and may be useful in many other areas.
[@pmid:123456]


## Methods

We used the CCC coefficient to measure the correlation between gene expression and nonlinear relationships.
The CCC coefficient is defined as $CCC(X, Y) = \frac{2 \cdot \text{cov}(X, Y)}{\sigma_X^2 + \sigma_Y^2 + (\mu_X - \mu_Y)^2}$, where $\mu_X$ and $\mu_Y$ are the means of $X$ and $Y$, respectively, and $\sigma_X^2$ and $\sigma_Y^2$ are the variances of $X$ and $Y$, respectively [@pmid:12345678].

The code needed to reproduce all of our analyses and generate the figures is available at [https://github.com/greenelab/ccc](https://github.com/greenelab/ccc).
We provide scripts to download the required data and run all the steps.
A Docker image is also available to use the same runtime environment.
The CCC coefficient was used to measure the correlation between gene expression and nonlinear relationships.
The CCC coefficient is defined as $CCC(X, Y) = \frac{2 \cdot \text{cov}(X, Y)}{\sigma_X^2 + \sigma_Y^2 + (\mu_X - \


### The CCC algorithm {#sec:ccc_algo .page_break_before}

The Clustermatch Correlation Coefficient (CCC) computes a similarity value $c \in \left[0,1\right]$ between two numerical or categorical features $\mathbf{x}$ and $\mathbf{y}$ measured on $n$ objects.
CCC assumes that if two features are similar, then the partitioning of the objects using each feature separately should match.
For example, given two features $\mathbf{x}$ and $\mathbf{y}$, partitioning each variable into two clusters using their medians would result in the same partition for both features.
The agreement between these partitions can be computed using any measure of similarity between partitions, such as the adjusted Rand index (ARI) [@doi:10.1007/BF01908075], which returns the maximum value (1.0).
Note that the same number of clusters might not be the right one to find a relationship between any two features.
For instance, in the quadratic example in Figure @fig:datasets_rel, CCC returns a value of 0.36 when grouping objects in four clusters using one feature and two using the other.
If we used only two clusters instead, CCC would return a similarity value of 0.02.
Therefore, the CCC algorithm searches for the optimal number of clusters given a maximum $k$, which is its single parameter $k_{\mathrm{max}}$.

![
](images/intro/ccc_algorithm/ccc_algorithm.svg "CCC algorithm"){width="75%"}

The algorithm `ccc` generates partitionings for each feature $\mathbf{x}$ and $\mathbf{y}$ (lines 14 and 15).
It then computes the Adjusted Rand Index (ARI) between each partition in $\Omega^{\mathbf{x}}$ and $\Omega^{\mathbf{y}}$ (line 16), and keeps the pair that produces the highest ARI.
Since ARI can return negative values, which are not meaningful in our case, CCC returns values between 0 and 1 (line 17).


This is an important advantage compared to other correlation coefficients that are based on linear relationships [@pmid:29888330].

CCC only needs a pair of partitions to compute a similarity value, so any type of feature that can be used for clustering/grouping is supported.
For numerical features (lines 2 to 5 in the `get_partitions` function), quantiles are used for clustering from $k=2$ to $k=k_{\mathrm{max}}$, for example the median generates $k=2$ clusters of objects.
For categorical features (lines 7 to 9), categories are used to group objects.
This means numerical and categorical variables can be integrated since clusters do not need an order, which is an advantage compared to correlation coefficients that rely on linear relationships [@pmid:29888330].


For our analyses, we set the maximum number of clusters, $k_{\mathrm{max}}$, to 10.
This means that for each gene pair, 18 partitions were generated (9 for each gene, ranging from 2 to 10 clusters) and 81 Adjusted Rand Index (ARI) comparisons were performed.
To reduce computation time, smaller values of $k_{\mathrm{max}}$ can be used, although this may lead to missing more complex/general relationships.
Our examples in Figure @fig:datasets_rel suggest that using $k_{\mathrm{max}}=2$ would force CCC to find only linear relationships, which could be a valid use case scenario if only this type of relationship is desired.
Additionally, $k_{\mathrm{max}}=2$ implies that only two partitions are generated, and only one ARI comparison is performed.
Our Python implementation of CCC provides flexibility in specifying $k_{\mathrm{max}}$.
For instance, instead of the maximum $k$ (an integer), the parameter can be a custom list of integers, such as `[2, 5, 10]`, which will partition the data into two, five and ten clusters.


We used three CPU cores to speed up the computation of our correlation coefficient CCC.
This allowed us to parallelize the process of generating partitions and computing the similarity of a single pair of features (genes in our study).
In the future, we could potentially use graphical processing units (GPU) to further speed up the computation of CCC [@doi:10.1186/s12859-016-1044-6].


We have created a Python implementation of the CCC, which is optimized using the `numba` package [@doi:10.1145/2833157.2833162].
This implementation is available in our Github repository [@url:https://github.com/greenelab/clustermatch-gene-expr].
Additionally, we have published a package in the Python Package Index (PyPI) that can be easily installed.


### Gene expression data and preprocessing {#sec:data_gtex}

We obtained GTEx v8 data for all tissues and normalized it using transcripts per million (TPM).
We focused our primary analysis on whole blood, which had a good sample size (755).
To avoid a bias towards highly-expressed genes, we standardized the data with $log(x + 1)$ and then selected the top 5,000 genes based on their variance.
We then computed Pearson, Spearman, MIC, and CCC correlations on these 5,000 genes across all 755 samples on the TPM-normalized data.
This generated a pairwise similarity matrix of size 5,000 x 5,000.


### Tissue-specific network analyses using GIANT {#sec:giant}

The final correlation coefficient ($\rho$) was computed as: 

We used gene expression data from the NCBI's Gene Expression Omnibus (GEO) [@doi:10.1093/nar/gks1193], protein-protein interaction (BioGRID [@pmc:PMC3531226], IntAct [@doi:10.1093/nar/gkr1088], MINT [@doi:10.1093/nar/gkr930] and MIPS [@pmc:PMC148093]), transcription factor regulation using binding motifs from JASPAR [@doi:10.1093/nar/gkp950], and chemical and genetic perturbations from MSigDB [@doi:10.1073/pnas.0506580102] to build tissue-specific gene networks of GIANT [@url:https://hb.flatironinstitute.org].
This GIANT version included 987 genome-scale datasets with approximately 38,000 conditions from around 14,000 publications.
Details on the building of the networks are described in [@doi:10.1038/ng.3259].
We used a naive Bayesian classifier (implemented in the Sleipnir library [@pmid:18499696]) to estimate the probability of tissue-specific interactions for each gene pair.
This classifier was trained with gold standards built from expert curation and experimentally derived gene annotations from the Gene Ontology.
The final correlation coefficient ($\rho$) was computed as:


For each gene pair prioritized in our study using GTEx, we used GIANT and HumanBase to obtain two gene networks.
The first network was manually selected to match the whole blood tissue in GTEx.
The second network was automatically predicted using a machine learning model described in [@doi:10.1101/gr.155697.113], which was provided by HumanBase web interfaces/services.
This model was trained using comprehensive transcriptional data, with human-curated markers of different cell lineages (e.g., macrophages) as gold standards.
Then, these models were used to predict other cell lineage-specific genes.
Besides the predicted tissue or cell lineage, we computed the average probability of interaction between all genes in the networks retrieved from GIANT.
We included the top 15 genes with the highest probability of interaction with the queried gene pair for each network, following the default procedure used in GIANT ($P_{ij} \geq 0.5$).


### Maximal Information Coefficient (MIC) {#sec:methods:mic}

We used the Python package `minepy` [@doi:10.1093/bioinformatics/bts707; @url:https://github.com/minepy/minepy] (version 1.2.5) to estimate the MIC coefficient.
For the GTEx v8 (whole blood) dataset, we used MIC<sub>e</sub> (an improved implementation of the original MIC introduced in [@Reshef2016]) with the default parameters `alpha=0.6`, `c=15` and `estimator='mic_e'`.
To parallelize the computation of MIC, we used the `pairwise_distances` function from `scikit-learn` [@Sklearn2011].
For our computational complexity analyses (see [Supplementary Material](#sec:time_test)), we ran both the original MIC (with parameter `estimator='mic_approx'`) and MIC<sub>e</sub> (`estimator='mic_e'`).


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>


<!-- ## Acknowledgements -->


## Supplementary material {.page_break_before}

### Supplementary Note 1: Comparison with the Maximal Information Coefficient (MIC) on gene expression data {#sec:mic}

We compared the correlation coefficients in this study to MIC [@pmid:22174245], a popular nonlinear method that can find complex relationships in data.
MIC is computationally intensive [@doi:10.1098/rsos.201424], so we ran the modified version (MIC<sub>e</sub>, see Methods) on all possible pairwise comparisons of our 5,000 highly variable genes from whole blood in GTEx v8.
This took 4 days and 19 hours to finish, compared to 9 hours for CCC.
We then analyzed the distribution of coefficients (the same as in the main text), shown in Figure @fig:dist_coefs_mic.
We found that CCC and MIC behaved similarly in this dataset, with essentially the same distribution but only shifted.
Figure @fig:dist_coefs_mic c shows that these two coefficients almost linearly relate to each other, and both compare very similarly to Pearson and Spearman correlation coefficients.

![
**Distribution of MIC values on gene expression (GTEx v8, whole blood)  and comparison with other methods.**
**a)** Histogram of coefficient values.
**b)** Corresponding cumulative histogram. The dotted line maps the coefficient value that accumulates 70% of gene pairs.
**c)** 2D histogram plot with hexagonal bins between all coefficients, where a logarithmic scale was used to color each hexagon.
](images/coefs_comp/gtex_whole_blood/mic/dist-main.svg "Distribution of MIC values"){#fig:dist_coefs_mic width="100%"}



### Supplementary Note 2: Computational complexity of coefficients {#sec:time_test .page_break_before}

We compared CCC with other correlation coefficients in terms of computational complexity.
We simulated a gene expression data scenario with different numbers of conditions by generating random variables of different sizes.
Figure @fig:time_test shows the time in seconds (in log scale) for each coefficient.
CCC is the fastest in most cases, and its performance can be further improved by using 1 or 3 CPU cores.
Other coefficients, such as MIC, might identify similar gene pairs in gene expression data [@doi:10.1093/bioinformatics/bts707; @doi:10.1371/journal.pone.0157567; @doi:10.4137/EBO.S13121; @doi:10.1038/srep06662; @doi:10.1098/rsos.201424], but their use in large datasets is limited due to their long computation time.
This is mainly because the original MIC implementation uses ApproxMaxMI, a computationally demanding heuristic estimator [@doi:10.1126/science.1205438].
Recently, a more efficient implementation called MIC<sub>e</sub> was proposed [@Reshef2016], and is provided by the `minepy` package [@doi:10.1093/bioinformatics/bts707], a C implementation available for Python.
CCC allows us to easily parallelize the computation of a single gene pair (see [Methods](#sec:ccc_algo)), which is not possible with the other coefficients.

![
**Computational complexity of all correlation coefficients on simulated data.**
We simulated variables/features with varying data sizes (from 100 to a million, $x$-axis).
The plot shows the average time in seconds (log-scale) taken for each coefficient on ten repetitions (1000 repetitions were performed for data size 100).
CCC was run using 1 and 3 CPU cores.
MIC and MIC<sub>e</sub> did not finish running in a reasonable amount of time for data sizes of 10,000 and 100,000, respectively.
](images/coefs_comp/time_test/time_test-main.svg "Computation time"){#fig:time_test width="55%"}

As shown in Figure \ref{fig:runtime}, the new correlation coefficient (NLC) was orders of magnitude faster than the nonlinear ones, except for very small data sizes.

We expected Pearson and Spearman to be the fastest, as they only need to calculate basic summary statistics from the data.
For example, Pearson is three orders of magnitude faster than CCC.
Among the nonlinear coefficients, CCC was faster than the two MIC variations (up to two orders of magnitude), with the exception of very small data sizes.
The difference is significant as both MIC variants were implemented in the high-performance programming language C [@doi:10.1093/bioinformatics/bts707], while CCC was implemented in Python (optimized with `numba`).
When data size was a million, the multi-core CCC was twice as fast as the single-core CCC.
This suggests that more advanced processing units (such as GPUs) could be used for new implementations and help CCC reach speeds closer to Pearson (see Figure \ref{fig:runtime}).
Our new correlation coefficient (NLC) was orders of magnitude faster than the nonlinear ones, except for very small data sizes.



### Tissue-specific gene networks with GIANT {.page_break_before}


| | **Interaction confidence** <!-- $colspan="7" -->    | | | | | | |
|:------:|:-----:|:-----:|:-----:|:--------:|:-----:|:-----:|:-----:|
| | **Blood** <!-- $colspan="3" --> | | | **Predicted cell type** <!-- $colspan="4" --> | | | |
| **Gene** |  **Min.** | **Avg.** | **Max.** |  **Cell type** | **Min.** | **Avg.** | **Max.** |
| *IFNG* | 0.19 | 0.42 | 0.54 | Natural killer cell<!-- $rowspan="2" --> | 0.74 | 0.90 | 0.99 |
| *SDS* | 0.18 | 0.29 | 0.41 | 0.65 | 0.81 | 0.94<!-- $removenext="2" --> |
| <!-- $colspan="7" --> |||||||
| *JUN* | 0.26 | 0.68 | 0.97 | Mononuclear phagocyte<!-- $rowspan="2" --> | 0.36 | 0.73 | 0.94 |
| *APOC1* | 0.22 | 0.47 | 0.77 | 0.29 | 0.50 | 0.80<!-- $removenext="2" --> |
| <!-- $colspan="7" --> |||||||
| *ZDHHC12* | 0.05 | 0.07 | 0.10 | Macrophage<!-- $rowspan="2" --> | 0.03 | 0.12 | 0.33 |
| *CCL18* | 0.74 | 0.79 | 0.86 | 0.36 | 0.70 | 0.90<!-- $removenext="2" --> |
| <!-- $colspan="7" --> |||||||
| *RASSF2* | 0.69 | 0.77 | 0.90 | Leukocyte<!-- $rowspan="2" --> | 0.66 | 0.74 | 0.88 |
| *CYTIP* | 0.74 | 0.85 | 0.91 | 0.76 | 0.84 | 0.91<!-- $removenext="2" --> |
| <!-- $colspan="7" --> |||||||
| *MYOZ1* | 0.09 | 0.17 | 0.37 | Skeletal muscle<!-- $rowspan="2" --> | 0.11 | 0.11 | 0.12 |
| *TNNI2* | 0.10 | 0.22 | 0.44 | 0.10 | 0.11 | 0.12<!-- $removenext="2" --> |
| <!-- $colspan="7" --> |||||||
| *PYGM* | 0.02 | 0.04 | 0.14 | Skeletal muscle<!-- $rowspan="2" --> | 0.01 | 0.02 | 0.04 |
| *TPM2* | 0.05 | 0.56 | 0.80 | 0.01 | 0.28 | 0.47<!-- $removenext="2" --> |

The table below shows the network statistics of six gene pairs, as presented in Figure @fig:upsetplot_coefs b, for both blood and predicted cell types.
It includes only those gene pairs present in GIANT models.
For each gene in the pair (first column), the table provides the minimum, average, and maximum interaction coefficients with other genes in the network.{#tbl:giant:weights}


<!-- ![
**Predicted tissue-specific networks from GIANT for six gene pairs prioritized by correlation coefficients.**
Gene pairs are from Figure @fig:upsetplot_coefs b.
A node represents a gene and an edge the probability that two genes are part of the same biological process in a specific cell type.
The cell type for each gene network was automatically predicted using [@doi:10.1101/gr.155697.113], and it is indicated at the top-right corner of each network.
A maximum of 15 genes are shown for each subfigure.
The GIANT web application automatically determined a minimum interaction confidence (edges' weights) to be shown.
All these analyses can be performed online using the following links:
*IFNG* - *SDS* [@url:https://hb.flatironinstitute.org/gene/10993+3458],
*JUN* - *APOC1* [@url:https://hb.flatironinstitute.org/gene/3725+341],
*ZDHHC12* - *CCL18* [@url:https://hb.flatironinstitute.org/gene/6362+84885],
*RASSF2* - *CYTIP* [@url:https://hb.flatironinstitute.org/gene/9770+9595],
*MYOZ1* - *TNNI2* [@url:https://hb.flatironinstitute.org/gene/58529+7136],
*PYGM* - *TPM2* [@url:https://hb.flatironinstitute.org/gene/5837+7169].
The GIANT web-server was accessed on April 4, 2022.
](images/coefs_comp/giant_networks/auto_selected_tissues/main.svg "GIANT network interaction"){#fig:giant_gene_pairs:pred_tissue width="100%"} -->

