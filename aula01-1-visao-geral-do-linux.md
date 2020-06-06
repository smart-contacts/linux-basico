---
title: Curso de Linux - Aula 01 - Visão Geral do Linux
description: Curso básico de Linux (Módulo I) divido em uma série de posts
date: 2020-05-18 15:04:47
image: assets/img/linux.jpg
category: Linux
background: "#FF942A"
---

## Videoaula no Youtube

<iframe width="1280" height="720" src="https://www.youtube.com/embed/BiU0W38puqA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## O GNU/Linux

![GNU/Linux](../src/images/tux.png)

Linux é um termo popularmente empregado para se referir a sistemas operacionais que utilizam o Kernel Linux. O kernel (ou núcleo) foi desenvolvido pelo programador finlandês Linus Torvalds, inspirado no sistema Minix. O seu código fonte está disponível sob a licença GPL para que qualquer pessoa o possa utilizar, estudar, modificar e distribuir livremente de acordo com os termos da licença.

As licenças de software livre podem ser divididas, de modo geral, em dois grupos: licenças de documentação e licenças de software. A licença GNU GPL é uma das mais conhecidas, e talvez uma das mais utilizadas como licença de software. A licença GPL foi criada para garantir que cópias de softwares livres possam ser distribuídas, alteradas ou utilizadas por novos programas. Um outro exemplo de licença é a GNU FDL, que segue a mesma linha da GPL, mas utilizada para a documentação. Existem muitas outras licenças, e o escopo destas pode variar muito.

Se você deseja conhecer mais detalhes sobre as licenças, sobre software livre ou sobre a Fundação do Software Livre, verifique o site [GNU](http://www.gnu.org).

### Fontes de software do Linux

![Estrutura básica](../src/images/shell.jpg)

O Linux possui várias características que o diferenciam dos outros sistemas operacionais e que o aproximam do Unix, sendo um dos motivos da sua escolha em várias aplicações nas quais são necessárias estabilidade e segurança (vide as soluções de Cloud Computing dos principais players, praticamente todas implementadas sobre sistemas Linux).

Kernel: é o núcleo do sistema operacional, a parte mais próxima do nível do hardware. Composta de chamadas ao sistema, de acesso aos dispositivos de entrada e saída, e de gerência dos recursos da máquina (cpu, memória, etc).

Shell: nome genérico de uma classe de programas que funcionam como interpretador de comandos e de linguagem de programação script no Unix. Os shells mais populares são: bash, csh, tcsh, ksh e zsh.

Em uma distribuição qualquer, seja Ubuntu, Debian, Red Hat, CentOS, etc, temos vários outros "pacotes" (programas) além do kernel, quem vêm de diferentes fontes, sendo as principais:

- Free Software Foundation e seus contribuidores;
- X Consortium: criou o sistema gráfico de janelas também conhecido como X Window;
- Universidade da Califórnia, em Berkeley (BSD Unix), e seus contribuidores.

### Principais recursos do Linux

O Linux oferece diversas vantagens para quem o utiliza, entre elas:

- Sistema de multitarefa e multiusuário
- Sistema gráfico X Window
- Suporte a inúmeras linguagens de programação
- Suporte a protocolos de rede (principalmente TCP/IP)
- Código-fonte do kernel
- Centenas de programas em GPL
- Permissão de arquivos
- Estabilidade
- etc...

### Estrutura básica de diretórios

O Linux, assim como qualquer outro sistema operacional, possui uma estrutura de diretórios padrão criada na instalação. Abaixo temos um esquema com uma representação da estrutura de diretórios do Linux.

![Diretórios](../src/images/diretorios.jpg)

#### /

Raiz da estrutura de diretórios. Os demais diretórios estão abaixo dele.

#### /bin

Comandos essenciais do sistema.

#### /home

Contém os diretórios pessoais dos usuários.

#### /proc

Diretório virtual mantido pelo kernel de extrema utilidade. Nele encontramos “arquivos” com a configuração atual do sistema, dados estatísticos, dispositivos já montados, interrupções, informações de processos, endereços e estados das portas físicas, dados sobre as redes, etc.

#### /boot

Kernel do sistema, arquivos estáticos do boot de inicialização (boot loader), contém tudo que é necessário para carregar o sistema.

#### /usr

Contém maior parte de seus programas.

/usr/lib - bibliotecas compartilhadas.

/usr/src - código-fonte.

/usr/bin - comandos não essenciais do sistema.

#### /dev

Arquivos de dispositivos de hardware.

#### /etc

Arquivos de configuração do sistema.

/etc/X11 - configuração do X Window System.

/etc/rc.d - scripts de inicialização do sistema.

#### /lib

Bibliotecas compartilhadas pelos programas do sistema e módulos do kernel.

#### /media 

Ponto de montagem temporária de sistemas de arquivos (discos removíveis, pendrives, etc).

#### /sbin 

Comandos essenciais de adminstração do sistema.

#### /tmp 

Arquivos temporários.

#### /root

Diretório local do superusuário (root).

#### /var 

Contém arquivos de alta rotatividade, como spool (utilizado no serviços de impressão, correio eletrônico, etc), logs, páginas de manual formatadas, etc.

/var/cache - cache de dados das aplicações.

/var/lock - arquivos de travamento.

/var/log - arquivos de log.

/var/run - dados variáveis run-time.

/var/tmp - arquivos temporários.

#### /opt

Pacote de softwares opcionais.


Se você tiver algo mais que possa agregar ao exposto, deixe seu comentário, será muito bem vindo!

Obrigado pela leitura.

### Links úteis:

[Canal no YouTube](https://www.youtube.com/channel/UCC6ue986efLUHRuqGiIfuwQ/featured?view_as=public)

[Instagram](https://www.instagram.com/smartcontacts/)

[Twitter](https://twitter.com/@ContactsSmart)

[GNU](http://www.gnu.org)

[Linux Ubuntu](https://ubuntu.com/)
