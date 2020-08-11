#Quality control for Plasma & Platelet & PBMC & Saliva

> Note: 
>
> DNA is fragmented and relatively stable in cell-free environment, many papers didnot include DNA quality control (QC) step by qPCR, they usually just exclude those samples with purified DNA yield less than the requirement of a specific DNA detection method.
>
> so this version didnot included DNA QC step in different biosources below, which can also be added if necessary .



##1.Plasma RNA 

Now that we have built more and more collaboration with different hospitals, the Quality Control(QC) of plasma samples is very important. We will test plasma before use by the following steps: 

1. Plasma purity.
   The standart procedure to isolate plasma from blood is 2-step centrifuge: 1,900g 10min -> 16,000g 10min, then draw the suppernatant carefully. But some samples might remain cell residue in the plasma. So before RNA extraction, we have to cetrefuge the plasma again to remove cell residue.
2. __RNA yield.__
   In general, 1ml patients' plasma could extract > 50ng cell-free RNA (Qubit result). If your RNA yield is too low, might exist RNA degradation, which is not suitable for downstream experiment.
3. RNA length distribution.
   Most of the exRNA in plasma is 20-30nt small RNA or degraded fragments from long RNA (mRNA, lncRNA, etc). We test RNA length distribution by Agilent RNA 6000 pico chip(Novegene, about 1 week).
4. __Marker genes test by qPCR.__
   Extract cfRNA in ```500ul``` plasma, reverse transcripted by 2 methods: 
* Small RNA, RT by miRcute Plus miRNA First-Strand cDNA Synthesis Kit, qPCR by miRcute Plus miRNA qPCR Detection Kit
  (SYBR Green).

* Long RNA, RT by RevertAid First Strand cDNA Synthesis Kit(Thermo Fisher Scientific), qPCR by TIANScript  II SYBR Kit.
  Test targets:

  > Fanjia, reference gene: miR-1228(-3p)

|Type|Name|Forward primer|Reverse primer|Note|Ref.|Max Cq|
|---|---|---|---|---|---|---|
|Small RNA |miR-15(a-5p) | TAGCAGCACATCATGGTTTACA|- |Abundant in 2,763 plasma | Nature communication|41|
| Small RNA| miR-16(-5p) |TAGCAGCACGTAAATATTGGCG | -|Abundant in 2,763 plasma | Nature communication|36|
|Small RNA |miR-21(-5p) |GCTTATCAGACTGATGTTG |- |Abundant in 2,763 plasma | Nature communication|35|
| Small RNA|miR-451(a) | ACCGTTACCATTACTGAGT|- | Abundant in 2,763 plasma | Nature communication|31|
|Small RNA |miR-486(-5p) |TCCTGTACTGAGCTGCCCCGAG | -| Abundant in 2,763 plasma | Nature communication|33|
|Small RNA |miR-1228*(-5p) |AATGTGGGCGGGGGCAGGTGTGTG | -|Abundant in 2,763 plasma | Nature communication|36|
|Small RNA |hY4 | CCGATGGTAGTGGGTTATCAG| -| Abundant in 2,763 plasma | Nature communication|29|
| Long RNA| GAPDH| GAACGGGAAGCTTGTCATCAA|ATCGCCCCACTTGATTTTGG |Internal control | Nature 2018(Quake) |36|
| Long RNA| ACTB| CGCGAGAAGATGCCCAGATC| TCACCGGAGTCCATCACGA|Internal control | Nature 2018(Quake) |37|
| Long RNA| HULC| TCATGATGGAATTGGAGCCTT| CTCTTCCTGGCTTGCAGATTG| lncRNA biomarker for HCC, PAAD |Trends in cancer |37|
|Long RNA | MALAT1| AAAGCAAGGTCTCCCCACAAG| GGTCTGTGCTAGATCAAAAGGCA|lncRNA biomarker for HCC, PAAD | Trends in cancer|39|



## 2.Platelet (RNA)  

