# Parte 1 - Criando o Repositório e Fazendo o Primeiro Commit

Primeiramente, Wanderlau. Você criará um repositório para armazenar as receitas que você planeja criar. Por isso, criaremos no seu computador um diretório para armazenar o repositório. Abra o terminal e digite:

```bash
mkdir restaurante-do-Wanderlau # Make Directory
cd restaurante-do-Wanderlau # Change Directory
```

Vamos iniciar o repositório, criar um arquivo e adicioná-lo nele.

```bash
git init
#Alternativamente, poderíamos ter criar o diretório e o repositório ao mesmo tempo com o comando:
git init restaurante-do-Wanderlau

touch readme # Cria um arquivo vazio
git add readme # Fazemos com que o git rastreie o arquivo
```

Droga, Wanderlau! Você criou o arquivo 'readme' mas o mais apropriado teria sido nomeá-lo como 'README.md'. Não se preocupe, vamos corrigir isso.

```bash
git mv readme README.md # Renomeia o arquivo
```

Ótimo, dessa forma não precisamos deletar o arquivo antigo e criar outro.

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

A opção '--amend' permite consertar o último commit caso tenhamos esquecido de adicionar algum arquivo ou escrevemos a mensagem errada. É como se o último commit nunca tivesse acontecido.

## Conclusão

Nessa parte inicial, você - Wanderlau - aprendeu a criar um repositório local, a adicionar arquivos a ele e a fazer o primeiro commit. No próximo passo, você aprenderá a criar um repositório remoto no Github e a adicionar uma conexão remota ao repositório local.
