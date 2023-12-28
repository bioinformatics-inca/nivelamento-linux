# Utilitários de Texto

## less  /  more
- Faz a paginação de saídas exibindo uma tela por vez.
- Para sair do aplicativo digite q (quit)
- Digite h para ver a lista das teclas disponíveis para navegação
~~~
less  Sample1.txt
more  Sample2.txt
~~~

## head / tail
- exibe as primeiras / últimas 10 (default) linhas do arquivo
~~~
head  Sample3.txt
head  -3  Sample3.txt
tail  -6  Sample3.txt 
tail  DNA.fasta
~~~

## cat
- exibe o conteúdo de arquivos
- concatena arquivos exibindo o resultado na tela
~~~
cat  teste.txt
cat  nodes.txt
cat  DNAx.fasta
cat  DNAx.fasta  DNAY.fasta
~~~

  -- Pergunta aos universitários: o que acontece quando usamos os caracteres curinga? Quais variações podemos usar?
~~~
cat  DNA*.fasta
cat  DNA?.fasta
cat  DNA[0-9].fasta
~~~

## grep
- procura por linhas em um arquivo que contenham expressões que satisfaçam um determinado padrão de busca
~~~
grep  gene  dna.fas
grep  ">"  dna.fas
grep  -v  ">"  dna.fas
grep  hpcnode-[2-4]-0[3-6]  nodes.txt
~~~


## sort  
- ordena linhas em arquivos de texto
~~~
sort  teste.txt
~~~

## uniq 
- filtra linhas adjacentes coincidentes
~~~
uniq  teste.txt
~~~

## wc  
- mostra a quantidade de linhas, palavras e bytes
~~~
wc  teste.txt
~~~

## nl  
- Exibe o conteúdo de um arquivo enumerando as linhas
~~~
nl  teste.txt
~~~


## diff / comm
- compara o conteúdo de dois arquivos linha por linha
~~~
diff  genes.list  teste.txt
diff  -y  genes.list  teste.txt
~~~

## cmp 
- compara dois arquivos, byte por byte
~~~
cmp  genes.list  teste.txt
~~~

## comm 
- compara dois arquivos (ordenados) linha por linha
~~~
comm  genes.list  teste.txt
comm  -23  genes.list  teste.txt
~~~

## echo
- Repete um argumento no "standard output"
~~~
echo Ola mundo!
echo -e "Ola mundo \n"
echo --help 
~~~

- ATENÇÃO: caracteres especiais 
~~~
echo  ">gene1"
echo   \>gene1
echo  "\>gene1"
echo  $PATH
echo '$PATH'
~~~
\* variáveis do sistema

