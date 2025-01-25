**1. Faça um programa que leia três valores e apresente como resultado a soma dos quadrados dos valores lidos.**

```
#include <stdio.h>

int main() {

int valor1, valor2,valor3, soma;

printf("Informe o valor 1 ");
scanf("%d", &valor1);

printf("Informe o valor 2 ");
scanf("%d", &valor2);

printf("Informe o valor 3 ");
scanf("%d", &valor3);

soma = (valor1 * valor1) + (valor2 * valor2) + (valor3 * valor3);
printf("A soma dos quadrados é %d\n", soma);

}
```

**2. Leia quatro notas, calcule a média aritmética e imprima o resultado**

```
#include <stdio.h>

int main() {

float valor1, valor2, valor3, valor4, media;

printf("Informe a nota 1 ");
scanf("%f", &valor1);

printf("Informe o nota 2 ");
scanf("%f", &valor2);

printf("Informe o nota 3 ");
scanf("%f", &valor3);

printf("Informe a nota 4 ");
scanf("%f", &valor4);

media = valor1 + valor2 + valor3 + valor4 / 4;
printf("A media das suas notas é: %.2f\n", media);

}
```

**O que é o %.2f?**
O `%.2f` é uma especificação de formatação usada em C para exibir números do tipo ponto flutuante (float ou double) com um número fixo de casas decimais. Ele é usado principalmente dentro da função `printf` para controlar como o número será mostrado ao usuário.

No formato `%.2f`, o símbolo `%` indica que um formato será aplicado. O `.2` especifica que o número deve ter exatamente **duas casas decimais** após o ponto. Já o `f` indica que o valor formatado é do tipo ponto flutuante.

Por exemplo, se você tiver um número como `3.14159` e usá-lo com o formato `%.2f`, o número será exibido como `3.14`, com o valor sendo automaticamente arredondado para manter duas casas decimais.

Esse recurso é muito útil em situações onde é necessário apresentar valores com uma precisão específica, como em cálculos financeiros, resultados científicos ou qualquer contexto que exija clareza e simplicidade na exibição de números. Ele também ajuda a evitar números excessivamente longos e difíceis de ler.

**3. Três amigos jogaram na loteria. Caso eles ganhem, o prêmio deve ser repartido proporcionalmente ao valor que cada um deu para a realização da aposta. Faça um programa que leia quanto cada apostador apostou, o valor do prêmio e imprima quanto cada um ganharia do prêmio com base no valor investido**

```
#include <stdio.h>

int main() {

float aposta1, aposta2, aposta3, total_apostas;
float premio;
float porcentagem1, porcentagem2, porcentagem3, total_porcentagem;
float premio1, premio2, premio3, total_premios;

printf("Infome o valor da aposta do apostador 1: ");
scanf("%f", &aposta1);

printf("Infome o valor da aposta do apostador 2: ");
scanf("%f", &aposta2);

printf("Infome o valor da aposta do apostador 3: ");
scanf("%f", &aposta3);

printf("Informe o valor do premio: ");
scanf("%f", &premio);

total_apostas = (float) (aposta1 + aposta2 + aposta3);
printf("O total de apostas foi de %.2f\n", total_apostas);

porcentagem1 = (float) (aposta1 / total_apostas);
porcentagem2 = (float) (aposta2 / total_apostas);
porcentagem3 = (float) (aposta3 / total_apostas);

total_porcentagem = (float) (porcentagem1 + porcentagem2 + porcentagem3);
printf("O total de porcentagens é: %.2f\n", total_porcentagem);

premio1 = (float) (premio * porcentagem1);
premio2 = (float) (premio * porcentagem2);
premio3 = (float) (premio * porcentagem3);
total_premios = (float) (premio1 + premio2 + premio3);
printf("O total em premios é: %.2f\n", total_premios);

printf("O apostador 1 apostou %.2f que corresponde a %.2f e deverá receber o premio de %.2f\n", aposta1, porcentagem1, premio1);
printf("O apostador 2 apostou %.2f que corresponde a %.2f e deverá receber o premio de %.2f\n", aposta2, porcentagem2, premio2);
printf("O apostador 3 apostou %.2f que corresponde a %.2f e deverá receber o premio de %.2f\n", aposta3, porcentagem3, premio3);

}
```

### Exercícios de estruturas de repetição:
 **1. Faça um programa que determine e mostre os cinco primeiros múltiplos de 3, considerando números maiores que 0.**

```
#include <stdio.h>

int main() {
    for (int i = 1; i <= 7; i++) {
        printf("%d\n", i * 3);
    }

    return 0;
}

```

**Explicação:**
- O **`for`** inicia com `i = 1` e executa enquanto `i` for menor ou igual a 5.
- A cada iteração, o número `i * 3` é impresso. Isso garante que o primeiro múltiplo de 3 seja 3, o segundo 6, e assim por diante.
- O `i` é incrementado automaticamente até que 5 múltiplos de 3 sejam impressos.

Este código resolve o problema de maneira simples e direta usando o laço `for`.

**2. Escreva um programa que declare um inteiro, inicialize-o com 0, incremente-o de 100 em 100, imprimindo seu valor na tela, até que seu valor seja 100000 (cem mil).**

```
#include <stdio.h>

int main() {

for (int i = 0; i <= 100000; i += 100) {
	printf("%d\n", i);
	}
}
```

**Explicação:**
- A variável `i` começa em 0 e é incrementada de 100 em 100 a cada iteração (`i += 100`).
- O `printf("%d\n", i);` imprime o valor de `i` a cada iteração.
- O loop continua até que `i` seja maior que 100000.

**3. Faça um programa que leia 10 números e escreva o maior e o menor valor lido.**

```
#include <stdio.h>
#include <limits.h>

int main() {

int numero;
int maior = INT_MIN;
int menor = INT_MAX;

for (int i = 1; i <= 10; i++) {
	scanf("%d", &numero);
	if (numero > maior) {
		maior = numero;
	} if (numero < menor) {
		menor = numero;
	}
}
	printf("O maior numero é %d e o menor numero é %d\n", maior, menor);
}
```

**Explicação:**
- **Declaração de variáveis:**
    - `numero`: armazena o número digitado pelo usuário.
    - `maior`: inicialmente definido como o valor mínimo possível para um `int` (usando `INT_MIN`), para garantir que qualquer número digitado será maior que esse valor.
    - `menor`: inicialmente definido como o valor máximo possível para um `int` (usando `INT_MAX`), para garantir que qualquer número digitado será menor que esse valor.
- **Laço `for`**:
    - O laço se repete 10 vezes, lendo um número a cada iteração usando `scanf`.
    - Para cada número lido, o programa verifica se ele é maior que o atual valor de `maior` e, em caso afirmativo, atualiza `maior`.
    - O programa também verifica se o número é menor que o valor de `menor` e, em caso afirmativo, atualiza `menor`.
- **Exibição do resultado**:
    - Após o laço terminar, o programa imprime o maior e o menor número digitado.

