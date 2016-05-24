# custom_genome_annotation
some annotation that are not that standard but still useful

## qsignature hg38

```
awk '{print $1"\t"$2"\t"$2+1"\t"$3"\t"$4}' qsignature.vcf > qsignature.bed
CrossMap.py bed hg19ToHg38.over.chain.gz qsignature.bed qsignature.hg38.bed
awk '{print $1"\t"$2"\t"$4"\t"$5}' qsignature.hg38.bed > qsignature.hg38.txt
```

## acmg56

```
wget https://raw.githubusercontent.com/lpantano/chrom_map/master/chrom_map.py
python chrom_map.py --name GRCh37_ensembl2UCSC --input acmg56.bed --out acmg56.ucsc.bed
CrossMap.py bed ../qsignature/hg19ToHg38.over.chain.gz acmg56.ucsc.bed acmg56.ucsc.hg38.bed
python chrom_map.py --name GRCh37_ensembl2UCSC --rev --input acmg56.ucsc.hg38.bed --out acmg56.hg38.bed
```
