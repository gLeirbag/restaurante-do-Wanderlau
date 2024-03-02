# Parte 2 - Criando um Repositório Remoto no GitHub

## Revisão Do Capítulo Anterior

Muito bem Wanderlau! Anteriormente você criou um repositório local, o que quer dizer que somente você tem acesso ao repositório do seu computador.

Agora, você deve criar um repositório remoto para que eventualmente você e até mesmo outras pessoas possam acessar de qualquer lugar.

Para isso usaremos o **GitHub**, uma plataforma para desenvolvedores do qual uma das funcionalidades é o armazenamento de repositórios git.

## Criando um Repositório no GitHub

Uma vez logado no GitHub,  clique no botão com o símbolo '+' no canto superior direito da janela e clique "New repository".

![alt text](/Recursos/Imagens/criarnovorepositorio.png)

###### Botão para criar um novo repositório

Ná pagina que abriu, escreva o nome do repositório, tenho certeza que você já sabe o nome do repositório, não é mesmo? "restaurante-do-Wanderlau". A descrição fica ao gosto do freguês.

Escolha se o repositório será público ou privado, e não marque as opções para adicionar um arquivo README, nem adicionar um arquivo .gitignore, nem escolha uma licença.

**Isso porque já temos um repositório local**, o que planejamos fazer é somente copiar nosso repositório local para o repositório remoto vazio.

>[!WARNING] Aviso!
> Se marcar uma opção que adicione um arquivo, o repositório remoto terá um commit que nosso repositório local não tem, o que causará um conflito.

## Adicionando uma Conexão Remota no Repositório Local

Agora que o repositório remoto foi criado, precisamos adicionar uma conexão remota ao nosso repositório local.

Para tal, usaremos a ferramenta ``git remote`` que nos permite adicionar, remover, listar conexões remotas... Para adicionar uma conexão remota, usamos o comando `git remote add <apelido-da-conexão> <URL>`.

...

Um segundo, Wanderlau, esqueci de algo importante! O git pode fazer uma conexão usando o protocolo **HTTPS** ou **SSH**, dessa forma você se autentica na conexão. Oras, não queremos que qualquer pessoa possa fazer alterações nas suas receitas, não é mesmo?

Se usarmos a URL com o protocolo **HTTPS** (i.e. `https://github.com/gLeirbag/restaurante-do-Wanderlau.git`) o git pedirá seu usuário e senha toda vez que você fizer uma operação remota. E a senha não é a de seu usuário, como era antigamente, mas sim um token de acesso que você pode criar no GitHub.

Há uma opção de armazenar o token de acesso em cache, mas pessoalmente não fui atrás de como fazer isso.

> [!TIP] Dica
> Caso queira criar um token de acesso e ler mais sobre como armazenar o token em caches:
> - [GitHub - Página de Tokens](<https://github.com/settings/tokens>)
> - [GitHub - Caching your GitHub credentials in Git](<https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git>)

Vamos adicionar uma conexão remota usando o protocolo **SSH**(i.e. `git@github.com:gLeirbag/restaurante-do-Wanderlau.git`).
Para isso, vamos criar uma chave pública e privada para o usuário de seu computador e compartilhar a chave pública com o seu perfil do GitHub.

> [!NOTE] Siga as Instruções abaixo.
> Siga as instruções do GitHub para adicionar uma chave SSH ao seu perfil.
> - [GitHub - Adding a new SSH key to your GitHub account](<https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account>)



## Fazendo o 'Push' dos Commits para o Repositório Remoto

Ufa, finalmente! Agora conseguiremos adicionar a conexão remota.

```bash
git remote add github git@github.com:gLeirbag/restaurante-do-Wanderlau.git
```

Neste caso, o apelido da conexão remota escolhido foi `github`. Quando se clona um repositório, o apelido padrão é `origin`, mas te sugeri "github" para que você saiba que o repositório remoto está no GitHub.

Caso não gostou do apelido, é possível a mudança do apelido da conexão remota com o comando `git remote rename <apelido-atual> <novo-apelido>`. Podemos checar a lista de conexões remotas com o comando `git remote` ou de forma mais detalhada (com as URL's das conexões) com `git remote -v`.

```bash
git remote -v
github  git@github.com:gLeirbag/restaurante-do-Wanderlau.git (fetch)
github  git@github.com:gLeirbag/restaurante-do-Wanderlau.git (push)
```

Bacana, agora temos uma conexão remota. Ah... não esqueça de fazer o commit caso tenha realizado alguma modificação. No meu caso, eu modifiquei o arquivo "Parte 2".

```bash
git add . # Adiciona todos os arquivos modificados ao index (Staging Area)
git commit -m "Descrito como criar um repositório remoto no GitHub" # "Commita" as mudanças
```

Podemos enviar nossos commits para o repositório remoto. Só basta usar o comando `git push github master`. "To push" significa "empurrar", ou seja, estamos empurrando nossos commits para o repositório remoto.

- [**Index**](readme.md)
- [**Parte 1 - Iniciando um Repositório**](Parte%201.md)
- [**Parte 3 - Primeira Receita, *git restore* e *Tags***](Parte%203.md)