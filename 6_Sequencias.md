# 6. Sequências

Sequências são estruturas de dados que possuem algumas propriedades em comum. Essencialmente, elas são ordenadas e podem ser indexadas. 

A função `range()` vista anteriormente é na verdade uma sequência. Falaremos agora de outras das principais sequências em Python.
<br>

## Listas

Listas são sequências de valores, que chamamos de itens. Esses itens são geralmente do mesmo tipo. 
<br>

**Declaração**  
A declaração é feita com o uso de colchetes, separando os itens por vírgulas.

```python
lista = []
```
```python
lista = [1, 2, 3]
```
<br>

**Indexação**  
É possível acessar os valores individualmente através da indexação.

```python
lista[1]
```
O índice pode também ser negativo, acessando a lista a partir do fim.
```python
lista[-1]
```
<br>

**Fatiamento**  
O fatiamento retorna uma sublista a partir do intervalo definido.

```python
lista[inicio:fim]   
```
```python
lista[inicio:fim:incremento]   
```
```python
lista[inicio:]   
```
```python
lista[:fim]   
```
```python
lista[::incremento]   
```
<br>

**Mutabilidade**  
A lista é uma sequência *mutável*, o que significa que podemos alterar itens seus individualmente:

```python
lista[1] = 0
```
Além da alterar um item, podemos também removê-lo. 
```python    
del lista[1]         
```
<br>

**Concatenação**  
Permite a união de duas listas.

```python
[1, 2] + [3, 4]
```
<br>

**Aninhamento**  
É possível também gerar uma lista de listas, o que é o equivalente a uma matriz em Python.

```python
matriz = [
    [1, 2],
    [3, 4]
]
```
<br>

**Cópia**  
Um detalhe importante sobre o funcionamento de listas é que, ao copiarmos uma lista, na realidade estamos fazendo uma referência para a lista original. Assim, se alterarmos a lista original, alteramos também a cópia.

<br>


**Métodos**  
Listas suportam também operações especiais que chamamos de *métodos*. Para usar um método, usamos o nome da nossa lista seguido do método e seus parâmetros. 

Abaixo temos uma lista de alguns dos métodos de listas:

| Método | Resultado |
| ------ | --------- |
| .index(item) | Retorna o índice de um item. |
| .append(item) | Insere um item do final da lista. |
| .insert(pos, item) | Insere um item na posição indicada. |
| .append(seq) | Insere os item da sequência do fim da lista. |
| .remove(item) | Remove a primeira ocorrência do item. |
| .pop(pos) | Retorna e remove um item da lista. |
| .copy() | Retorna uma cópia da lista |
| .sort() | Ordena a lista. |
| .reverse() | Inverte a ordem dos itens. |
| .count(item) | Retorna o número de ocorrências de um item. |
<br>

**Iteração**  
Como toda sequência, listas podem ser iteradas com o uso de `for`. 

```python
for item in lista
```
No exemplo, a variável `item` assumirá o valor de um novo item da lista a cada iteração.
<br>
Podemos também usar a função `enumerate()` para obter simultâneamente os índices e valores dos itens quando necessário.
```python
for item, valor in enumerate(lista) 
```

Outras funções incluem, por exemplo, a iteração em ordem reversa.
```python
for item in reversed(lista)
```
<br>

**Pertencimento**  
Python possui um operador exlusivo para verificar a existência de um item em listas (e outras estruturas) sem necessidade do uso de iteração.

```python
2 in [0, 1, 2, 3]
```
É possível também usar o operador `in` negado.
```python
4 not in [0, 1, 2, 3]
```
<br>

## Tuplas

Tuplas são sequências similares a listas, com a principal diferença que seus itens não podem ser alterados individualmente. Por isso, dizemos que são sequências *imutáveis*. 
<br>

**Declaração**  
A declaração de tuplas é feita com o uso de parênteses.

```python
tupla = ()
```
```python
tupla = (1,)
```
```python
tupla = (1, 2, 3)
```
```python
tupla = 1, 2, 3
```
<br>

**Operações**  
Tuplas suportam a maioria das operações de listas, como indexação, fatiamento, concatenação, aninhamento, iteração e pertencimento.
<br>


**Métodos**  
Ao contrário das listas, as tuplas não suportam métodos.

As tuplas são úteis quando precisamos que uma sequência  não seja alterada. Por não possuem as mesmas limitações em relação a cópia, são uteis também na passagem de sequências como parâmetros de funções, como veremos mais adiante.
<br>

