# Projeto GIFDEX (Solana App)
Construído na Solana Devnet
Criado com Solana 1.14.17

Site disponível em [https://solana-app.jg-lembo.repl.co/](https://solana-app.jg-lembo.repl.co/) através do Replit.

## A Plataforma

A plataforma do projeto tem como funcionalidade permitir que os usuários colecionem uma Pokédex completa feita a partir de GIFs dos Pokémons.

Inicialmente, o usuário deve conectar sua carteira para poder visualizar a coleção. Assim, ele poderá ver todos os GIFs que já foram inseridos. No topo da página, o usuário pode utilizar o formulário para adicionar um GIF a um Pokémon que ainda não esteja registrado. A checagem de que o Pokémon existe e está disponível é feita pelo frontend. 

Além disso, todos os Pokémons não registrados possuem cards padrão indicando que o Pokémon não possui registro. Utilizando o botão de "Adicionar" no card, o usuário consegue adicionar diretamente o link do GIF daquele Pokémon em específico.

Por fim, nos cards de Pokémons já existentes, que possuem nome e número do Pokémon, além da carteira do usuário que os registrou, qualquer usuário pode usar o botão de "Curtidas" para curtir o GIF, sendo que este próprio botão exibe a quantidade de curtidas. Caso o usuário tenha curtido um GIF, pode usar o mesmo botão para remover sua curtida, caso queira.

## O Programa Solana

O programa Solana contém o código necessário para executar todas as funcionalidades da GIFDEX, como adicionar Pokémons e curtir GIFs.

O código inicial do programa é responsável por criar a conta que armazenará todos os GIFs e respectivas informações.

A função _add\_gif_ é a responsável pela adição dos GIFs. As informações armazenadas, além do link do GIF em questão, são o nome do Pokémon a que o GIF se refere e o endereço da carteira do usuário que o enviou. Além disso, um contador de curtidas e uma lista com os usuários que curtiram o GIF são criados.

A função _like\_gif_ é a que permite que os usuários deixem suas curtidas em um GIF. Além de adicionar uma curtida ao GIF, ela também adiciona o usuário que a executou em uma lista de pessoas que curtiram o GIF. Assim, ela garante que um mesmo usuário não deixe mais de uma curtida no mesmo Pokémon. A função _remove\_like\_gif_, por sua vez, retira a curtida de um GIF, caso o usuário já o tenha curtido. Ela remove a sua curtida e remove seu endereço da lista de usuários que já curtiram o GIF, permitindo que ele possa deixar sua curtida novamente no futuro.