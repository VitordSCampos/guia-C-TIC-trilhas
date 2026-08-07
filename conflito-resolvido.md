# Registro de conflito resolvido


**Branches envolvidas:** `ajuste-objetivos-a` e `ajsute-objetivo-b`

**Arquivo em conflito:** `README.md`

**Trecho antes da resolução:**
```
(<<<<<<< HEAD
- - descrever os fundamentos da linguagem C e justificar por que ela continua sendo usada hoje;
=======
- explicar a importância da linguagem C e o porque ela se amntém relevante até os dias atuais;
>>>>>>> fa7c82faf5d9cb8a07dfdd4d5c3016f6f7085107)
```

**Decisão tomada:** *(qual versão você manteve, ou como combinou as duas, e por quê)*
A versão mantida foi uma combinação sintática das versões que causaram o conflito, a fim de aproveitar da mellhor maneira descritiva do objetivo listado.

**Trecho depois da resolução:**
```
-explicar os fundamentos da linguagem C e por que ela se mantém relevante até os dias atuais;
```

**Comando(s) usado(s) para resolver:**
```
Após fazer o git pull origin com ajuste-objetivos-b, o conflito c=foi notificado no terminal no VsCode, impedindo o commit do mesmo, nisso foi verificado o conflito no arquivo README.md, o arquivo foi editado sintaticamente e a sequência para o commit foi repetida, sendo enviada ao github com sucesso.
```

**O que esse conflito te ensinou:** 
importância de dar nomes bem caracteristicos para cada branch, impedindo confusões na hora de subir edições para a nuvem, além disso a necessidade de uma comunicação clara entre o time antes de fazer qualquer edição em trechos próximos.
