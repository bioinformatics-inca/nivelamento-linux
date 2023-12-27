# Manipulação de arquivos e diretórios

- copiar (arquivos, diretórios)
~~~
cp  [opções] [origem] [destino]
cp  -i  DNA.fasta  dna.fas
cp  -i  dna.fas  /tmp
cp  -r  ~/Downloads/curso  /tmp
~~~

- mover
~~~
mv  [opções] [origem] [destino]
mv  -iv  dna.fas  ADN.fas
mv  -i  /tmp/dna.fas   .
~~~

- remover (!!!!! cuidado !!!!)
~~~
rm  [opções] [origem]
rm  -i  ADN.fas
~~~

- criar diretório
~~~
mkdir  Exemplos
~~~

- alterar diretórios
~~~
cp  -i  DNA.fasta  Exemplos/
ls  Exemplos
mv  -i  Exemplos  Novoexemplo  
rmdir   Novoexemplo
rm  -ir  Novoexemplo
~~~

