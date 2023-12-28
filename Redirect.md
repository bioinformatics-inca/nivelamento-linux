# Redirecionamento de comandos

## desvio de saída

- redireciona saída padrão de um programa/comando/script para algum dispositivo ou arquivo
- um caractere ''maior'' (``>``) inicia ou sobrescreve um arquivo
- dois caracteres juntos (``>>``) adicionam o conteúdo ao arquivo (e inicia o arquivo quando não existe).
  
~~~
$ echo  ">gene W"  >  DNAw.fasta
$ echo "ATGTCAGCATGGATTGCGACTTAG"  >> DNAw.fasta
$ cat  DNA1.fasta  DNA2.fasta  DNA3.fasta >  multi_DNA.fasta
~~~
Cuidado: ele não avisa ao sobrescrever um arquivo existente!

## desvio de entrada

- o comando à esquerda recebe o arquivo indicado de entrada

~~~
$  tr  [T]  [U]  <  DNA.fasta
~~~


# Concatenação de comandos

- Para executar comandos individuais em sequência, use o caractere de ''ponto e vírgula'' (``;``)
~~~
$  comando 1; comando 2; comando 3
$  date; echo; sleep 5 ;  echo; date; echo Dormi
~~~

# Conexão de comandos

##  "pipe" - conexão de comandos 
- envia a saída padrão para o comando seguinte
~~~
$  cat  multi_DNA.fasta  |  grep  gene
$  ls   |  grep  DNA
$  head -50 Sample1.txt | tail -4
$  cat  teste.txt  |  sort  |  uniq  -c 
$  sort  teste.txt  |  uniq  -c  |  sort   > lista_contagem.txt
$  ls   /etc  |  more
~~~


# misturando tudo
~~~
$  sort  teste.txt  |  uniq    >   teste.sorted 
$  cat  genes.list | sort -u  > genes.sorted
$  cat  *.sorted  |  sort  | uniq -c | grep " 2 "  
~~~