search formula: (platelet*[TI] OR TEP[TI] OR PLT[TI] OR thrombocyte*[TI]) AND (RNA[TI] OR lncrna[TI] OR mir[TI] OR mirna[TI]) AND (profile[TIAB] OR distribution[TIAB] OR landscape[TIAB] OR atlas[TIAB])

> __reference__: 
>
> 1._Best. 2019. nature protocal. RNA sequencing and swarm intelligence–enhanced classiﬁcation algorithm development for blood-based disease diagnostics using spliced blood platelet RNA_
>
> 2._Best. 2017. cancer cell. Swarm Intelligence-Enhanced Detection of NonSmall-Cell Lung Cancer Using Tumor-Educated Platelets_
>
> 3._Best. 2015. cancer cell. RNA-Seq of Tumor-Educated Platelets Enables Blood-Based Pan-Cancer, Multiclass, and Molecular Pathway Cancer Diagnostics_
>
> 4._Pontes. 2015. plos one. The miRNA Profile of Platelets Stored in a Blood Bank and Its Relation to Cellular Damage from Storage_



1. Platelet purity.
   The standart procedure to isolate Platelet from blood is 2-step centrifuge, detail see blood component co-seperation methods.

   > \1. 4度先过夜后放入-80度
   >
   > \2. 血小板加入RNAlater时不要产生气泡，缓慢吹打
   >
   > \3. 高胆固醇的血会比较粘稠，难以分离，血小板产量会下降很多
   >
   > \4. 吸取<=9/10的体积，避免血细胞污染
   >
   > \5. 文献报道的单独分离血小板最佳离心温度是10-16度，与一般血浆4度分离略有差异
   >
   > \6. 阿司匹林等药物对血小板有很大影响，需要登记最近一周部分药物使用情况

2. __Cell count.__

   ```<10``` nucleated cells per ```10 million``` platelets, for a single leukocyte is comparable to the RNA content of ~1,000 platelets.

   **Option1**: fix about half of the total platelet pellet (10ul) in 3.7% (wt/vol) paraformaldehyde (PFA), counting the number of nucleated cells per 10 million platelets in a chamber under a table-top light microscope

   **Option2**: resuspending ﬁxed cells in a crystal violet staining solution and observing them with a table-top light microscope. 

   > * PFA (多聚甲醛)，常3.7% (wt/vol)浓度用于固定细胞，0.01M PBS用于稀释至特定浓度，室温或4℃固定10-30min，用缓冲液漂洗后即可用于染色。适合组织和细胞的光镜免疫化学研究
   > * crystal violet (结晶紫)，可以把细胞染成深紫色
   > * (脱色液)
   > * 普通光学显微镜（高倍镜），蓝色物镜
   > * 载玻片和盖玻片
   > * (细胞计数表/器)
   >

   尝试方法：2ml 全血提取约150-600*10^6个血小板，50ul RNAlater溶解后（这里浓缩40倍，常规新鲜的全血血细胞计数需要稀释20倍），根据初期摸索结果需要稀释到200-500倍才利于计数。

   血小板计数：取5ul加395ul血小板稀释液(80倍)，分别取适量（~10ul）加入不同计数板，静置15min后用于计数。

   白细胞单独计数：在50ul未稀释的血小板里取5ul滴在载玻片上，（盖玻片）涂布均匀，涂片后用PFA固定10-30min,（摸索实验中直接在5ul体系加15ulPFA固定，之后取5ul涂片染色)，结晶紫染色1min，清水冲走染色液后，直接在低倍镜下数细胞核被染成紫色的细胞个数。

   共同计数：在50ul未稀释的血小板里取1ul加入399ul血小板稀释液（400倍），吸取1ul，加入10ul 4%PFA固定30min左右，再加入10ul结晶紫染液(1:1)，取10ul用于计数板计数。

