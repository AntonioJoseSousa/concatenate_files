# concatenate_files

## Script para fazer download e unir arquivos .FASTA

Este script faz o download de 22 arquivos .fa.gz (cromossomos), os coloca em ordem numérica e, por fim, concatena todos os arquivos de forma ordenada em um arquivo final chamado `hg38.fa`.

### Passo 1: Criação de um novo diretório/pasta

```bash
mkdir referencia

### Passo 2: Criação de um arquivo de download da referência

seq 1 22 | awk '{print("wget -c https://hgdownload.soe.ucsc.edu/goldenPath/hg38/chromosomes/chr"$1".fa.gz")}' > pegar-fa.txt

### Passo 3: Execução do arquivo para o download da referência

sh pegar-fa.txt

### Passo 4: Visualizar os arquivos baixados

ls

output 

chr10.fa.gz  chr12.fa.gz  chr14.fa.gz  chr16.fa.gz  chr18.fa.gz  chr1.fa.gz   chr21.fa.gz  chr2.fa.gz  chr4.fa.gz  chr6.fa.gz  chr8.fa.gz
chr11.fa.gz  chr13.fa.gz  chr15.fa.gz  chr17.fa.gz  chr19.fa.gz  chr20.fa.gz  chr22.fa.gz  chr3.fa.gz  chr5.fa.gz  chr7.fa.gz  chr9.fa.gz


### Passo 5: Concatenar todos os arquivos baixados, em ordem numérica, salvar em um único arquivo e  Mover o arquivo final para a pasta "reference"

/workspace/comandos-linux (main) $ ls -1 *.fa.gz | sort -V | xargs zcat > hg38.fa | mv /workspace/comandos-linux/hg38.fa /workspace/comandos-linux/reference

### Passo 7: Verificar a ordem dos cromossomos no arquivo final

/reference (main) $ grep ">" hg38.fa

output

>chr1
>chr2
>chr3
>chr4
>chr5
>chr6
>chr7
>chr8
>chr9
>chr10
>chr11
>chr12
>chr13
>chr14
>chr15
>chr16
>chr17
>chr18
>chr19
>chr20
>chr21
>chr22
