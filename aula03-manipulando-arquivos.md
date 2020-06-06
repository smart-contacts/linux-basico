<p align="center">
  <a href="https://smartcontacts.com.br/">
    <img alt="Smart Contacts" src="https://smartcontacts.com.br/assets/img/logo.png" width="200" />
  </a>
</p>
<h2 align="center">
Informação sobre tecnologia, dicas, tutoriais, mini-cursos e muito mais.
</h2>

## Videoaula no Youtube

[Link do Vídeo no Youtube](https://youtu.be/ECP0NSGec7M)

## Comandos para manipulação de arquivos

#### cat

Permite visualizar e concatenar arquivos. Sintaxe:

```
cat [opções] [diretório/arquivo] [diretório1/arquivo1]
```

opções:

n - Numera todas as linhas de saída.

#### tac

Mostra o conteúdo de um arquivo (como o cat) só que em ordem inversa. Sintaxe:

```
# tac [opções] [diretório/arquivo]
```

#### cp

Esse comando faz uma cópia exata de um arquivo para outro. Sintaxe:

```
# cp -[opções] <arquivo-origem> <arquivo-destino>
```

opções:

i - Caso o arquivo que será copiado já exista no local de destino, este solicita uma confirmação.

n - Não sobrescreve um arquivo existente (sobrepõe a opção -i anterior).

r - Cópia recursiva. Caso seja a cópia de um diretório, copiará, inclusive, o seu conteúdo.

#### rm

Apagar arquivos. Também pode ser usado para apagar diretórios e subdiretórios vazios ou que contenham
arquivos. Sintaxe:

```
# rm -[opções] [arquivo/diretório]
```

opções:

i - Pergunta antes de remover, esta é ativada por padrão.

f - Remove os arquivos sem perguntar.

r - Usado para remover arquivos em sub-diretórios. Esta opção também pode ser usada para remover sub-diretórios.

v - Mostra os arquivos na medida que são removidos.

> Nota: Devemos usar com atenção o comando **rm**, uma vez que os arquivos e diretórios que forem apagados,
não poderão ser mais recuperados (pelo menos de forma prática).

#### mv

Esse comando renomeia o arquivo ou move para outro diretório. Exemplos:

```
# mv ~/arquivo1.md ~/arquivo2.md
renomeia o arquivo1.md para arquivo2.md

# mv ~/arquivo1.md ~/linux/arquivo2.md
renomeia o arquivo1.md para arquivo2.md, movendo para o subdiretorio linux

# mv arquivo1.md ~/linux/docs/
moverá o arquivo arquivo1.md para o diretório ~/linux/docs/ (sem alterar o nome)
```

#### touch

Altera a data e a hora que um arquivo foi criado. Caso seja usado com nomes de arquivos que não existam,  criará esses arquivos vazios.

```
# touch -[opções] [arquivos]
```

opções:

t datahora - Muda a hora e a data para o **datahora** definidos. O formato é AAAAMMDDhhmm.

a - Muda somente a data e hora do acesso ao arquivo.

c - Não cria arquivos vazios, caso os arquivos não existam.

m - Muda somente a data e hora da modificação.

#### head

Mostra as dez primeiras linhas de um arquivo. A opção **-n** permite que seja indicada a quantidade de linhas a serem mostradas. Exemplo:

```
# head -n 2 leiame.txt
```

#### tail

Mostra as linhas finais de um arquivo texto. Por padrão ele mostra as dez últimas linhas.

```
# tail -n 20 teste.txt
```

#### nl

Mostra o número de linhas junto com o conteúdo de um arquivo. Sintaxe:

```
# nl teste.txt
```

#### more

Permite fazer a paginação de arquivos. O comando more pode ser usado para leitura de arquivos que ocupem mais de uma tela. Quando toda a tela é ocupada, o more efetua uma pausa e permite que você pressione Enter ou espaço para continuar avançando no arquivo sendo visualizado. Para sair do more pressione q.

```
# more teste.txt
```

#### less

Permite fazer a paginação de arquivos ou da entrada padrão. O comando less pode ser usado para leitura de arquivos que ocupem mais de uma tela. Quando toda a tela é ocupada, o less efetua uma pausa (semelhante ao more) e permite que você pressione Seta para Cima e Seta para Baixo ou PgUP/PgDown para fazer o rolamento da página. Para sair do less pressione q.

```
# less teste.txt
```

#### pipe: |

Envia a saída de um comando para a entrada do próximo comando para continuidade do processamento. Os dados enviados são processados pelo próximo comando que mostrará o resultado do processamento.

```
# cat arquivo1.md | less
```

#### operadores: >, >>

**>** - (new) redireciona a saída-padrão. Normalmente usa-se redirecionando para um arquivo, porém se o arquivo existir, seu conteúdo será substituído.

**>>** - (append) redireciona a saída-padrão. Normalmente usa-se redirecionando para um arquivo, porém se o arquivo existir, o conteúdo será mantido e a saída será acrescentada no final do arquivo.

```
# cat > texto.txt
Os caracteres digitados serão inseridos no arquivo texto.txt até que seja digitado CTRL+D, que significa EOF (end of file).

# cat texto.txt > texto01.txt
Redireciona o conteúdo do primeiro arquivo para o segundo, substituindo o conteúdo.

# cat texto.txt >> texto01.txt
Redireciona o conteúdo do primeiro arquivo para o segundo, acrescentando ao final.
```

#### ln

Cria links para arquivos e diretórios no sistema (cria hard link por padrão). O link é um mecanismo que faz referência a outro arquivo ou diretório em outra localização. Os links podem ser de 2 tipos:

Links Simbólicos: é um arquivo especial que contém um ponteiro que aponta para outro arquivo. Assume as permissões do arquivo original. Se o arquivo original for apagado, o link fica quebrado, deixando de funcionar.

Hard Links ou Links Físicos: São arquivos com nomes diferentes e possivelmente em diretórios diferentes. Possuem o mesmo conteúdo e as mesmas permissões do arquivo original. É como se um arquivo tivesse dois nomes. Se o arquivo original é apagado, o link permanece. Só podem ser criados para arquivos, e que estejam em um mesmo sistema de arquivos. Sintaxe:

```
ln [-s] <arquivo_origem> <link>

ln [--symbolic] <arquivo_origem> <link>
```

#### split

Comando utilizado para dividir um arquivo em n-arquivos. O padrão é dividir o arquivo a cada 1000 linhas. Para especificar uma quantidade de linhas diferente do padrão, passe o número como parâmetro na linha de comando. Sintaxe:

```
split [opção] arquivoentrada arquivosaida
```

Os arquivos menores gerados, são nomeados da seguinte forma: arquivosaidaaa arquivosaidaab arquivosaidaac, etc.

Exemplo:

```
# split -10 /tmp/teste.txt /tmp/saida.txt
```

#### tr

Comando utilizado para alterar conteúdo de arquivos texto, através de substituição, remoção de mais de uma ocorrência de uma palavra, etc. O comando tr não usa arquivos diretamente, sendo necessário receber como entrada, a saída de outro comando, através do pipe. Sintaxe:

```
tr -[opção] texto_de_busca [texto_de_troca]
```

opções:

d - Deleta as ocorrências do **texto_de_busca**.

s - Exclui as ocorrências repetidas do **texto_de_busca**.

Exemplos:

```
# cat /tmp/teste.txt | tr -d fim

# cat /tmp/teste.txt | tr a-z A-Z
```


Se você tiver algo mais que possa agregar ao exposto, deixe seu comentário, será muito bem vindo!

Obrigado pela leitura.


### Links úteis:

[Canal no YouTube](https://www.youtube.com/channel/UCC6ue986efLUHRuqGiIfuwQ/featured?view_as=public)

[Instagram](https://www.instagram.com/smartcontacts/)

[Twitter](https://twitter.com/@ContactsSmart)

[GNU](http://www.gnu.org)

[Linux Ubuntu](https://ubuntu.com/)