3. __RNA yield.__
   In general, ```~2ml``` whole blood (~1ml plasma) could extract ```50(5-90)ng``` RNA (Qubit result). 200-500*10^6 platelets/ml whole blood, platelet RNA yield moderately correlated to the platelet counts.

   too low means might exist RNA degradation, too high means nucleated cells contamination (can be validated in cell count), both are not suitable for downstream experiment.

   samples with a yield of ```<100 pg``` of total RNA should not be included.

4. RNA length distribution.
   test RNA length distribution by Agilent RNA 6000 pico chip(Novegene, about 1 week)

   * A: clearly visible __5S, 18S, and 28S__ ribosomal RNA peaks (distinguishable in the 100- to 200-nt, 1,500- to 2,000-nt, and 4,000-nt regions of the Bioanalyzer graphs, respectively)
   * B: ```RIN > 7```

   > A OR B

![image-20200704122824496](./img/PLT_QC2.png)



5. (Marker genes test by qPT-PCR.)

>  Not always needed, 2019 nature protocal qc does not include this step.

Extract RNA in platelet  (1ml plasma), reverse transcripted by 2 methods: 

- Small RNA: TIANGEN miRCute (SYBR Green).
- Long RNA: TIANGEN Script (SYBR Green).
  Test targets:

| Type     | name                  | Forward                       | Reverse                 | note                           | Reference               | max Ct |
| -------- | --------------------- | ----------------------------- | ----------------------- | ------------------------------ | ----------------------- | ------ |
| long     | __ACTB__              | CGCGAGAAGATGCCCAGATC          | TCACCGGAGTCCATCACGA     | High TPM                       | Best. 2017. cancer cell |        |
| long     | __GAPDH__             | GAACGGGAAGCTTGTCATCAA         | ATCGCCCCACTTGATTTTGG    |                                |                         |        |
| Long RNA | **HULC**              | TCATGATGGAATTGGAGCCTT         | CTCTTCCTGGCTTGCAGATTG   | lncRNA biomarker for HCC, PAAD | Trends in cancer        |        |
| Long RNA | **MALAT1**            | AAAGCAAGGTCTCCCCACAAG         | GGTCTGTGCTAGATCAAAAGGCA | lncRNA biomarker for HCC, PAAD | Trends in cancer        |        |
| long     | B2M                   | NA                            | NA                      | High TPM                       | Best. 2017. cancer cell |        |
| long     | PPBP                  | NA                            | NA                      | High TPM                       | Best. 2017. cancer cell |        |
| short    | mir-126(-3p)          | gcg**tcgtaccgtgagtaataatgcg** | -                       | abundant                       | PMID26646931            |        |
| short    | **mir-223(-3p)**      | cgc**tgtcagtttgtcaaatacccca** | -                       | abundant                       | PMID26646931            |        |
| short    | **hsa-let-7i(-5p)**   | GCG**TGAGGTAGTAGTTTGTGCTGTT** | -                       | abundant                       | Pontes. 2015. plos one  |        |
| short    | miR-191(-5p)          | **CAACGGAAUCCCAAAAGCAGCUG**   | -                       | abundant                       | Pontes. 2015. plos one  |        |
| short    | **hsa-miR-127(-3p)**  | **tcggatccgtctgagcttggc-**    | -                       | Quality marker                 | Pontes. 2015. plos one  |        |
| short    | **hsa-miR-320a(-3p)** | **aaaagctgggttgagagggcga**    | -                       | Quality marker                 | Pontes. 2015. plos one  |        |

##3. Saliva RNA

> 2020, pengfei, adapted from siqi plasma RNA QC protocal

> reference: 
>
> 1._Wong, 2018, clinical chemistry, Discovery and Validation of Salivary Extracellular RNA Biomarkers for Noninvasive Detection of Gastric Cancer._ 
>
> 2._Wong, 2018, clinical chemistry, Characterization of Human Salivary Extracellular RNA by Next-generation Sequencing._ 
>
> 3.*Wong, 2015, clinical chemistry, The Landscape of MicroRNA, Piwi-Interacting RNA, and Circular RNA in Human Saliva.*
>
> 4.*Wong, 2011, clinical chemistry, Direct Saliva Transcriptome Analysis.*
>
> 5.*Wong, 2009, Clin Cancer Res, Salivary microRNA: Discovery, Characterization, and Clinical Utility for Oral Cancer Detection.*



