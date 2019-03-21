# 9. Funções

Uma função é um pequeno programa que realiza uma ação específica.

Uma das vantagens de se usar funções é manter o código organizado. A medida que nossos programas se tornam maiores, dividi-lo em partes menores é vital para o desenvolvimento e manutenção do código. 

Outra vantagem de se usar funções é que podemos escrevê-las uma única vez e usá-las sempre que necessário, inclusive em arquivos diferentes. Na verdade Python inclui uma variedade de funções e algumas delas já foram usadas até aqui.

Antes de aprender como criar nossas próprias funções, conheceremos melhor as funções disponíveis na linguagem.
<br>

## Funções embutidas (built-in)

São funções que fazem parte da linguagem e estão sempre disponíveis. 

Uma lista completa das funções embutidas na linguagem pode ser vista a seguir.

|               |             |              |            |                |
| ------------- | ----------- | ------------ | ---------- | -------------- |
| abs()         | dict()      | help()       | min()      | setatttr()     |
| all()         | dir()       | hex()        | next()     | slice()        |
| any()         | divmod()    | id()         | object()   | sorted()       |
| ascii()       | enumerate() | input()      | oct()      | staticmethod() |
| bin()         | eval()      | int()        | open()     | str()          |
| bool()        | exec()      | isinstance() | ord()      | sum()          |
| bytearray()   | filter()    | issubclass() | pow()      | super()        |
| bytes()       | float()     | iter()       | print()    | tuple()        |
| callable()    | format()    | len()        | property() | type()         |
| chr()         | frozenset() | list()       | range()    | vars()         |
| classmethod() | getattr()   | locals()     | repr()     | zip()          |
| compile()     | globals()   | map()        | reversed() | \__import__()  |
| complex()     | hasattr()   | max()        | round()    |                |
| delattr()     | hash()      | memoryview() | set()      |                |

