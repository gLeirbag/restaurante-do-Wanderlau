# Configurando o Git

>[!TIP]
> Entenda como "escopo" a "visibilidade" que uma configuração possui. Por exemplo, uma configuração global é visível para todos os repositórios que você criar, enquanto uma configuração local é visível apenas para um repositório específico, tu vai entender.

O **git** possuí três arquivos de configuração com definições de variáveis que controlam os aspectos de seu funcionamento. Estes arquivos podem ser encontrados em:

**Windows:**

- **Escopo do Sistema:** `%ProgramFiles%/Git/etc/.gitconfig`
- **Escopo do Usuário (Global):** `C:/Users/usuario/.gitconfig`
- **Escopo do Repositório (Local):**`.../seuProjeto/.git/config`

**Linux:**

- **Escopo do Sistema:** `/etc/gitconfig`
- **Escopo do Usuário (Global):** `~/.gitconfig`
- **Escopo do Repositório (Local):**`.../seuProjeto/.git/config`

Cada arquivo é referente a um **escopo** distinto, assim, as configurações definidas em um arquivo sobrescrevem as configurações definidas em arquivos de escopos inferiores.

O escopo local, o mais específico, é associado a cada projeto git. O escopo global é associado a cada usuário do sistema, então se você e sua irmã usam o mesmo computador, vocês podem fazer uso de configurações diferentes. O escopo do sistema é associado a todos os usuários do sistema, e é o escopo menos específico.

```bash
# Cada comando abaixo define uma variável em um escopo diferente.
git config --system <variável> <valor>
git config --global <variável> <valor>
git config --local <variável> <valor>
```

## Listando as Configurações

Pode listar as variáveis já definidas com o comando `git config --list --show-origin`. A opção `--show-origin` mostra o escopo aonde a variável foi definida.


## Configurando o Nome de Usuário e E-mail

Você pode fazer as atribuições às variáveis tanto editando os arquivos de configuração manualmente com um editor de texto - como o **notepad** do Windows - ou através do comando `git config`.

Nós definimos nosso nome e e-mail para o git para usá-los como **uma assinatura dos nossos *commits***.

```bash
git config --global user.name "Seu Nome"
git config --global user.email "Seu Email"
``` 

Repare que usamos a opção `--global` para definir o escopo da variável como global, dessa forma, enquanto usarmos esse usuário no computador, o git usará essas informações para os commits.

Há quem recomende configurar essas informações para cada repositório, pois as vezes você não quer que seu e-mail pessoal esteja de acesso público.

## Configurando o Editor de Texto

Configurar o editor de texto é útil por exemplo quando se usa o comando `git commit` sem a opção `-m`. Nesse caso, o git abrirá o editor de texto para que você possa escrever a mensagem do commit.

```bash
git config --system core.editor "notepad.exe"
```

Dessa forma, o git abrirá aquele editor de texto padrão do Windows quando necessário. Repare que nesse exemplo usamos a opção `--system`.

## Recomendado

- [Index](../readme.md)
- [Parte 1 - Iniciando um Repositório](../Parte%201.md)