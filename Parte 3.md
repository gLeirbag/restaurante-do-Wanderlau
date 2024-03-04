# Parte 3 - Definindo a Primeira Receita

## Revisão do Capítulo Anterior

Ei, Wanderlau! No último capítulo você criou um repositório remoto no Github e o associou ao repositório local. Agora finalmente você poderá começar a escolher as receitas para impressionar o **o Sr. Pierter Dussuí**.

E então, Wanderlau, o que você tem em mente? Qual será a primeira receita que você irá criar?

## Criando um Arquivo de Receita

Hmm, entendi, Wanderlau. Realmente parece sensato começar com uma entrada. Uma salada com camarões e abacate, não é mesmo? Para Dussuí se aclimatar com o clima tropical do Brasil. Poxa, Wanderlau, você é um gênio!

Então, você criará um diretório para armazenar as receitas? Ah, sim, suponho que possa usar o comando `mkdir Receitas` para criar o diretório e `cd Receitas` para entrar no diretório.

> Wanderlau então criou um arquivo e escreveu a receita.

Olha... fiquei com água na boca com essa sua receita. Mas, Wanderlau, o que é isso? O que é esse monte de caracteres aleatórios no final do arquivo?

>[!WARNING] Final do arquivo "Entrada - Saladinha Básica.md"
>
> * 2 colheres de sopa de azeite de oliva extra virgem
> * Sal e pimenta a gosto
>AAAAAABBBBBBBCCCCCCCDDDDDDDEEEEEEEFFFFGGGGGGHHHHHHHIIIIIIJJJJJJKKKKKKLLLLLMMMMMNNNNNOOOOOOPPPPPQQQQQRRRRRSSSSSTTTTTUUUUUVVVVVVWWWWXXXYYYZZZZZ


Oh não, Wanderlau! Está me dizendo que, após você ter adicionado o arquivo `Entrada - Saladinha Básica.md` ao repositório local com o comando `git add "Entrada - Saladinha Básica.md"` um **gato** invadiu seu escritório, pisou em seu teclado e escreveu um monte de caracteres aleatórios no arquivo?

## Consertando Erros

Vamos reconstituir os acontecimentos.

1. Você **criou o arquivo** e **escreveu** a receita;
2. **Começou a rastreá-lo** com `git add`;
3. O gato invadiu seu escritório, pisou no teclado e **salvou** o arquivo.

Nesse caso, veremos o seguinte ao verificar o *status* do repositório:

```bash
git status -s
AM "Parte 3.md"
```

O '**A**', na coluna do *index* (ou *Staging Area*), indica que o arquivo foi adicionado a *Staging Area*. O '**M**', na coluna do *Working Directory*, indica que o arquivo foi modificado e é diferente do que está na *Staging Area*.

Sabe de uma coisa, Wanderlau? Isso me lembra daquela conversa que tivemos quando não consegui tirar minha CNH.
> Toda crise é uma oportunidade de aprendizado.

Agora é uma boa oportunidade de aprendermos sobre o comando `git diff`. O comando `git diff` nos mostra as diferenças entre o *Working Directory* e a *Staging Area*.

```bash
git diff "Entrada - Saladinha Básica.md"
...
* 2 colheres de sopa de azeite de oliva extra virgem
+ AAAAABBBBBBBCCCCCCCDDDDDDDEEEEEEEFFFFGGGGGGHHHHHHHIIIIIIJJJJJJKKKKKKLLLLLMMMMMNNNNNOOOOOOPPPPPQQQQQRRRRRSSSSSTTTTTUUUUUVVVVVVWWWWXXXYYYZZZZZ
```

O comando `git diff` nos mostra a diferença no arquivo da *Working Directory* e o arquivo na *Staging Area* ou do último *commit* caso não tenha sido adicionado à *Staging Area* (que no caso também é a *Staging Area*, só que do último commit).

> [!TIP]
> O comando `git diff --staged` nos mostra a diferença entre o *Staging Area* e o último *commit*.

Legal, agora confirmamos que o gato bagunçou o arquivo.

Se simplesmente usarmos o comando 'git status', veremos a solução para o problema:

```bash
git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
    modified:   "Entrada - Saladinha Básica.md"
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
    modified:   "Entrada - Saladinha Básica.md"****
```

Oras, então é só usar o comando `git restore "Entrada - Saladinha Básica.md"` para desfazer as alterações que não foram adicionadas à *Staging Area*. Corrigido o problema!

> [!TIP]
> `git restore [arquivo]` é equivalente a `git checkout -- [arquivo]`, o primeiro comando é mais recente e mais intuitivo.

>[!TIP]
> **Caso queira retirar um arquivo da *Staging Area* sem modifica-lo**, use o comando `git restore --staged [arquivo]`.

## Marcando um Marco com *Tags*

Ufa... Finalmente, depois de tanto tempo, temos a primeira receita do restaurante do Wanderlau. Isso é um grande marco, não é mesmo?

Se ao menos o git tivesse uma **funcionalidade de marcar pontos importantes no histórico do repositório**. Ah, mas tem! São as ***tags***.

As tags nada mais são do que **ponteiros para um commit específico**, como uma placa de sinalização no meio da estrada. Um exemplo de uso de tags é para marcar versões de um software.

No git há dois tipos de tags: **lightweight** e **annotated**.

A diferença entre elas é que a **annotated tag** possui informações associadas a ela, como o nome do autor, a data e uma mensagem para a tag.

Vamos criar um commit e marcar um marco com uma tag **annotated**. Note que a tag é associada ao último commit.

```bash
git add * # Adiciona todos os arquivos modificados ao index (Staging Area)
git commit -m "Primeira receita escrita" # Commita as mudanças
git tag -a v0.1 -m "Primeira receita escrita" # Cria uma tag 'annotated'
git push github master # Envia os commits para o repositório remoto

# A opção '-a' indica que estamos criando uma tag 'annotated', note que ela 
# também possui uma mensagem. Caso não passemos a opção '-m' o 
# git abrirá o editor de texto que configuramos.
```

Ah, eu ia me esquecendo de outro detalhe importante! As tags precisam ser explicitamente enviadas para o repositório remote, **não são enviadas automaticamente com o comando`git push`**.

Para enviar a tag para o repositório remoto, usamos o comando `git push github <tag>`. No nosso caso, `git push origin v0.1`.

Poderíamos enviar todas as tags de uma vez com o comando `git push github --tags`.

>[!TIP]
> Caso queira saber mais sobre as tags e outros objetos do git, leia [Objetos Git](Outros/Objetos%20Git.md).

## Outros detalhes

* Para listar as tags, use o comando `git tag`.
* Para atualizar uma tag (Fazer com que ela aponte para outro commit), use o comando `git tag -f <tag>`.
* Para deletar uma tag, use o comando `git tag -d <tag>`.
* Para ver informações sobre uma tag, use o comando `git show <tag>`.
* Para associar uma tag a um commit específico, use o comando `git tag -a <tag> <hash do commit>`.

> [!TIP]
> Existem ferramentas pra úteis para usar o `git diff` de maneira mais intuitiva.

* [**Index**](readme.md)
* [**Parte 2 - Adicionando uma Conexão Remota no Repositório Local**](Parte%202.md)
* [**Parte 4 - *git restore* e *Tags***](Parte%204.md)