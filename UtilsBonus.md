# Utilitários avançados de Texto

## tr
- troca caracteres entre dois conjuntos
~~~
$  cat   DNA.fasta   |   tr   [T]   [U]   >   RNA.fasta
$  tr   A-Z   a-z   <   DNA.fasta
$  cat   ZIP_CODES.txt   |   tr   -d   \"   >  new_ZIP_CODES.txt
~~~

## cut
- corta campos da entrada
~~~
$  cut  -d','  -f2  lista_SNPs_leucemia.csv
~~~

## rev
- reverte a ordem dos caracteres de cada linha
~~~
$  rev  teste.txt
~~~

## sed
- "Stream EDitor" ou editor de fluxo, editor não interativo
~~~
$  sed [opções] regras [arquivo]
$  sed  -e  's/\*//'  pasa.fas
$  echo  blablabla   |  sed  -e  's/b/p/'
~~~
Indicação de tutorial em português: http://aurelio.net/sed/livro/

## awk
- linguagem processamento de texto e busca de padrões
~~~
$  awk   -F   ":"   '{print $1}'   pasa.fas
$  head nodes.txt | awk  '{print $4  "\t"  $5 "\t"  $1}'
~~~

