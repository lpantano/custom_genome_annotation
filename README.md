# custom_genome_annotation
some annotation that are not that standard but still useful

## qsignature hg38

```
awk '{print $1"\t"$2"\t"$2+1"\t"$3"\t"$4}' qsignature.vcf > qsignature.bed
CrossMap.py bed hg19ToHg38.over.chain.gz qsignature.bed qsignature.hg38.bed
awk '{print $1"\t"$2"\t"$4"\t"$5}' qsignature.hg38.bed > qsignature.hg38.txt
```
