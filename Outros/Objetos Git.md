# Objetos Git

O git tem seu funcionamento dado através de 4 tipos de objetos: ***blobs***, ***trees***, ***commits*** e ***tags***. Todos esses objetos são armazenados em um diretório chamado `.git/objects`.

## Blobs

Um **blob** é um objeto que armazena **somente o conteúdo** de um arquivo, o blob não armazena o nome do arquivo. Esses objetos são referenciados por um **hash SHA-1**.

> [!IMPORTANT]
> O hash SHA-1 é um algoritmo de criptografia que gera um valor hash de 40 caracteres a partir de um arquivo. Ou seja, gerará um texto de 40 caracteres que é único para cada arquivo. Ótimo para funcionar como um identificador.

## Trees

**Tree** é um objeto que representa um diretório. Por isso, ele associa o nome de um arquivo ao hash SHA-1 do *blob* correspondente. Ele também associa o nome de um diretório a um hash SHA-1 de outro *tree*. 

```bash
100644 blob c3d3a20ee03593c834ef5013a9fb5bf106a71058    .gitignore
040000 tree 19356ce5fbeec15ba71505d2767690c4fc632769    Outros
100644 blob 4611e204bd8e46d5603327c387755629c33b2cb9    Parte 1.md
100644 blob b911a336949881fe23868843d043ec65fe71b477    Parte 2.md
100644 blob 35d6467ee675f310af6db949519b39209a647af9    Parte 3.md
100644 blob d343860b3972dca7900a623463e5c477487e32ee    Parte 4.md
040000 tree f9a8e98ac83576970c9ea688b43054500361bdb6    Receitas
040000 tree cff43fc89544f469738d8b77ad4993f49dda7ecb    Recursos
100644 blob cfd9ae32514f4b3f41f490d98da657e46f430569    To-Do.md
100644 blob 1ab8cf40592a059c3623258ce4dd8a415705562f    readme.md
```
###### Exemplo de conteúdo de um arquivo tree

## Commits

Note que a tree é um objeto que representa um diretório num determinado instante de tempo, quase que um commit.

O ***commit*** nada mais é que a **associação** de uma tree aos seguintes elementos:

* Autor do commit;
* E-mail do autor;
* Data do commit;
* Mensagem do commit;
* Commit pai (ou pais, no caso de um merge).

## Tags

Já discutimos sobre as tags anteriormente (Parte 3), elas são **ponteiros para um commit específico**. Sua estrutura é similar à de um commit. Associa um autor, mensagem, data a um commit(ao invés de uma tree).

## Recomendado

* [**Index**](readme.md)
* [**Parte 3 - Primeira Receita, *git diff*, *git restore* e *Tags***](Parte%203.md)

### Referências

* [**Git Book - 10.2 Git Internals - Git Objects**](https://git-scm.com/book/en/v2/Git-Internals-Git-Objects)