## Strings

Vimos anteriormente que strings são um tipo de dado que representa texto, mas strings são também tratadas como sequências de caracteres. Em Python, não existe diferença de um caractere para uma string.

Assim como as tuplas, strings são sequências *imutáveis*.
<br>

**Operações**  
Strings suportam a maioria das operações das demais sequências, como indexação, fatiamento, concatenação e iteração.
<br>

**Métodos**  
Abaixo temos uma lista de alguns dos métodos de strings:

| Método | Resultado |
| ------ | --------- |
| .upper() | Retorna cópia da str em maiúsculas |
| .lower() | Retorna cópia da str em minúsculas |
| .capitalize() | Retorna cópia da str com a primeira letra maiúscula |
| .title() | Retorna cópia com cada palavra iniciando em maiúscula |
| .isalpha() | Retorna True se a str é composta de letras |
| .isdigit() | Retorna True se a str é composta de números|
| .isalnum() | Retorna True se a str é composta de letras e números |
| .islower() | Retorna True se a str é minúscula |
| .isupper() | Retorna True se a str é maiúscula |
| .find(sub) | Retorna o número de ocorrências da substring |
| .count(sub) | Retorna o índice da substring |
| .replace(old, new) | Retorna cópia da string com os termos antigos substituidos pelos novos |
| .strip(char) | Remove caracteres no início/fim da str (' ' por padrão) |
| .startswith(sub) | Compara o início da string, retorna True/False |
| .endswith(sub) | Compara o final da string |
| .split() | Retorna lista com palavras convertidas em itens |
| 'd'.join(lista) | Retorna str com itens separados pelo delimitador |
<br>

**Strings multilinha**  
São delimitadas por três aspas, e permitem que strings possuam diversas linhas. Regras de indentação são ignoradas no interior das strings multilinha.

```python
print("""Olá,

este é um exemplo de strings multilinha.

- Grupy-Lavras

""")
```
<br>

**Formatação de strings**  

É um recurso que permite criar formatos customizados para strings, além de strings compostas usando variáveis, que são úteis quando seu conteúdo é dinâmico.

Para isso usamos marcadores `{}` e o método `.format()`.

Daremos exemplos de alguns dos usos comuns, mas um estudo detalhado do assunto está fora do escopo deste curso (a sintaxe de formatação é extensa e considerada uma *mini-linguagem*)

```python
# uso de marcadores
'{} passo depois do {}'.format('um', 'outro')
```
```python
# uso de marcadores com índices
'{1} passo depois do {0}'.format('um', 'outro')
```
```python
# preenchimento de números com zeros
'{:03d}'.format(1)
```
```python
# formatação de casas decimais
'{:.2f}'.format(3.141592653589)
```

Quando usamos valores numéricos como parâmetros, eles são automaticamente convertidos em strings.

Na versão 3.6 foi incluída uma nova sintaxe de formatação, conhecida como f-strings. Alguns exemplos de sintaxe das de f-strings:

```python
# uso de marcadores
f'O valor é {valor}'
```

```python
# formatação numérica
f'O resultado é {valor:{largura}.{precisao}}'
```

<br>

# *Bônus:* Arquivos

Arquivos de texto são tratados de forma similar as estruturas já vistas, com a diferença que precisam ser corretamente abertos e fechados. 

**Inicialização**

Um arquivo é aberto com a função `open()`, que pode receber alguns parâmetros adicionais e retorna uma estrutura do tipo arquivo. Por exemplo:

```python
arquivo = open('nome_do_arquivo.txt')
# ...
arquivo.close()
```

Uma forma alternativa recomendada:

```python
with open('nome_do_arquivo.txt') as arquivo:
	# ...
```

Por padrão, `open()` abre um arquivo de texto para leitura. Parâmetros opcionais não serão cobertos no curso, mas podem ser facilmente verificados na documentação. 

**Métodos**

Alguns dos métodos mais usados são:

| Método | Resultado |
| ------ | --------- |
| .read() | Retorna todo o conteúdo do arquivo em uma única string |
| .readline() | Lê uma linha do arquivo e retorna string |
| .readlines() | Lê todo o conteúdo do arquivo e retorna lista de strings |
| .write(str) | Escreve uma string em um arquivo aberto para escrita |

[Atividade](./7_Atividade.md)