# Trabalho1 AED 2023-2024

Este é o código-fonte para o primeiro projeto de AED 2023-2024.

## Ficheiros

- `image8bit.c` - implementação do módulo (a COMPLETAR)
- `image8bit.h` - interface do módulo
- `instrumentation.[ch]` - módulo para contagens de operações e medição de tempos
- `imageTest.c` - programa de teste simples
- `imageTool.c` - programa de teste mais versátil
- `Makefile`    - regras para compilar e testar usando `make`
- `README.md`   - estas informações que está a ler
- `TIPS.md`     - sugestões para os alunos
- `Design-by-Contract.md` - explicação sobre metodologia DbC


## Compilar

- `make` - Compila e gera os programas de teste.
- `make clean` - Limpa ficheiros objeto e executáveis.



## Atualizar repositório


Dada a natureza do trabalho, poderá ser necessário
atualizar repositório base (upstream) deste projeto.
Se isso acontecer, deverá atualizar o seu repositório com os seguintes comandos:

```bash
git remote add upstream git@github.com:detiuaveiro/image8bit-pub.git
git fetch upstream
git rebase upstream/master
```

## Recursos

Sugere-se o desenvolvimento progressivo pela seguinte ordem:

1. Completar `ImageCreate` e `ImageDestroy`.
2. Compilar os programas correndo `make`
   e testar com
Também pode ler sobre os princípios da [programação por contrato][dbc],
que são seguidos neste projeto.

   ```bash
   valgrind ./imageTool test/original.pgm save out.pgm`
   ```
   
   Isto chama `ImageLoad`, que chama `ImageCreate`
   e depois `ImageSave` e `ImageDestroy`.
   Verificar que toda a memória foi libertada.
3. Completar a função interna `G`,
   que é usada por `ImageSetPixel` e `ImageGePixel`.
4. Completar `ImageStats`.
   Se usar `ImageGePixel`, permitirá testar `G`.
   Testar com `./imageTool test/original.pgm info`.
5. Completar `ImageNegative`, `ImageThreshold`, `ImageBrighten`.
6. Completar `ImageValidRect`.
7. Completar `ImageMirror`, `ImageRotate`.
8. Completar `ImageCrop`, `ImagePaste` e `ImageBlend`.
9. Completar `ImageMatchSubImage` e `ImageLocateSubImage`.
10. Completar `ImageBlur`.

Pode executar `make test1`, `make test2`, etc.
para fazer testes simples a muitas destas funções.
Mas faça outros testes que considere adequados.

## Atualizar repositório


Dada a natureza do trabalho, poderá ser necessário
atualizar repositório base (upstream) deste projeto.
Se isso acontecer, deverá atualizar o seu repositório com os seguintes comandos:

```bash
# Fazer esta apenas 1 vez:
git remote add upstream https://github.com/detiuaveiro/image8bit-pub.git

git fetch upstream
git checkout main
git merge --allow-unrelated-histories upstream/main
# (Resolver quaisquer conflitos que surjam...)
git commit
```