1. Saliva purity.
   The standart procedure to isolate saliva supernatent from saliva mix is 1-step centrifuge, detail see saliva seperation methods.

2. __RNA yield.__
   In general, ```~1ml``` cell-free saliva could extract ```20-80ng``` RNA (Qubit result). 

   total RNA amount ```<5 ng```  was not performed.

3. RNA length distribution.
   test RNA length distribution by Agilent RNA 6000 pico chip (Novegene, about 1 week)

   ```RIN > 7```

4. (Marker genes test by qPT-PCR.)

   Extract RNA in 2ml cell-free saliva, reverse transcripted by 2 methods: 

   - Small RNA: TIANGEN miRCute (SYBR Green).
   - Long RNA: TIANGEN Script (SYBR Green).
     Test targets:

| Type  | name              | Forward                        | Reveres                 | Lenth | note             | Reference                      |
| ----- | ----------------- | ------------------------------ | ----------------------- | ----- | ---------------- | ------------------------------ |
| long  | **ACTB**          | CCTCGCCTTTGCCGATCC             | GAGCGCGGCGATATCATCA     | 73bp  | Internal control | Wong, 2018, clinical chemistry |
| long  | **GAPDH**         | CCAACTGCTTAGCACCCCTG           | GGGCCATCCACAGTCTTCTG    | 112bp | Internal control | Wong, 2018, clinical chemistry |
| long  | **SPINK7**        | CATCACCTATGGGAATGAATGTC        | TCCATCGTGAAGAAACTGAACTC | 79bp  | __mRNA marker__  | Wong, 2018, clinical chemistry |
| long  | **PPL**           | CCGGAGCATCTCTAACAAGGA          | ACCTGGTCGGCATTCTTCTG    | 66bp  | __mRNA marker__  | Wong, 2018, clinical chemistry |
| long  | SEMA4B            | ATCCAGGACATCGAGGGAGC           | GTTGGTACAAAAGACGGGGAC   | 77bp  | __mRNA marker__  | Wong, 2018, clinical chemistry |
| short | **mir-140-5p**    | ccg**cagtggttttaccctatggtag**  | -                       |       | __miRNA marker__ | Wong, 2018, clinical chemistry |
| short | **mir-301a(-3p)** | ccg**cagtgcaatagtattgtcaaagc** | -                       |       | __miRNA marker__ | Wong, 2018, clinical chemistry |
| short | **mir-223(-3p)**  | cgc**tgtcagtttgtcaaatacccca**  | -                       |       | Top abundant     | Wong, 2018, clinical chemistry |
| short | **mir-21(-5p)**   | GCTTATCAGACTGATGTTG            | -                       |       | Top abundant     | Wong, 2018, clinical chemistry |
| short | **miR-16(-5p)**   | TAGCAGCACGTAAATATTGGCG         | -                       |       | Top abundant     | Wong, 2009, Clin Cancer Res    |





##4.PBMC RNA

> reference: 
>
> 1._Hoda, 2017, genomics, Transcriptome landscape of human primary monocytes at different sequencing depth_
>
> 2. Google: how many Peripheral blood mononuclear cell ml blood.

search formula: (pbmc*[TI] OR monocyte*[TI] OR lymphocyte*[TI] OR wbc[TI] OR leukocyte*[TI] OR leucocyte*[TI]) AND (RNA[TI] OR lncrna[TI] OR mir[TI] OR mirna[TI] OR transcript*[TI]) AND (profile[TIAB] OR distribution[TIAB] OR landscape[TIAB] OR atlas[TIAB])

1. PBMC purity.
   The standart procedure to isolate PBMC from whole blood is 2-step centrifuge, detail see blood component co-seperation methods.

