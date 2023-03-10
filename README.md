Teste Técnico - Estagio Analise e Desenvolvimento

Repositorio destinado ao teste técnico para Estagio em Analise e Desenvolvimento.


# 🚀 Começando


- **[Question1](#-question-1)** - Lógica de Programação (Estrutura de Repetição)
- **[Question2](#-question-2)** - Programação / Sequência de Fibonacci
- **[Question3](#-question-3)** - Sequências Lógicas
- **[Question4](#-question-4)** - Lógica
- **[Question5](#-question-5)** - Programação / String invertida

📋 Question 1
------------

```c
int INDICE = 13, SOMA = 0, K = 0;

enquanto K < INDICE faça

{

K = K + 1;

SOMA = SOMA + K;

}

imprimir(SOMA);



//Ao final do processamento, qual será o valor da variável SOMA?

```
```bash
#Output
91

```
Resolution
------------
O valor da variável SOMA será a soma dos números inteiros de 1 a 13, que é 91. O laço `while` executará 13 vezes e a cada iteração somará um novo número à variável SOMA, começando com 1 e terminando em 13.

Abaixo segue mesmo codigo, porém em C#.

```c#

using System;

class Program
{
    static void Main(string[] args)
    {
        int INDICE = 13, SOMA = 0, K = 0;

        while (K < INDICE)
        {
            K = K + 1;
            SOMA = SOMA + K;
        }

        Console.WriteLine(SOMA);
    }
}

```

📋 Question 2
------------

Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...), escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.

Resolution
------------
```c#
using System;

class Program
{
    static void Main(string[] args)
    {
        //Solicita um numero inteiro
        Console.Write("Digite um número inteiro: ");
        int numero = int.Parse(Console.ReadLine());
        
        //Criando os primeiros elementos da sequência.
        int a = 0, b = 1;
        
        //Loop utilizando desestruturação de tupla para atualizar os valores de a e b da sequência.
        while (b < numero)
            (a, b) = (b, a + b);
        //Imprime no console se o numero {0} percente ou não pertence {1} a sequencia.
        Console.WriteLine("{0} {1} à sequência de Fibonacci.", numero, b == numero ? "pertence" : "não pertence");
    }
}

```
Exemplo:

```bash
#input
34
```

```bash
#output
34 pertence à sequência de Fibonacci.
```

📋 Question 3
------------
Descubra a lógica e complete o próximo elemento:

I) 1, 3, 5, 7, ___

II) 2, 4, 8, 16, 32, 64, ____

III) 0, 1, 4, 9, 16, 25, 36, ____

IV) 4, 16, 36, 64, ____

V) 1, 1, 2, 3, 5, 8, ____

VI) 2,10, 12, 16, 17, 18, 19, ____

Resolution
------------

I) 1, 3, 5, 7, `9` - A lógica é adicionar 2 a cada elemento.

II) 2, 4, 8, 16, 32, 64, `128` - A lógica é multiplicar por 2 a cada elemento. 

III)  0, 1, 4, 9, 16, 25, 36, `49` - A lógica é elevar o índice do elemento ao quadrado. 

IV) 4, 16, 36, 64, `100` - A lógica é elevar o índice do elemento ao quadrado e depois multiplicar por 4. 

V) 1, 1, 2, 3, 5, 8, `13` - A lógica é somar os dois elementos anteriores, sequencia de Fibonacci.

VI) 2, 10, 12, 16, 17, 18, 19, `200` - A lógica é que todos os numeros da sequencia escritos por extenso começam com a letra "D"


📋 Question 4
------------

Dois veículos (um carro e um caminhão) saem respectivamente de cidades opostas pela mesma rodovia. O carro de Ribeirão Preto em direção a Franca, a uma velocidade constante de 110 km/h e o caminhão de Franca em direção a Ribeirão Preto a uma velocidade constante de 80 km/h. Quando eles se cruzarem na rodovia, qual estará mais próximo a cidade de Ribeirão Preto?

Resolution
------------

Os dois veiculos estarão a uma mesma distância da cidade de Ribeirão Preto. Independente do tempo ou velocidade deles, ao se cruzarem estarão a uma mesma distância da cidade.

📋 Question 5
------------

Escreva um programa que inverta os caracteres de um string. Evite usar funções prontas, como, por exemplo, reverse;

Resolution
------------

```c#
using System;

class Program {
    static void Main(string[] args) {
       
        Console.Write("Digite uma string: ");
        string str = Console.ReadLine();
        Console.WriteLine("String original: " + str);
        
        // Método "ToCharArray()" para converter a string em um array de caracteres chars.
        char[] chars = str.ToCharArray();
        
        //Criando as variaveis start e end, para definir o inicio e o fim da string.
        int start = 0;
        int end = chars.Length - 1;
        
        //Loop while para inverter os caracteres da string. Trocando o primeiro caractere com o último, o segundo com o penúltimo, e assim por diante.
        while (start < end) {
            char temp = chars[start];
            chars[start] = chars[end];
            chars[end] = temp;
            start++;
            end--;
        }
        
        //Criando a variavel reversedStr que será nossa nova string invertida.
        string reversedStr = new string(chars);
        Console.WriteLine("String invertida: " + reversedStr);
    }
}
```
Exemplo:

```bash
#input
Felipe
```

```bash
#output
String original: Felipe
String invertida: epileF
```
