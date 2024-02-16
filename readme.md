# Restaurante do Wanderlau

Você é Wanderlau, um aspirante a chef de cozinha que acabou de abrir seu primeiro restaurante. Teu amigo Manoel, que trabalha para a ABIN, descobriu que o grande crítico gastronômico francês, **o Sr. Pierter Dussuí**, visitará os restaurantes de sua cidade.

Sr. Dussuí é conhecido por ter o poder de elevar ou destruir a popularidade dos restaurantes que visita. Essa é a sua chance de fazer seu negócio decolar para a extratosfera ou sucumbir ao esquecimento e fracasso.

Vamos lá, Wanderlau, vamos usar a ferramenta de controle de versão Git e o Github para planejar os melhores pratos que o Brasil já viu!!

## Parte 1 - Criando o Repositório e Fazendo o Primeiro Commit

Primeiramente, Wanderlau. Você criará um repositório para armazenar as receitas que você planeja criar. Primeiramente, criaremos no seu computador um diretório para armazenar o repositório. Abra o terminal e digite:

```bash
mkdir restaurante-do-Wanderlau # Make Directory
cd restaurante-do-Wanderlau # Change Directory
```

Vamos iniciar o repositório, criar um arquivo e adicioná-lo ao repositório.

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

Ótimo, dessa forma não precisamos deletar o arquivo antigo e criar outro. Vamos ver o status do repositório. Com a opção '-s' o comando 'git status' mostra o status do repositório de forma mais resumida.
  
A primeira coluna mostra o status do arquivo em relação ao último commit. A segunda coluna mostra o status do arquivo em relação ao index(Também conhecido como Staging Area).

* ?? : O arquivo não está sendo rastreado pelo git.
* !! : O arquivo está sendo ignorado pelo git.
* A : O arquivo foi adicionado ao index.
* M : O arquivo foi modificado.
* D : O arquivo foi deletado.
* R : O arquivo foi renomeado.
* T : O tipo do arquivo foi modificado.

```bash
git status -s
```

Vamos fazer o commit do arquivo. Traduzindo 'to commit' significa 'comprometer-se'. Ou seja, estamos nos comprometendo com as mudanças que fizemos nos arquivos.

```bash
git commit -m "Adicionado o arquivo README.md"
# Se não passarmos a opção '-m' o git abrirá o editor de texto que configuramos.
```

Pronto, Wanderlau. Você fez o seu primeiro commit. Mas espere um segundo, não criamos um repositório remoto ainda! Vamos fazer isso no próximo passo. Vamos criar mais um arquivo para criar um repositório remoto no Github.

```bash
touch "Parte 2 - Criando um Repositório Remoto no Github.md" 
git add "Parte 2 - Criando um Repositório Remoto no Github.md"
git commit -m "Adicionado o arquivo README.md e Parte 2" --amend
```

A opção '--amend' permite consertar o último commit caso tenhamos esquecido de adicionar algum arquivo ou escrevemos a mensagem errada. É como se o último commit nunca tivesse acontecido.

Continuamos no próximo arquivo.
