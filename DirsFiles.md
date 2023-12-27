# Estrutura de arquivos e diretórios

## A origem de tudo:   /

~~~
/
├── bin
├── boot
├── cdrom
├── dev
├── etc
├── home    <---------  pastas dos usuários
├── lib
├── lib64
├── lost+found
├── media   <---------  montagem de dispositivos USB
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin
├── srv
├── sys
├── tmp		<---------  arquivos temporários
├── usr
└── var

21 directories
~~~


## Tipos de arquivos

O GNU/Linux reúne tudo em quatro tipos básicos de arquivos:

- Comuns - aqueles manipulados na parte do tempo, contendo texto, código fonte em C, scripts shell, arquivos binários, etc.
- Diretórios - arquivos que contêm os nomes dos arquivos e subdiretórios, assim como os ponteiros para aqueles arquivos e subdiretórios.
- Links - (ponteiros) não são realmente arquivos; na verdade, são entradas de diretório que apontam para o mesmo endereço.
- Especiais - Todos os dispositivos físicos associados ao sistema Linux são representados no sistema de arquivos, e , na maioria das vezes, estão localizados no diretório /dev.
~~~
$  ls  -l
~~~

