# Fibonacci em Vetor
Faça um programa que leia um valor e apresente o número de Fibonacci correspondente a este valor lido. Lembre que os 2 primeiros elementos da série de Fibonacci são 0 e 1 e cada próximo termo é a soma dos 2 anteriores a ele. Todos os valores de Fibonacci calculados neste problema devem caber em um inteiro de 64 bits sem sinal.

**Entrada**

A primeira linha da entrada contém um inteiro T, indicando o número de casos de teste. Cada caso de teste contém um único inteiro N (0 ≤ N ≤ 60), correspondente ao N-esimo termo da série de Fibonacci.

**Saída**

Para cada caso de teste da entrada, imprima a mensagem "Fib(N) = X", onde X é o N-ésimo termo da série de Fibonacci.

# Resolução 

```
#include <stdio.h>

int main()
{
    int t, n;
    long long int fibonacci[60];
    fibonacci[0] = 0;
    fibonacci[1] = 1;
    for(int i = 2; i <= 60; i++)
    {
        fibonacci[i] = fibonacci[i - 1] + fibonacci[i - 2];
    }
    scanf("%d", &t);
    for(int a = 1; a <= t; a++)
    {
        scanf("%d", &n);
        printf("Fib(%d) = %lld\n", n, fibonacci[n]);
    }
}
```
