# Parte 5 - Branches Remotas e Tracking Branches

## Introdução



## Branches Remotas

No guia anterior, falamos sobre branches. Mas trabalhamos com elas apenas no seu computador. Caso queira compartilhar tua branch com o repositório remoto, você precisa explicitamente enviar ela para lá.

```bash
git push <conexão-remota> <branch-local>
```

No caso, já deletamos a branch que criamos mas registrei essa informação porque é algo relevante, Wanderlau.

> [!WARNING]
> Podemos deletar uma branch remota com o comando `git push <conexão-remota> --delete <branch-remota>`.

## Tracking Branches

Wanderlau... Tinha uma coisa que eu podia ter te falado mais cedo...

Lá atrás, eu falei que para enviar os commits para o repositório remoto, se usa o comando `git push <conexão-remota> <branch-local>`. No nosso caso específico, usamos `git push github master`.

Eu sei que é cansativo ficar escrevendo `github`e `master` toda vez, e o que eu escondi de você é há uma maneira de evitar isso. Me desculpe...

Se usarmos git push sem argumentos recebemos uma mensagem de erro, mas ela nos dá uma dica de como resolver o problema.

```bash
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=github/<branch> master
```

Se trata de criarmos um ***link*** entre uma branch local e uma branch remota. Isso é chamado de ***tracking branch***. 

Uma tracking branch automaticamente "segue" a branch remota, e quando usamos `git push` ou `git pull` sem argumentos, o git sabe para onde enviar ou de onde puxar os commits.

**Branch Local**, **Branch Remota**, Tracking Branch, é branch pra dar com pau! Ou melhor, é branch para dar com galho!

Branches locais são aquelas que estão no seu computador, e branches remotas são aquelas que estão no repositório remoto.

### Criando uma Tracking Branch

O comando `git branch`lista todas as branches locais! Podemos usar o comando `git branch -a` para listar tanto as branches locais quanto as remotas.

```bash
git branch -a
* master
  remotes/github/master
```

Podemos usar ainda a opção `-v` para ver mais informações sobre as branches. E podemos combinar as opções `-a` e `-v` para ver mais informações sobre todas as branches.

```bash
git branch -av
* master                d88c413 Revisão da parte 4
  remotes/github/master d88c413 Revisão da parte 4
```

Só para constar, d88c413 é o hash do último commit da branch master. No caso, como ambas as branches estão apontando para o mesmo commit, podemos dizer que a branch master está **sincronizada** com a branch remota.

Bom, chega de enrolação, vamos criar uma tracking branch! Basta fazermos o seguinte:

```bash
git branch --set-upstream-to=github/master master
# git branch --set-upstream-to=<repositório-remoto>/<branch-remota> <branch-local>
# no lugar de --set-upstream-to, podemos usar -u.
```

Pronto,  Wanderlau! Agora, quando usarmos `git push` ou `git pull` sem argumentos, o git sabe para onde enviar ou de onde puxar os commits.

No comando `git branch` podemos usar duas opções `-vv` para ver mais informações sobre essas *tracking branches*.

```bash
git branch -vva
* master                d88c413 [github/master] Revisão da parte 4
  remotes/github/master d88c413 Revisão da parte 4
```

Repare que agora temos a informação `[github/master]` ao lado da branch master. Isso indica que a branch master está **rastreando** a branch remota.

> [!NOTE]
Podemos ver ainda mais informações sobre as tracking branches com o comando `git remote show <repositório-remoto>`.

> [!NOTE]
Podemos desativar o tracking branch com o comando `git branch --unset-upstream`.

## Sobremesa - A Receita Final

Nossa, o título ficou meio dramático, mas é isso mesmo. Para Pieter Dussuí só falta a sobremesa..

Está me falando que teve a ideia perfeita? Fazer um especialíssimo *Petit Gateau*?

Jogada de mestre, Wanderlau! A viagem gastronômica começa numa salada tropical remetendo ao Brasil, então viajamos para a Itália com um autêntico *Spaghetti alla Carbonara*, e trazemos Dussuí de volta a sua terra natal com um *Petit Gateau*.