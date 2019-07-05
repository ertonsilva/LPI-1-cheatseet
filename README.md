# LPI-1-cheatseet
Conteúdo para a prova LPI-1

## 103.1 (peso 4)

O principal meio de interação com um sistema linux é o terminal (shell), nele os comando são interpretados por um interpretador (bash, sh, csh, ksh) ou flavors, a diferença é bem sutil. 



**A LPI cobre o BASH**



A maneira mais básica de se interagir com um server linux é através do prompt de comando.

Possuimos 3 níveis de usuários, sendo eles:

*usuário comum*

*usuário comum com poderes de super usuário*

*usuário root*

É recomendado utilizar o *sudo* invés de *root* por questões de segurança, afinal, você não precisa se tornar o *root* para realizar uma edição de um arquivo protegido, utilize o *sudo* para isso.

A PS1 é o prompt, uma sequência de caracteres que indicam se um sistema esta pronto para receber os comandos.

A PS1 é a variável de ambiente (estudaresmos mais sobre variáveis de ambiente depois) que define o prompt no linux.

O primeiro comando é o "echo", ele é utilizado para imprimir informações na tela. O bash como toda linguagem de programação possui variáveis, uma das variaveis é a SHELL, printando ela, você consegue ver qual shell esta utilizando:

```bash
erton@vm-lpi:~$ echo $SHELL
/bin/bash
```

Os comandos podem ser classificados em 3 tipos:

*Comando inrerno*

​	É um comando embutido no shell

*Comando externo*

​	É um comando instalado no shell

*Script*

​	É uma sequência de comandos

Você pode verificar qual o tipo de um comando utilizando o *type*

Exemplo de comando embutido:

```bash
erton@vm-lpi:~$ type echo
echo is a shell builtin
```

Exemplo de comando externo:


```bash
erton@vm-lpi:~$ type clear
clear is /usr/bin/clear
```


Quando você utiliza muito um comando ele fica "hasheado" no cache pelo sistema, exemplo:


```bash
erton@vm-lpi:~$ type clear
clear is hashed (/usr/bin/clear)
```

Quando o programa é externo o bash precisa saber onde o comando está, para isso existe a variável "PATH", ela é uma variável de ambiente que guarda os caminhos:

```bash
erton@vm-lpi:~$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
```

Os diretórios são divididos por :

O shell verifica cada diretório procurando o comando solicitado, caso não exista no primeiro, ele procura no segundo e assim por diante.

Caso o programa não seja interno e não esteja no PATH você deve referenciar onde o programa está, você pode utilizar o *pwd* para verificar onde você está:

```bash
erton@vm-lpi:~/Downloads$ pwd
/home/erton/Downloads
```

Para entrar em algum diretório, você deve utilizar o *cd*

O ./ indica que o comando está no diretório onde você se encontra.

Existem dois tipos de caminhos no Linux:

*Caminho absoluto*

​	É um caminho que começa sempre com barra no início, seguindo a estrutura de diretórios do Linux

*Caminho relativo*

​	Existe o caminho relátivo ou parcial, onde você indica o caminho a partir de onde está.

### Váriaveis de ambiente

Os aspectos do shell são definidos e controlados a partir de diversas variáveis.

existem dois tipos de variáveis:
*Variavel local*

​	Disponíveis apenas no shell atual.

*Variavel exportada*

​	São variáveis do shell atual e se todos os sub-shell "filhos" do shell atual.

Você deve declarar uma variável local seguindo a seguinte sintaxe:

```bash
erton@vm-lpi:~$ teste=valor
erton@vm-lpi:~$ echo $teste
valor
```

Para que ela seja declarada globalmente você deve **exportar**:

```bash
erton@vm-lpi:~$ export $teste
```

Você pode também definir o valor da variável ja exportando ela:

```bash
erton@vm-lpi:~$ export teste=valor1
```

Exportando a variável, ela vai ser conhecida somente por processos originários daquele shell.

#### SET

O comando *set* deve ser utilizado quando você quiser ver as variáveis locais e globais




#### ENV

## 103.7 (2)

## 103.8 (3)
