一、软件安装
https://cloud.tencent.com/developer/article/2078559
二、数据下载
1.下载参考文件
#权重文件，组织、细胞特异LD分数,基线模型文件全在LDSC_SEG_annotation_geneset里
#下载SNP list和下载对应的LD分数文件 （EUR）
wget -r -np -nH --cut-dirs=5 -R "index.html*" https://ibg.colorado.edu/cdrom2021/Day06-nivard/GenomicSEM_practical/eur_w_ld_chr/
2.GWAS数据(clean)：自己准备
三、数据预处理Munge Data
01.ldsc_sumstats.sh
对 GWAS 汇总统计数据进行标准化处理，生成适合 LDSC 分析的.sumstats.gz 文件。
四、LDSC
02.ldsc.sh
这两个调换顺序变成trait1=("AD2015" ),trait2=("ST19").结果也是一样的，不影响分析
五、LDSC_SEG
001.generate_ldcts.R
目的是为了产生一个Multi_tissue_gene_expr.ldcts文件用于后续分析，此文件可以循环使用
002.LDSC_SEG.pbs对每个性状进行ldsc-seg分析
003.result_summary.R
