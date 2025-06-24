1. Introdução
O projeto "Meu Filme Ideal" é um sistema de recomendação de filmes desenvolvido em Prolog. O
objetivo é recomendar filmes personalizados aos utilizadores com base em preferências como
gênero favorito, diretor preferido, ator favorito, avaliação mínima e adequação à idade.




2. Base de Dados
A base de dados é composta por dois conjuntos principais de fatos:
- Filmes: Cada filme contém título, gênero, ano de lançamento (2025), diretor, ator principal,
avaliação (de 1 a 10) e classificação etária.
- Utilizadores: Cada utilizador tem nome, idade, gênero favorito, diretor favorito e ator favorito.
Esses dados são representados por fatos Prolog do tipo filme/7 e utilizador/5.



3. Regra de Recomendação
recomenda(Utente, Filme) :-
 utilizador(Utente, Idade, Genero, Diretor, Ator),
 filme(Filme, Genero, _, Diretor, Ator, Nota, Class),
 Nota >= 8.0,
 Class =< Idade.
Essa regra verifica se o filme tem o gênero, diretor e ator favoritos do utilizador, possui nota maior
ou igual a 8.0 e é apropriado para a idade do utilizador.


4. Consultas Possíveis

recomenda(Utilizador, Filme).[recomenda os filmes que o utilizador gosta]
filme(Titulo, drama, _, _, _, _, _).[recomenda os filmes de um gênero.]
filme(Titulo, _, _, carlos_lima, _, _, _).[recomenda os filmes de um diretor.]
filme(Titulo, _, _, _, _, Nota, _), Nota > 9.[recomenda filmes com avaliação acima de 9]
filme(Titulo, _, _, _, _, _, Class), Class =< 12.[recomenda filmes com classificação etária até 12 anos]
filme(Titulo, _, _, _, joana_reis, _, _).[recomenda filmes com determinado ator (ex: joana_reis)]
filme(Titulo, _, 2025, _, _, _, _).[recomenda os filmes lançados em 2025]
recomenda(ana, Filme).[recomendação de filmes para um utilizador (ex: ana)]
recomenda(Utilizador, Filme).[mostra todas as recomendações possíveis para todos utilizzadores]
Essas consultas permitem ao utilizador explorar os dados, ver filmes recomendados, ou realizar
pesquisas específicas com base em critérios desejados.


5. Conclusão
O sistema desenvolvido permite demonstrar a aplicação de lógica simbólica usando Prolog para
resolver um problema prático de recomendação. O projeto integra fatos e regras de forma clara, e
está preparado para ser usado, modificado ou ampliado conforme necessário.
