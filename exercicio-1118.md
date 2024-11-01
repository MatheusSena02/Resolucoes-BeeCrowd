# Várias Notas Com Validação

Escreva um programa para ler as notas da primeira e a segunda avaliação de um aluno. Calcule e imprima a média semestral. O programa só deverá aceitar notas válidas (uma nota válida deve pertencer ao intervalo [0,10]). Cada nota deve ser validada separadamente.

No final deve ser impressa a mensagem “novo calculo (1-sim 2-nao)”, solicitando ao usuário que informe um código (1 ou 2) indicando se ele deseja ou não executar o algoritmo novamente, (aceitar apenas os código 1 ou 2). Se for informado o código 1 deve ser repetida a execução de todo o programa para permitir um novo cálculo, caso contrário o programa deve ser encerrado.

**Entrada**

O arquivo de entrada contém vários valores reais, positivos ou negativos. Quando forem lidas duas notas válidas, deve ser lido um valor inteiro X . O programa deve parar quando o valor lido para este X for igual a 2.

**Saída**

Se uma nota inválida for lida, deve ser impressa a mensagem “nota invalida”. Quando duas notas válidas forem lidas, deve ser impressa a mensagem “media = ” seguido do valor do cálculo.

*Antes da leitura de X deve ser impressa a mensagem "novo calculo (1-sim 2-nao)" e esta mensagem deve ser apresentada novamente se o valor da entrada padrão para X for menor do que 1 ou maior do que 2, conforme o exemplo abaixo.*

**A média deve ser impressa com dois dígitos após o ponto decimal.**


# Resolução 
```
#include <stdio.h>

int main()
{
    double notas[2], media;
    int condicao = 0;
    char resposta = '1';
    while(resposta == '1')
    {
        scanf("%lf", &notas[0]);
        if(notas[0] < 0 || notas[0] > 10)
        {
            condicao = 1;
            while(condicao == 1)
            {
                printf("nota invalida\n");
                scanf("%lf", &notas[0]);
                if(notas[0] >= 0 && notas[0] <= 10)
                {
                    condicao = 0;
                }
            }
        }
        scanf("%lf", &notas[1]);
        if(notas[1] < 0 || notas[1] > 10)
        {
            condicao = 1;
            while(condicao == 1)
            {
                printf("nota invalida\n");
                scanf("%lf", &notas[1]);
                if(notas[1] >= 0 && notas[1] <= 10)
                {
                    condicao = 0;
                }
            }
        }
        media = (notas[0] + notas[1])/2;
        printf("media = %.2lf\n", media);
        printf("novo calculo (1-sim 2-nao)\n");
        scanf(" %c", &resposta);
        if(resposta == '1')
        {
            continue;
        }else if(resposta == '2')
        {
            break;
        }else if(resposta != '1' || resposta != '2')
        {
            condicao = 1;
            while(condicao == 1)
            {
                printf("novo calculo (1-sim 2-nao)\n");
                scanf(" %c", &resposta);
                if(resposta == '1' || resposta == '2')
                {
                    condicao = 0;
                }
            }
        }
        
    }
}
```
