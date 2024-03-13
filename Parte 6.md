# Resolução de Conflitos

## Sobremesa - A Receita Final

Nossa, o título ficou meio dramático, mas é isso mesmo. Para Pieter Dussuí só falta a sobremesa...

Está me falando que teve a ideia perfeita?!? Fazer um especialíssimo *Petit Gateau*?

Jogada de mestre genial, Wanderlau! A viagem gastronômica perfeita. Decolamos de uma salada tropical  - remetendo ao Brasil, então damos um pula na Itália, com um autêntico *Spaghetti alla Carbonara*. E por fim, trazemos Dussuí de volta a sua terra natal, com um ***Petit Gateau***.

Vamos lá, então, para a receita final!

## Introdução

>  Wanderlau então começou a escrever a receita, mas para sua surpresa, nesse meio tempo, sua namorada enviou para o repositório uma receita especial de ***Petit Gateau***.

Está me dizendo que você foi perguntar pra ela se lembrava da receita de ***Petit Gateau*** que vocês fizeram juntos no último aniversário dela? E de repente, ela já colocou a receita no repositório?

Nossa, Wanderlau, como sua namorada é prestativa. E agora? Está me dizendo que há alguns pontos na sua receita que você gostaria de manter, mas também gostaria de adicionar alguns ingredientes da receita dela?

Mas essa é a situação perfeita para um *merge*!

## Fazendo o Merge

Vejamos a situação. Nós temos nossa receita na branch local `master` e a receita da sua namorada na branch `petitGateu` no `github`. Se dermos um `git status` veremos que teoricamente estamos "atualizados" com o repositório remoto pois ainda não demos `git fetch`.

Vamos primeiro commitar o que temos agora e em seguida fazer um `git fetch` para atualizarmos as informações do repositório remoto.