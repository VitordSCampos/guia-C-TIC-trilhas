# 2. Conceitos fundamentais

## Variáveis e tipos

Em C, toda variável precisa ser declarada com um tipo antes de ser usada.

| Tipo | Representa | Exemplo |
|---|---|---|
| `int` | números inteiros | `int idade = 20;` |
| `float` | números decimais (precisão simples) | `float altura = 1.75;` |
| `double` | números decimais (precisão dupla) | `double pi = 3.14159265;` |
| `char` | um único caractere | `char letra = 'A';` |

```c
int idade;      // declaração
idade = 20;     // atribuição

int nota = 8;   // declaração + atribuição na mesma linha
```

### Operadores básicos

- Aritméticos: `+`, `-`, `*`, `/`, `%` (resto da divisão)
- Atribuição: `=`, `+=`, `-=`, `*=`, `/=`
- Relacionais: `==`, `!=`, `>`, `<`, `>=`, `<=`
- Lógicos: `&&` (e), `||` (ou), `!` (não)

**Atenção:** divisão entre dois `int` em C descarta a parte decimal. `7 / 2` resulta em `3`, não `3.5`. Para obter o resultado decimal, pelo menos um dos operandos precisa ser `float` ou `double`.

## Entrada e saída

```c
int idade = 20;
printf("Tenho %d anos\n", idade);
```

Especificadores de formato mais usados:

| Especificador | Tipo |
|---|---|
| `%d` | int |
| `%f` | float/double |
| `%c` | char |
| `%s` | string (vetor de char) |

```c
int idade;
printf("Digite sua idade: ");
scanf("%d", &idade);
```

Note o `&` antes da variável — ele indica o *endereço de memória* da variável, porque o `scanf` precisa saber *onde* guardar o valor lido (você vai aprofundar isso quando estudar ponteiros).

## Estruturas condicionais

```c
int idade = 17;

if (idade >= 18) {
    printf("Maior de idade\n");
} else {
    printf("Menor de idade\n");
}
```

Com múltiplas condições:

```c
int nota = 7;

if (nota >= 9) {
    printf("Conceito A\n");
} else if (nota >= 7) {
    printf("Conceito B\n");
} else {
    printf("Conceito C ou reprovado\n");
}
```

`switch-case` é útil quando você compara uma mesma variável com vários valores fixos:

```c
switch (diaSemana) {
    case 1:
        printf("Domingo\n");
        break;
    default:
        printf("Outro dia\n");
}
```

O `break` é essencial — sem ele, a execução "cai" para o próximo `case` (comportamento chamado de *fall-through*).

## Estruturas de repetição

`for` é ideal quando você sabe quantas vezes quer repetir:

```c
for (int i = 1; i <= 5; i++) {
    printf("%d\n", i);
}
```

`while` testa a condição **antes** de executar (pode nunca executar); `do-while` executa **pelo menos uma vez** antes de testar:

```c
int senha;
do {
    printf("Digite a senha: ");
    scanf("%d", &senha);
} while (senha != 1234);
```

Laços aninhados:

```c
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 3; j++) {
        printf("%d x %d = %d\n", i, j, i * j);
    }
}
```

**Próximo:** [Exercícios →](03-exercicios.md)