(Uma referência de cada uma delas pode ser consultada em: https://docs.python.org/3/library/functions.html)

As funções embutidas possuem finalidades diversas. A função `abs()`, por exemplo, recebe um valor numérico e devolve seu valor absoluto. Já a função `len()` retorna o número de itens de uma sequência ou estrutura de dados.

Algumas dessas funções, como `dict()`, `list()`, `range()`, `set()`, `tuple()`, são na verdade *construtores*, retornando um objeto com o tipo desejado. 

A seguir veremos como definir nossas próprias funções.
<br>

## Definindo funções

Antes de usarmos uma função, precisamos defini-la. A definição contém o código que será executado na *chamada* da função. 

A definição da função é feita com a palavra-chave `def`, e o nome da função segue regras idênticas aos nomes de variável.

```
def ola():
    print('Olá!')
```
Para executarmos o código posteriormente, basta chamarmos pelo nome da função:

```
ola()
```
<br>

**Escopo**

Podemos ter dentro do *corpo* da função uma variável com nome igual a outra que esteja fora dela, sem que haja conflito, porque elas estão em escopos diferentes.

Esse isolamento é importante para que possamos utilizar uma função mesmo sem conhecer sua implementação, e principalmente sem inteferir no restante do programa.

<br>

**Parâmetros**

Para transmitir valores para nossa função, utilizamos a passagem de parâmetros. Parâmetros são especificados na definição da função, enquanto os valores propriamente ditos são passados quando a função é chamada.

```Python
# definição da função
def ola(nome):
    print('Olá, {}!'.format(nome))
```
```Python
# chamada da função
meu_nome = input('Qual seu nome? ')
ola(meu_nome)
```
Os valores passados na chamada da função podem simplesmente seguir a mesma ordem da definição dos parâmetros, ou podem fazer referência a eles explicitamente. Isso é útil quando temos diversos argumentos.

Além disso, é possível que um parâmetro tenha um valor padrão, podendo ser omitido na chamada da função.

```Python
# TODO: exemplo
```
Ao passar um valor como parâmetro estamos fazendo uma cópia desse valor dentro do escopo da função, sendo que o comportamente dessa cópia varia conforme seu tipo.
<br>

**Retornando valores**

Além de receber parâmetros, uma função pode também retornar um valor.

Toda função retorna um único valor. Na ausência de um `return`, Python retorna automaticamente o valor `None`.

```Python
# TODO: exemplo
```

Para retornar múltiplos valores, é necessário agrupá-los em uma estrutura de dados. O tipo ideal varia conforme a necessidade, embora existam estruturas específicas para essa situação, as *[named tuples](https://docs.python.org/3/library/collections.html#collections.namedtuple)*, parte do módulo *collections*. 

```Python
# TODO: exemplo
```
<br>

## Docstrings

Documentar o código é parte essencial do desenvolvimento de software. Python fornece uma forma conveniente de documentar funções, as **docstrings**.

Docstrings são strings multilinha comuns, que colocadas na primeira linha da definição de uma função são interpretadas como strings de documentação.

Uma documentação deve indicar o que o código faz, não como ele funciona.

Algumas convenções no uso de docstrings são discutidas na PEP 257, que pode ser encontrada em <https://www.python.org/dev/peps/pep-0257/>.

**Docstrings de uma única linha**

São usadas para funções cuja funcionadalida é clara:

```
# TODO: mudar exemplo

def double(x):
    """Return doubled x."""
    return x * 2
```

Mesmo tendo uma única linha, as três aspas são usadas.

A função deve ser descrita por ações: faz isso, retorna aquilo... 

A docstring deve ser terminada por um ponto. 

**Docstrings multilinha**

Usadas quando é necessária uma descrição mais elaborada:

```
#TODO: mudar exemplo

def vowel_count(word):
    """
    Count the number of vowels in a word.

    args:
        word: string under test

    returns:
        count: number of counted vowels
    """

    count = 0
    for c in word:
        if c in "AEIOUYaeiouy":
            count = count + 1
    return count
```

Aqui as aspas são mantidas em suas próprias linhas.

A primeira linha contém uma descrição em formato idêntico a docstring de uma linha, e é seguida por uma linha em branco.  

Uma descrição complementar pode ser adicionada se necessário, novamente seguida por uma linha em branco.  

Por último são descritos os argumentos e valores retornados.

Após fechar as aspas, deve-se deixar outra em branco. 

## Módulos

Além das funções embutidas na linguagem, Python é famosa pela sua vasta biblioteca de *módulos* com as mais diversas aplicações. 

Módulos são simplesmente arquivos de código que podem ser importados, permitindo que usemos funções definidas neles.

A *biblioteca padrão* é um conjunto de módulos distribuídos junto a linguagem. Uma relação completa dos módulos da biblioteca padrão pode ser vista em https://docs.python.org/3/library/.

**Importando módulos da biblioteca padrão**

Podemos importar um módulo ou apenas parte dele, conforme necessário:

```python
import math
```
```python
from math import sqrt
```
```python
import datetime as dt
```

Além disso, é possível instalar módulos de terceiros utilizando um gerenciador de pacotes como o **PIP**, ou ainda importar módulos que nós mesmos criamos anteriormente. 

**Importando módulos próprios**

Para importar um arquivo criado anteriormente, basta que ele esteja na mesma pasta do programa atual (ou interpretador). O nome do módulo é o mesmo do arquivo.

```python
import meu_modulo
```

<br>

## Função main()

Agora que já sabemos como encapsular código usando funções e como criar e importar módulos, precisamos controlar o comportamento dos nosso programas ao serem executados diretamente ou importados. 

Ao contrário de outras linguagens de programação, o uso de uma função `main()` é opcional em python, sendo usada apenas quando precisamos separar o código a ser executado numa chamada direta do restante, como a declaração de funções.

Para isso, basta declararmos a função `main()` com código que deve ser chamado na execução, e incluir a chamada da main em uma condicional conforme o exemplo:

```python
def minha_funcao():
    pass

def main():
	pass

if __name__ == '__main__':
    main()
```

Assim, o programa irá chamar a função main() quando executado diretamente, e ignorá-lo quando importado como módulo.

[Atividade](./10_Atividade.md)

