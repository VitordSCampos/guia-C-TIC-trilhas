# Registro de conflito resolvido

> Este documento tem duas partes: (1) um passo a passo de como provocar um conflito de merge de forma controlada, e (2) um template para você preencher com o que de fato aconteceu no seu repositório.

## Como provocar o conflito (siga estes passos)

1. A partir da `main` atualizada, crie duas branches:
   ```bash
   git checkout main
   git checkout -b ajuste-objetivos-a
   ```
   Edite a seção "Objetivos de aprendizagem" do `README.md` (mude a redação de um dos itens). Faça commit:
   ```bash
   git add README.md
   git commit -m "docs: reescreve objetivo 3 do README"
   ```

2. Volte para `main` e crie a segunda branch a partir dela (sem ter mesclado a primeira ainda):
   ```bash
   git checkout main
   git checkout -b ajuste-objetivos-b
   ```
   Edite a **mesma seção, na mesma linha**, com uma redação diferente. Faça commit:
   ```bash
   git add README.md
   git commit -m "docs: reescreve objetivo 3 com outra abordagem"
   ```

3. Suba as duas branches e abra um Pull Request de cada uma para `main` no GitHub:
   ```bash
   git push -u origin ajuste-objetivos-a
   git push -u origin ajuste-objetivos-b
   ```

4. Faça merge do primeiro PR normalmente (não deve dar conflito, porque a `main` ainda não tinha mudado).

5. Ao tentar fazer merge do segundo PR, o GitHub vai acusar conflito, porque as duas branches alteraram a mesma linha. Traga a branch para local e resolva:
   ```bash
   git checkout ajuste-objetivos-b
   git merge main
   ```
   O Git vai marcar o trecho conflitante assim:
   ```
   <<<<<<< HEAD
   (sua versão nesta branch)
   =======
   (versão que já está na main)
   >>>>>>> main
   ```
   Edite o arquivo manualmente, decidindo qual versão manter (ou combinando as duas), remova as marcações `<<<<<<<`, `=======`, `>>>>>>>` e finalize:
   ```bash
   git add README.md
   git commit -m "merge: resolve conflito na secao de objetivos"
   git push
   ```
   Finalize o merge do PR no GitHub.

---

## Template — o que de fato aconteceu

**Branches envolvidas:** `___` e `___`

**Arquivo em conflito:** `___`

**Trecho antes da resolução:**
```
(cole aqui o trecho com as marcações <<<<<<< ======= >>>>>>>)
```

**Decisão tomada:** *(qual versão você manteve, ou como combinou as duas, e por quê)*

**Trecho depois da resolução:**
```
(cole aqui o resultado final)
```

**Comando(s) usado(s) para resolver:**
```
(cole aqui)
```

**O que esse conflito te ensinou:** *(ex.: importância de branches curtas, comunicação antes de editar o mesmo trecho, etc.)*
