# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
**a) A saída será undefined seguido de erro** 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

**R: A alternativa correta é a (a). Isto porque, var x é içado, porém, sem um valor inicial. Então, console.log(x) imprime undefined.
Entretanto, let y também é içado, mas fica na "Temporal Dead Zone" (TDZ); isto é: A Zona Morta Temporal, que é um período durante o qual uma variável declarada com let, var, ou const, não pode ser acessada antes de ser inicializada com um valor. Dessa forma, como console.log(y) tenta acessar y antes da inicialização, isto gera um ReferenceError.**

______
**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

**a) Substituir if (a || b === 0) por if (a === 0 || b === 0)**

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

**R: A resposta correta é a alternativa (a). O erro ocorre porque a || b === 0 não verifica corretamente se a ou b são = 0, devido à precedência dos operadores. Portanto, para garantir o funcionamento do código corretamente, basta fazer: a === 0 || b === 0.**

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

**b) O código imprime 200.**

c) O código imprime 50.

d) O código gera um erro.

**R: O código vai imprimir 200, pois, após o primeiro case ( case eletrônico ), não tem um "break". Dessa forma, a execução continua para case "vestuário", alterando o preço para 200. Assim, apenas quando encontra break ele sai do switch.**

______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

**d) 24**

**R: O código passa por três etapas principais: 1) Multiplicação por 2 (map) → Todos os números do array são dobrados:
[1, 2, 3, 4, 5] ---> [2, 4, 6, 8, 10]; 2) Filtragem (filter) → Mantém apenas os números maiores que 5:[2, 4, 6, 8, 10] ---> [6, 8, 10]; 3) Soma dos valores (reduce) → Soma os números que foram filtrados: 6 + 8 + 10 = 24. Portanto, a alternativa correta é a (d).**
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

**c) ["banana", "abacaxi", "manga", "laranja"]**

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

**R: O método splice modifica o array removendo e adicionando elementos. Dessa forma, o número 1 significa que a alteração começa na posição da "maçã".
Já o número 2, indica que dois elementos serão removidos ("maçã" e "uva"). Assim, os elementos "abacaxi" e "manga" são adicionados no lugar de maçã e uva. Portanto, a alternativa correta é a (c).**
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

**b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.**

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

**R: A alternativa correta é a (b), pois, a segunda afirmação não justifica a primeira, porque ela apenas indica como a herança é implementada, sem explicar o conceito mais amplo da palavra-chave.**
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

**a) I e II são verdadeiras.**

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

**R: O único tópico que está incorreto é o III. Isto porque, na linguagem JavaScript, a herança de classes é suportada através da palavra-chave "extends". Portanto, o código funciona, sim, corretamente.**

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

**b) A asserção é verdadeira e a razão é falsa.**

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

**R: A alternativa correta é a (b). Dado isso, na asserção, diz que o polimorfismo em POO permite que objetos de tipos diferentes respondam de formas distintas à mesma mensagem, o que é verdade. Porém, a razão está incorreta, pois, a sobrecarga de métodos não é suportada em JavaScript de forma nativa.**
______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```
**R: Os problemas contidos no código são:**
**- O método size não existe para arrays em JavaScript. Portanto, o correto é usar a propriedade length para obter o tamanho de um array.**
**- A variável "soma" não foi inicializada antes de ser usada no loop. Entretanto, o ideal é inicializar a soma com 0 antes de começar a somar os valores.**
**- Falta de acumulação da soma; dentro do loop, a linha soma = 2 * numeros[i]; substitui o valor de soma a cada iteração. O correto seria acumular o valor, ao invés de substituí-lo. Ou seja, deve-se somar o dobro de cada número ao valor acumulado.**

**Código corrigido:**

function somaArray(numeros) {
    // inicializando a variável soma com 0
    let soma = 0;

    // usando 'numeros.length' para obter o tamanho correto do array
    for (let i = 0; i < numeros.length; i++) {
        // Acumulando o dobro de cada número no array
        soma += 2 * numeros[i];
    }

    // retornando a soma final
    return soma;
}

// testando a função
console.log(somaArray([1, 2, 3, 4]));  // resultado esperado: 20
______

10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

**R: O que é herança no contexto de classes? A herança, nada mais é, do que algo que permite que uma classe herde propriedades e métodos de outra classe. Dessas forma, a classe Livro irá herdar as propriedades (nome e preço) da classe Produto e, ao mesmo tempo, poderá modificar métodos dessa classe, como o calcularDesconto(). Isto é feito utilizando o conceito de polimorfismo, onde a classe filha, neste caso, "Livro", redefine um método da classe pai (Produto) para, assim, comportar-se de maneira diferente. No entanto, o método calcularDesconto() na classe Livro foi sobrescrito para aplicar um desconto diferente de 20%, ao invés de 10%. Isto é feito da seguinte maneira: calcularDesconto() { return this.preco * 0.80; }.**


**Criando um exemplo:**

// classe Produto
class Produto {
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    // método que aplica um desconto fixo de 10%
    calcularDesconto() {
        return this.preco * 0.90;  // 10% de desconto
    }
}

// classe Livro que herda de Produto
class Livro extends Produto {
    constructor(nome, preco) {
        super(nome, preco);  // chama o construtor da classe pai (Produto)
    }

    // sobrescreve o método calcularDesconto para aplicar 20% de desconto
    calcularDesconto() {
        return this.preco * 0.80;  // 20% de desconto
    }
}

// criando instâncias de Produto e Livro
let produto1 = new Produto("Smartphone", 1000);
let livro1 = new Livro("JavaScript para Iniciantes", 50);

// testando os métodos
console.log(`Preço do Produto: R$ ${produto1.calcularDesconto()}`);  // Esperado: 900
console.log(`Preço do Livro: R$ ${livro1.calcularDesconto()}`);      // Esperado: 40

