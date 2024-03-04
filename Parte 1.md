# Parte 1 - Criando o Repositório e Fazendo o Primeiro Commit

> [!TIP]
> Caso não tenha configurado o git ou não saiba sequer o que isso significa, é bom ler [Configurando o Git](Outros/Configurando%20o%20Git.md), não é nada complicado, fazer um miojo é muito mais difícil.

Primeiramente, Wanderlau. Você criará um repositório para armazenar as receitas que você planeja criar. Por isso, criaremos no seu computador um diretório para armazenar o repositório. Abra o terminal e digite:

```bash
mkdir restaurante-do-Wanderlau # Make Directory
cd restaurante-do-Wanderlau # Change Directory
```

Vamos iniciar o repositório, criar um novo arquivo e adicioná-lo ao repositório.

```bash
git init
# Alternativamente, poderíamos ter criar o diretório e o repositório ao mesmo tempo
# com o comando:
git init restaurante-do-Wanderlau

# No Linux, podemos criar um arquivo com o comando 'touch'
touch readme 
# No Windows, podemos criar um arquivo com o comando 'echo'
echo.>readme

# Fazemos com que o git rastreie o arquivo
git add readme 
```

Droga, Wanderlau! Nomeamos o arquivo como `readme`, mas o mais apropriado teria sido nomeá-lo como 'README.md'.

Não se preocupe, para corrigir basta renomear o arquivo com o comando 'git mv'.

```bash
git mv readme README.md # Renomeia o arquivo
```

Se não usarmos esse comando, poderia ter renomeado o arquivo manualmente e depois re-adicionado o arquivo ao repositório com o comando `git add README.md`.

> [!IMPORTANT]
> Ei Wanderlau! Vai facilitar muito seu entendimento da próxima seção se você ler [Estados de um Arquivo Rastreado e Sobre um Repositório](Outros/Estados%20de%20um%20arquivo%20e%20Sobre%20um%20Reposit%C3%B3rio.md).

## Informações sobre os estados atuais dos arquivos


Vamos ver os *status* do repositório. O comando 'git status', com a opção '-s', mostra o status do repositório de forma resumida.
  
```bash
git status -s
```

O output do comando é duas colunas seguidas do nome do arquivo.

A primeira coluna mostra o ***status*** do arquivo em relação ao último ***commit***. A segunda coluna mostra o status do arquivo em relação ao *index*(Também conhecido como ***Staging Area***).

* ?? : O arquivo não está sendo rastreado pelo git.
* !! : O arquivo está sendo ignorado pelo git.
* A : O arquivo foi adicionado ao index.
* M : O arquivo foi modificado.
* D : O arquivo foi deletado.
* R : O arquivo foi renomeado.
* T : O tipo do arquivo foi modificado.

Vamos fazer o *commit* do arquivo. 'To commit' em português significa 'comprometer-se'. Ou seja, estamos nos comprometendo com as mudanças que fizemos nos arquivos.

```bash
git commit -m "Adicionado o arquivo README.md"
# Se não passarmos a opção '-m' o git abrirá o editor de texto que configuramos.
```

Pronto, Wanderlau. Você fez o seu primeiro commit. Mas espere um segundo, não criamos um repositório remoto ainda! Mas relaxa que vamos fazer isso no próximo passo.

Vamos criar mais um arquivo para criar um repositório remoto no Github.

```bash
touch "Parte 2 - Criando um Repositório Remoto no Github.md" 
git add "Parte 2 - Criando um Repositório Remoto no Github.md"
git commit -m "Adicionado o arquivo README.md e Parte 2" --amend
```

A opção '--amend' permite consertar o último commit caso tenhamos esquecido de adicionar algum arquivo ou escrevemos a mensagem errada. 

> [!IMPORTANT]
> Ao usar `--amend`, é como se o commit anterior **nunca tivesse existido**.

## Conclusão

Nessa parte inicial, você - Wanderlau - aprendeu a criar um repositório local, a adicionar arquivos a ele e a fazer o primeiro commit. No próximo passo, você aprenderá a criar um repositório remoto no Github e a adicionar uma conexão remota ao repositório local.


- [Index](readme.md)
- [Parte 2 - Criando um Repositório Remoto no Github](Parte%202.md)

