# Parte 2 - Criando um Repositório Remoto no Github

## Revisão Do Capítulo Anterior

Muito bem Wanderlau! Anteriormente você criou um repositório local, o que quer dizer que somente tem acesso ao repositório o seu computador.

Agora, você deve criar um repositório remoto para que eventualmente outras pessoas e até mesmo você possa acessar de qualquer lugar.

Para isso usaremos o Github, uma plataforma para desenvolvedores cuja uma das funcionalidades é o armazenamento de repositórios git.

## Criando um Repositório no Github

Uma vez logado no Github,  clique no botão com o símbolo '+' no canto superior direito da janela e clique "New repository".

Ná pagina que abriu, escreva o nome do repositório, tenho certeza que você já sabe o nome do repositório, não é mesmo? "restaurante-do-Wanderlau". A descrição fica ao gosto do freguês.

Escolha se o repositório será público ou privado, e não marque as opções para adicionar um arquivo README, nem adicionar um arquivo .gitignore, nem escolha uma licença.

Isso porque já temos um repositório local, o que planejamos fazer é somente copiar nosso repositório local para o repositório remoto.

## Adicionando uma Conexão Remota no Repositório Local

Agora que o repositório remoto foi criado, precisamos adicionar uma conexão remota ao nosso repositório local.

Para tal, usaremos a ferramenta 'git remote' que nos permite adicionar, remover, listar conexões remotas...

Para adicionar uma conexão remota, usamos o comando `git remote add <apelido-da-conexão> <URL>`.

Um segundo, Wanderlau, esqueci de algo importante! O git pode fazer uma conexão usando o protocolo **HTTPS** ou **SSH**, dessa forma você se autentica na conexão, não queremos que qualquer pessoa possa fazer alterações na suas receitas, não é mesmo?

Se usarmos a URL com o protocolo **HTTPS** (i.e. `https://github.com/gLeirbag/restaurante-do-Wanderlau.git`) o git pedirá seu usuário e senha toda vez que você fizer uma operação remota. E a senha não é a de seu usuário, como era antigamente, mas sim um token de acesso que você pode criar no Github.

Há uma opção de armazenar o token de acesso em cache, mas pessoalmente não fui atrás de como fazer isso.

* Criar Token:<https://github.com/settings/tokens>
* "Caching your GitHub credentials in Git": <https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git>

Vamos adicionar uma conexão remota usando o protocolo **SSH**(i.e. `git@github.com:gLeirbag/restaurante-do-Wanderlau.git`)

Para isso, vamos criar uma chave pública e privada para o usuário de seu computador e compartilhar a chave pública com o seu perfil do Github.

Poh, Wanderlau! Não vou explicar como faz isso! O próprio Github conta com um tutorial para isso. Vá até <https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=windows> e siga as instruções.

## Fazendo o 'Push' dos Commits para o Repositório Remoto

Ufa, finalmente! Agora conseguiremos adicionar a conexão remota.

```bash
git remote add github git@github.com:gLeirbag/restaurante-do-Wanderlau.git
```

O apelido da conexão remota é "github", quando se clona um repositório, o apelido padrão é "origin", mas te sugeri "github" para que você saiba que o repositório remoto está no Github.

Caso não gostou do apelido, pode mudar o apelido da conexão remota com o comando `git remote rename <apelido-atual> <novo-apelido>`. Podemos checar a lista de conexões remotas com o comando `git remote` ou de forma mais detalhada(com as URL's) com `git remote -v`.

```bash
git remote -v
github  git@github.com:gLeirbag/restaurante-do-Wanderlau.git (fetch)
github  git@github.com:gLeirbag/restaurante-do-Wanderlau.git (push)
```

Bacana, agora que temos uma conexão remota. Ah! Não esqueça antes de fazer o commit caso tenha mudado alguma coisa, no meu caso eu modifiquei o arquivo "Parte 2 - Criando um Repositório Remoto no Github.md".

```bash
git add . # Adiciona todos os arquivos modificados ao index (Staging Area)
git commit -m "Descrito como criar um repositório remoto no Github" # "Commita" as mudanças
```

 podemos enviar nossos commits para o repositório remoto. Só basta usar o comando `git push github master`. "To push" significa "empurrar", ou seja, estamos empurrando nossos commits para o repositório remoto.