2. __RNA yield.__
   In general, ```~2ml``` whole blood (~1ml plasma) could extract ```1-6*10^6```cells,  ``` 1-6ug``` RNA using miRNeasy Mini Kit (Qiagen), 1 μg RNA/million PBMCs (nanodrop/agilent2100 result). 

   total RNA amount ```<? ng```  was not performed.

3. RNA length distribution.
   test RNA length distribution by Agilent RNA 6000 pico chip (Novegene, about 1 week)

   ```RIN > 7```

4. (Marker genes test by qPT-PCR.)

   Extract RNA in 2ml whole blood, reverse transcripted by 2 methods: 

   - Small RNA: TIANGEN miRCute (SYBR Green).

   - Long RNA: TIANGEN Script (SYBR Green).

     Test targets:

| Type | name      | F                    | R                    | L     | Note               | reference            |
| ---- | --------- | -------------------- | -------------------- | ----- | ------------------ | -------------------- |
| long | __ACTB__  | CCTCGCCTTTGCCGATCC   | GAGCGCGGCGATATCATCA  | 73bp  | Internal control   | Hoda, 2017, genomics |
| long | __GAPDH__ | CCAACTGCTTAGCACCCCTG | GGGCCATCCACAGTCTTCTG | 112bp | Universial control |                      |
| long | PPIA      | NA                   | NA                   |       | Internal control   | Hoda, 2017, genomics |



#Plate setup

| Long | 1#Plasma rep1 | 1#Plasma rep2 | 1#Plasma rep3 | 1#PLT rep1 | 1#PLT rep2 | 1#PLT rep3 |
| ---- | ------------- | ------------- | ------------- | ---------- | ---------- | ---------- |
| 1    | GAPDH         |               |               | GAPDH      |            |            |
| 2    | ACTB          |               |               | ACTB       |            |            |
| 3    | HULC          |               |               | HULC       |            |            |
| 4    | MALAT1        |               |               | MALAT1     |            |            |
| 5    | NEG           |               |               | NEG        |            |            |
| 6    |               |               |               |            |            |            |
| 7    |               |               |               |            |            |            |
| 8    |               |               |               |            |            |            |

2 samples per plate (**3 rep**)



| short | 1#Plasma rep1 | 1#Plasma rep2 | 1#Plasma rep3 | 1#PLT rep1 | 1#PLT rep2 | 1#PLT rep3 |
| ----- | ------------- | ------------- | ------------- | ---------- | ---------- | ---------- |
| 1     | 15            |               |               | 15         |            |            |
| 2     | 16            |               |               | 16         |            |            |
| 3     | 21            |               |               | 21         |            |            |
| 4     | 451a          |               |               | 223        |            |            |
| 5     | 486           |               |               | let-7i     |            |            |
| 6     | 1228*         |               |               | 127        |            |            |
| 7     | HY4           |               |               | 320a       |            |            |
| 8     | NEG           |               |               | NEG        |            |            |

2 samples per plate (**3 rep**)



##注意/问题：

1. 血浆外其他组分QC时miR的引物设计是按照说明书要求通过5'加G/C，3’减(G/C)碱基使单引物靠近65度的。
2. 以上miRNA引物序列里若出现U说明为原始序列，尚未设计引物
3. PBMC仅提取后测RNA含量。唾液由于没有繁琐的分离程序，QC同样仅提取后测RNA含量。
4. 目前至少共有4个miRNA需要合成引物，统计如下；已经完成合成

| name          | Primer                    | Tm   | Length |
| ------------- | ------------------------- | ---- | ------ |
| mir-223(-3p)  | CGCTGTCAGTTTGTCAAATACCCCA | 63.7 | 25     |
| let-7i(-5p)   | GCGTGAGGTAGTAGTTTGTGCTGTT | 63.5 | 25     |
| mir-127(-3p)  | TCGGATCCGTCTGAGCTTGGC     | 64.5 | 21     |
| mir-320a(-3p) | AAAAGCTGGGTTGAGAGGGCGA    | 64.5 | 22     |

