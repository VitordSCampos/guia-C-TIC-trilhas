# 1. Introdução

## O que é C?

C é uma linguagem de programação compilada, criada por Dennis Ritchie no início dos anos 1970 nos Laboratórios Bell. Apesar da idade, continua extremamente relevante: sistemas operacionais (boa parte do Linux e do Windows), firmware, sistemas embarcados e até partes de outras linguagens (o próprio interpretador do Python é escrito em C) dependem dela.

### Por que aprender C mesmo já sabendo lógica de programação?

Se você já programou em outra linguagem, o "pensar em algoritmo" já está resolvido. O que muda em C:

- **Tipagem estática**: você precisa declarar o tipo de cada variável, e ele não muda depois.
- **Compilação**: o código não roda direto — primeiro é traduzido (compilado) para código de máquina, e só depois executado. Erros de sintaxe aparecem *antes* de rodar, na hora de compilar.
- **Controle próximo do hardware**: C não "esconde" a memória tanto quanto linguagens mais modernas — isso é ao mesmo tempo o que a torna rápida e o que a torna mais exigente para programar.

### Onde C é usada hoje

- Sistemas operacionais e drivers
- Sistemas embarcados (IoT, automação, firmware)
- Bancos de dados e interpretadores de outras linguagens
- Disciplinas introdutórias de Ciência da Computação, por ensinar como o computador realmente executa um programa

## Seu primeiro programa

Todo programa em C parte de uma estrutura mínima parecida com esta:

```c
#include <stdio.h>

int main() {
    printf("Ola, mundo!\n");
    return 0;
}
```

### Linha a linha

- `#include <stdio.h>`: importa a biblioteca padrão de entrada/saída — é dela que vem a função `printf`.
- `int main() { ... }`: todo programa em C começa a executar pela função `main`. O `int` antes dela indica que a função devolve um número inteiro ao sistema operacional ao terminar.
- `printf("Ola, mundo!\n");`: imprime o texto no terminal. O `\n` representa "quebra de linha".
- `return 0;`: encerra o `main` avisando que tudo correu bem (por convenção, `0` significa sucesso).
- Cada instrução termina com `;` — esquecer o ponto e vírgula é o erro de compilação mais comum de quem está começando.

### Compilando e executando

Se estiver usando um compilador local com `gcc`:

```bash
gcc programa.c -o programa
./programa
```

Se preferir não instalar nada, use um compilador online como o onlinegdb.com ou o replit.com — cole o código e clique em rodar.

**Próximo:** [Conceitos fundamentais →](02-conceitos.md)
