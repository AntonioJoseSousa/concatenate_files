# concatenate_files

Script para fazer download e unir arquivos .FASTA
O Script irá fazer download de 22 arquivos.fa.gz(cromossomos), colocar em ordem numerica e por fim ira concatenar todos os arquivos de forma ordenada em um arquivo final o hg38.fa

#criação de um novo diretorio/Pasta

'''mkdir referencia'''

#criação de um arquivo de download da referencia

'seq 1 22 | awk '{print("wget -c https://hgdownload.soe.ucsc.edu/goldenPath/hg38/chromosomes/chr"$1".fa.gz")}' > pegar-fa.txt'

#execução do arquivo para o download da reference 

'sh pegar-fa.txt'

#vizualizar os arquivos baixados

'ls'

output 

chr10.fa.gz  chr12.fa.gz  chr14.fa.gz  chr16.fa.gz  chr18.fa.gz  chr1.fa.gz   chr21.fa.gz  chr2.fa.gz  chr4.fa.gz  chr6.fa.gz  chr8.fa.gz
chr11.fa.gz  chr13.fa.gz  chr15.fa.gz  chr17.fa.gz  chr19.fa.gz  chr20.fa.gz  chr22.fa.gz  chr3.fa.gz  chr5.fa.gz  chr7.fa.gz  chr9.fa.gz

#concatenar todos os arquivos baixados, em ordem numérica e salvar em um unico arquivo e por fim salvar na pasta reference

'/workspace/comandos-linux (main) $ ls -1 *.fa.gz | sort -V | xargs zcat > hg38.fa | mv /workspace/comandos-linux/hg38.fa /workspace/comandos-linux/reference'

#Verificar a ordem

'/reference (main) $ grep ">" hg38.fa'

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
