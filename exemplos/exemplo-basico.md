# Exemplo básico resolvido

Um programa único que junta os quatro conceitos do guia — variáveis, entrada/saída, condicional e repetição — num problema só: **calcular a média de notas de uma turma e dizer quantos alunos foram aprovados.**

## Enunciado

Ler quantos alunos existem, depois ler a nota de cada um (0 a 10), e ao final imprimir:
- a média da turma;
- quantos alunos foram aprovados (nota ≥ 7,0).

## Código completo

```c
#include <stdio.h>

int main() {
    int totalAlunos;
    int aprovados = 0;
    float notaAtual;
    float somaNotas = 0;

    printf("Quantos alunos tem a turma? ");
    scanf("%d", &totalAlunos);

    for (int i = 1; i <= totalAlunos; i++) {
        printf("Nota do aluno %d: ", i);
        scanf("%f", &notaAtual);

        somaNotas += notaAtual;

        if (notaAtual >= 7.0) {
            aprovados++;
        }
    }

    float media = somaNotas / totalAlunos;

    printf("\nMedia da turma: %.2f\n", media);
    printf("Alunos aprovados: %d de %d\n", aprovados, totalAlunos);

    return 0;
}
```

## Por que o código é assim

- `totalAlunos` e `aprovados` são `int` porque representam contagens inteiras; `notaAtual`, `somaNotas` e `media` são `float` porque notas podem ter casas decimais.
- O `for` repete a leitura exatamente `totalAlunos` vezes — um caso clássico de "sei quantas vezes preciso repetir", por isso `for` e não `while`.
- `somaNotas += notaAtual;` é o mesmo que `somaNotas = somaNotas + notaAtual;` — vai acumulando o total a cada volta do laço.
- O `if` dentro do laço testa cada nota individualmente e incrementa `aprovados` só quando a condição é verdadeira.
- A média só é calculada **depois** do laço terminar, porque precisa da soma completa.
- `%.2f` formata o float com 2 casas decimais na hora de imprimir.

## Para praticar

Tente modificar este programa para também informar:
- a maior e a menor nota da turma;
- o percentual de aprovação (aprovados / totalAlunos * 100).

Essas duas variações usam exatamente os mesmos conceitos já vistos — é um bom teste para saber se os fundamentos do guia realmente fixaram.
