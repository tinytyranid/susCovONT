# susCovONT

**Pipeline to generate consensus.fasta files and identify pangolin lineage and nextstrain clade of Sars-CoV-2 genomes from ONT sequencing.**


This pipeline takes as input a folder with name <run_name> which contains the folders `fast5_pass` and `fastq_pass` from Sars-CoV-2 ONT sequencing together with a CSV-file which links barcode and sample name, and it [outputs consensus.fasta files](https://artic.network/ncov-2019/ncov2019-bioinformatics-sop.html) along with `<run_name>_report.csv` which includes [pangolin lineage](https://cov-lineages.org/pangolin.html), [nextstrain clade, mutations](https://clades.nextstrain.org/) and [QC](https://github.com/marithetland/susCovONT/wiki/3.-QC-and-parameters). 


## Quick start

```
python ~/Programs/git/covid-genomics/SARSCoV2_pipeline.py --input_dir /path/to/<run_name> --sample_names sample_names.csv
```
Where:
* `--input_dir`: Input directory `<run_name>` must contain `fast5_pass` and `fastq_pass` folders, with the `<run_name>` corresponding to your run (e.g. 20210213_1359_X5_FAO88697_5cf6e6f0)
* `--sample_names`: A CSV-file which connects barcodes with sample names, following the format:
```
barcode,sample_name
NB01,NEGCONTROL
NB02,E1234567_P1
NB03,V2345678_P1
```

Note: Basecalling and demultiplexing may also be performed if not already done on GridION/MinIT.


## Please see the wiki for more information:
* [What does the pipeline do?](https://github.com/marithetland/covid-genomics/wiki/What-does-it-do%3F)
* [How to run](https://github.com/marithetland/covid-genomics/wiki/1.-How-to-run)
* [Installation](https://github.com/marithetland/covid-genomics/wiki/2.-Installation)
* [QC parameters and how to change these](https://github.com/marithetland/susCovONT/wiki/3.-QC-and-parameters)
* [What does the output look like](https://github.com/marithetland/covid-genomics/wiki/4.-Output)
* [How to run the commands manually](https://github.com/marithetland/covid-genomics/wiki/6.-Manual-run)

### And as an extra bonus:
* [Setting up MinKNOW and RAMPART](https://github.com/marithetland/covid-genomics/wiki/5.-MinKNOW-and-RAMPART)
* [Further exploration using the Nexctlade Web Application](https://github.com/marithetland/covid-genomics/wiki/Using-Nextclade-web-application)


## Note and thanks
Please note that this script is intended for the use at the AMR lab at Stavanger University Hospital, you may need to change it (sprecifically the `scripts/config.cfg` file) for it to work in your environment.

This pipeline uses scripts and pipelines from the [Artic network's nCoV-2019 novel coronavirus bioinformatics protocol] (https://artic.network/ncov-2019/ncov2019-bioinformatics-sop.html). See also the [Parameters](https://github.com/marithetland/covid-genomics/wiki/Parameters) page.

Many thanks to the artic, pangolin and nextclade developers for creating the protocols and pipelines!

## Repo name
This pipeline was created for the analysis of Sars-CoV-2 data from Oxford Nanopore Technologies (ONT) sequencing at Stavanger University Hospital (SUH/SUS). Hence the name, susCovONT: SUS + Covid-19 + ONT.
