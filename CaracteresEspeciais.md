# Caracteres especiais

## Caracteres especiais do Shell ( # ~ ' > \ $ < | " & ...)

 ``#``  –  comentário 
 
 ``$``  –  variável  (ex.: $PATH)
 
 ``~``  –  /home/usuario 
 
 ``&``  –  envia processo para o "background"
 
 ``;``   –  separação de comandos
 
 ``|``   –  "pipe": concatenação de comandos
 
 ``/``   –  separação de diretórios
 
 ``>`` , ``<``  , ``>>``  – redirecionamento
 
 ``\``   –  escape do caractere seguinte
 
   ``     $ ls Área\ de\ trabalho``


## Caracteres-curinga ( * , ? , [ ] , { } )

- Asterisco  *  – qualquer coisa de qualquer tamanho
~~~
$  ls  *.fasta
$  ls  DNA*
~~~

- Interrogação  ?  – qualquer UM caractere
~~~
$  ls  Sample?.txt
$  ls  DNA?.fasta
~~~

- Lista de caracteres [ padrão ] – faixa de caracteres
~~~
$  ls  Sample[0-3].txt
$  ls  Sample[^2].txt
~~~
\* [^2] indica qualquer caracter exceto o 2


