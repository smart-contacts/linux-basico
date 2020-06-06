---
title: Curso de Linux - Aula 01 - Comandos básicos
description: Curso básico de Linux (Módulo I) divido em uma série de posts
date: 2020-05-18 20:00:00
image: assets/img/linux.jpg
category: Linux
background: "#FF942A"
---

## Videoaula no Youtube

<iframe width="1280" height="720" src="https://www.youtube.com/embed/BiU0W38puqA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Comandos básicos

#### clear

Limpa a tela e posiciona o cursor no canto superior esquerdo do vídeo.

```
# clear
```

#### date

Permite ver/modificar a Data e Hora do Sistema. Sintaxe:

```
# date MMDDHHMMYY
```

Onde:

MM – mês
DD – dia
HH – hora
MM – minuto
YY – ano

#### time

Mede o tempo gasto para executar um processo (programa).

Exemplos:

```
# time ls
# time date --help
```

#### uptime

Mostra o tempo de execução do sistema desde que o computador foi ligado. Sintaxe:

```
# uptime
```

#### df

Mostra o espaço livre/ocupado de cada partição. Sintaxe:

```
# df -h
```

Mostra as informações de forma mais amigável, utilizando as letras M para megabytes e G para gigabytes.

#### free

Mostra detalhes sobre a utilização da memória RAM do sistema. O free é uma interface ao arquivo **/proc/meminfo**. Sintaxe:

```
# free -[opções]
```

opções:

m - Mostra o resultado em Mbytes.
g - Mostra o resultado em Gbytes.
t - Mostra uma linha contendo o total.

#### dmesg

Mostra as mensagens de inicialização do kernel. São mostradas as mensagens da última inicialização do sistema.

Exemplo:

```
# dmesg | less
```

#### echo

Mostra mensagens. Esse comando é útil na construção de scripts para mostrar mensagens na tela para o usuário acompanhar sua execução. A opção -n pode ser usada para que não ocorra o salto de linha após a mensagem ser mostrada. Sintaxe:

```
# echo [mensagem]
```

#### uname

Retorna o nome e versão do kernel atual. Sintaxe:

```
# uname -[opções]
```

opções:

a - Mostra informações do sistema com maiores detalhes, como versão do kernel, nome, arquitetura da máquina, etc.
n - Retorna o nome da máquina.
r - Mostra a versão do kernel.

#### reboot

Reinicia o computador. Sintaxe:

```
# reboot
```

#### shutdown

Desliga/reinicia o computador imediatamente ou após determinado tempo (programável) de forma segura. Todos os usuários do sistema são avisados que o computador será desligado. Sintaxe:

```
# shutdown -[opções] [hora] [mensagem]
```

opções:

r - Reinicia o sistema.
c - Cancela a execução do shutdown. Você pode acrescentar uma mensagem avisando aos usuários sobre o fato.
h - Desliga o sistema.

Reinicia o sistema:

```
# shutdown -r now
```

Desliga o sistema em 10 minutos:

```
# shutdown -h 10
```

Desliga o sistema imediatamente:

```
# shutdown now
```

#### halt

Desliga o computador imediatamente

```
# halt
```

## Comandos de ajuda

#### man

Consulta os manuais do sistema. Utiliza-se o **man** precedendo o nome do comando a ser consultado.

Consultar o manual do comando **date**:

```
# man date
```

#### --help

Parâmetro para consultar as opções disponíveis para um comando.

Consultar as opções do comando **shutdown**:

```
# shutdown --help
```


Se você tiver algo mais que possa agregar ao exposto, deixe seu comentário, será muito bem vindo!

Obrigado pela leitura.


### Links úteis:

[Canal no YouTube](https://www.youtube.com/channel/UCC6ue986efLUHRuqGiIfuwQ/featured?view_as=public)

[Instagram](https://www.instagram.com/smartcontacts/)

[Twitter](https://twitter.com/@ContactsSmart)

[GNU](http://www.gnu.org)

[Linux Ubuntu](https://ubuntu.com/)
