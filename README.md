# analise-jogos-tabuleiro
análise rápida dos jogos ranqueados na Ludopedia (Portal de jogos de tabuleiro)

Disponibilizei o artigo das analises no fórum da Ludopedia 
https://www.ludopedia.com.br/topico/57280/analise-rapida-dos-jogos-ranqueados-na-ludopedia?id_post=397999#id_post_397999

---

De tempos em tempos procurava na internet para ver se alguém já havia conseguido esses dados e disponibilizado na rede. Há alguns dias atrás, após pesquisar na internet, encontrei uma base dados fornecida na plataforma Kaggle (De acordo com eles, Kaggle é a maior comunidade de ciência de dados do mundo com ferramentas e recursos poderosos para ajudar você a atingir suas metas de ciência de dados.), há pelo menos 7 meses (como eu não havia encontrado antes??), pelo usuário BRUNOVR. Agradeço a ele por disponibilizar os dados (https://www.kaggle.com/datasets/brunovr/ludopedia-rank).


O conjunto de dados contido no Kaggle é bem minimalista, contendo somente os seguintes dados:
 - ***idade***: idade recomendada para jogar o jogo
 - ***artista***: Nomes de artistas que trabalharam no jogo (separados por vírgulas)
 - ***designer***: Nomes de game designers (separados por vírgulas)
 - ***dominio***: Domínio do jogo (Especialista, Família ou Criança)
 - ***imagem***: URL para uma imagem da capa do jogo
 - ***mecanicas***: Lista de mecânicos envolvidos no jogo
 - ***mídia***: pontuação média dada pelos usuários
 - ***notaRank***: pontuação dada pelo site (média bayesiana)
 - ***notas***: Quantidade de usuários dando pontuação ao jogo
 - ***numOfPlayers***: Número de jogadores que podem jogar o jogo
 - ***Posição***: Posição no ranking
 - ***timeOfPlay***: Tempo estimado de jogo único
 - ***título***: título do jogo
 - ***ano***: ano de lançamento


Perceba que nessa base não contêm dados de categoria, descrição, quantas pessoas favoritaram, etc.

Primeiramente, gostaria de ressaltar algumas coisas. A primeira é que os dados contidos na base de dados contém um viés de amostragem, para você entender melhor o que é isso, vou dar um exemplo:

- Você gosta de jogos de tabuleiro?
- ( ) Sim
- ( ) Não


Se eu colocasse a pergunta acima na Ludopedia, para os usuários responderem, a resposta ‘Sim’ teria 100% dos votos, por conta que a maioria dos usuários da plataforma possuem apreço por boardgames.


Vendo de outra forma, jogadores casuais, como familiares, crianças ou aquele seu amigo que joga esporadicamente com você, não teriam interesse em se cadastrar na Ludopedia e/ou se tornar usuários ativos na comunidade. Isso implica que há menos usuários casuais ou infantis ativos na comunidade do que usuários que gostam de jogos Expert..


Dito isso, essas análises servirão para designers tomarem melhores decisões e encontrarem o caminho mais adequado no desenvolvimento dos seus jogos. Assim como a Netiflix, que não decide comprar licenças de séries de TV como Stranger Things porque eles acham que os assinantes "podem" gostar. Seria muito arriscado tomar decisões tão grandes baseadas apenas em uma "persona" ou "idéia" do que seus clientes comuns gostam. Para garantir que isso aconteça, a Netflix usa análise de dados, data science e previsões para apoiar seus tomadores de decisão durante todo o processo de aquisição.


Essas análises também servirão para jogadores novos que procuram parecidos com os quais gostam ou que gostariam de enter um pouco mais do universo de jogos de tabuleiro.


Agora que a enrolação acabou, gostaria que você me acompanhasse nessas análises!


![Nota média do ranking por categoria](https://lh6.googleusercontent.com/yRFdeE0Ecqk_Bb2BqNvxDUm08HVM7DORlvyEKvy_bh3j1NBJqv3i1VCcp01vMl23ZNYzzyIUdKmp1a50TdXLcT7FqS6lXnZFCy_vc9BoKJhOzjHwMJ1nQ3dHJNO1FyGe1DXFR-CG)

O primeiro gráfico, apresentado acima, demonstra que Jogos Expert possuem notas melhores no ranking do que jogos de outros domínios, mas isso tem uma grande influência do viés de amostragem que havíamos abordado anteriormente. Vamos analisar mais cuidadosamente esses dados.

![Quantidade de jogos por categoria](https://lh3.googleusercontent.com/7GQ6VDYmT0ivrFXug0AsEUHM1DTNE7ALlDbqw62DRQ9NZbTzvTe_J8hy8hwUJphWYYIEFlR9V79dDklvAMrsy8E5kVpq8O1DkraS3FF1jcMYsip9f2DysA2nBsYZ1ZyIp4uYG7-H)

Neste segundo gráfico, podemos ver que a quantidade de Jogos Expert presentes no ranking é muito maior do que nas outras categorias. Isso demonstra que há um gap para Jogos Familiares no mercado nacional, que é, aproximadamente, dois terços da quantidade de Jogos Experts no mercado. E um gap ainda maior para jogos infantis, bastante inferior aos outros domínios. Mas será que não fazem mais jogos infantis porque não tem público para isso?


![Quantidade média de avaliações por categoria](https://lh3.googleusercontent.com/oGwSuQ64Y-tsKaumDF78Lu7xKUYD_DYRznS798kId0HOiFbrKc00Q2L5vGRP9Lld2tzaFvzu0dZnbjtWXZaGU7qH87kqGHmM4aB2TTGApyyEf0rabtu4O0uxG3XxUBae0FRYZ2yb)


Ifelizmente não possuimos a variável 'Quantidade de pessoas que jogaram o jogo', para contornar isto, podemos usar a variavel 'Quantidade de avaliações do jogo', devido a alta correlação entre essas duas variáveis. Podemos supor, analisando o gráfico acima, que há mais jogadores casuais que jogadores Experts (emoticon da cabeça explodindo). Podemos supor, também, que a quantidade de pessoas que jogam jogos infantis é aproximadamente a metade das pessoas que jogam jogos experts (emoticon da cabeça explodindo novamente). Isso significa que há um gap de jogos infantis, pois a quantidade de jogos infatis é bem menor que a metade da quantidade de jogos Experts no mercado, como vimos na analise anterior.


![Quantidade de jogos por classificação etária](https://lh3.googleusercontent.com/N7oL3NSTzZNd5mTyGSY5UbBEB3eoDRVWGBK4T8F1b5ZC2OizOZWZNEJtkAYKDDTx_6oQRfnVL1QGogCSHQUZ5s9DTZwlmcdVrioJ93RnkrU6lolBeOs6XnvRtItlvAx6B0K2a9jZ)


O gráfico acima corrobora com as suposições feitas anteriormente, ou seja, existem mais jogos voltados para o público “adolescente” e adulto, conjuntamente, do que para outros tipos de público. Resumindo, existem, no mercado nacional, poucos jogos voltados para o público infantil e para o publico adulto isoladamente (faixa etária acima de 18 anos).

![Quantidade média de avaliações por classificação etária](https://lh4.googleusercontent.com/2LS7w2Xeb7uI7Lar16eG_Kd0fRv7F8vWJeo0jFj3BCrsp89u8u8dz_OALR7sDz3q7ob4F67u2aQpaAiTFHo5j-l9MoYO09ZREXpVJ3yBtaw72enwHh2QJ_6DmCJRVAiffDL2cngy) 

Além de batermos o martelo sobre o assunto que jogos infantis (jogos para crianças acima de 5 ou 6 anos) são bastante jogados apesar da quantidade de jogos criados (conseguimos mais um insight incrível). Através desses dados, também, é possível bater o martelo sobre o gap de jogos para o público de faixa etária acima de 18 anos, pois existe muita gente jogando os poucos jogos disponíveis (emoticon da cabeça explodindo). Agora vamos deixar esses temas de lado e vamos falar sobre a quantidade de jogadores permitidos em cada jogo, você acha isso importante?


![Quantidade de jogos por quantidade de jogadores](https://lh3.googleusercontent.com/6PmXtzIkBNHxcEm5l4DV0uuoqTs91IlxhS8UuLGPcjXwD4c3SMEM2FLaXdFuVtgL82lFthMjFqTHpA0_drCME3aqahweC45PKX1fJmqnWMQirbS8KYjB9Y3IbDb4fFJ7j3agYi3U)


No gráfico acima podemos ver que a quantidade de jogos de dois a cinco jogadores é bem alta, provavelmente por conta que há mais Jogos Expert no ranking e eles, geralmente, permitem uma quantidade menores de jogadores. Mas será que é isso que o público mais gosta?


![Quantidade de avaliações por quantidade de jogadores](https://lh4.googleusercontent.com/B5ehmD7ogkhWcXn5MFT7VKZgx0vFOpwTsU6BFnPCTzejc5VIeJYE1jI4xAWC5ymKHO2WkadYTp6lLinckOO5XYNAEj7yMTZrnniGBRqYAdniQnN33CmJOY5MLkV6XYS5l_zBrLwU)


O gráfico acima é bem interessante, ele demonstra que existem muitos usuários que jogam jogos solo (emoticon de carinha triste) e demonstra que jogos com muitas pessoas são muito mais jogados, como os famosos party games! Ou seja, há evidências que implicam que existe um gap para jogos solo e party games no mercado nacional.


![Gráfico de densidade sobre o tempo de duração média das partidas](https://lh5.googleusercontent.com/ysknenaNqVul7qIBHDSwzHNWDXeQxcpWlw9xqyTcistd32YlBKMPhxVeDG0BK988CLi9uOJbR7O_wnBWBa0CsljhWMhl-aYwWa0dwCXEyBx4UHseFecihPCFAG2fyrZbRrSrK3nm)


Sobre o tempo de duração de cada partida, o gráfico acima demonstra que mesmo que existam mais jogos Experts no mercado nacional, ainda assim, a maioria dos jogos possui um tempo de duração menor que 75 minutos. Isso pode indicar que o público aceita melhor jogos que são mais "rápidos".


Mas e para você, que não é designer de jogos, o que eu tenho para lhe oferecer?

![Quantidade de jogos por designer](https://lh4.googleusercontent.com/aCjlwaUX0uhQeRQPv6utPzdXLxed2UIK-Jt_tK36AmzNzeQE8hrtCL5c4cWVphci4LWEeDYnLo-j-drHdjNis60uLDKT1eLsva1dm1mxWrmLXrcf8qZ7HLzS4QdFi0Pn7_ARzVPt)


Que tal falarmos dos designers? No gráfico acima temos os designers que possuem mais jogos ranqueados na Ludopedia (os top 50). Isso significa que, se você está com dúvida de que jogo comprar, uma boa pedida seria escolher o jogo de algum designer que possui o maior número de jogos no ranking. Mas será que quantidade é sinônimo de qualidade?


![Nota ponderada em relação ao ranking e aquantidade de jogos por designer](https://lh5.googleusercontent.com/vf4kd-qRmrc5wUoLXYwhO-wYBG_K1rKpeIrD4GocrsuNanOaZMmYOh12qMWEdNvh_N3n6gR-2tkRCD-lcgGpCh9oxNd-tPh2TrDfVIE66rNQdAdJic4kVTaijLd65taJkq77v9vx)


Será que o gráfico acima consegue demonstrar, de forma mais efetiva, quais são os melhores designers de board games da Ludopedia??? É interessante ver como o Corey Konieczka subiu várias posições nesse gráfico em relação ao anterior. E para você, quem é o melhor, Corey Konieczka, Stefan Feld ou Vlaada Chvátil?


Agora, por fim, vamos falar do assunto mais divertido, mecânicas!


![Quantidade de jogos por mecânica](https://lh6.googleusercontent.com/jpY9kn4Wbpzctvp-dSpZw-yjGwvVYqo7rNfIklG6jkmVORVP7mzti4SkOlcw_HNMMAwZEXeJVJju_iXphMg-Kt9mXih5agAPerL6BlEC0LX4jZutKSR9obdBLZZSri_BzxYRXTJ2)


O gráfico acima mostra as mecânicas mais usadas nos jogos ranqueados na Ludopedia. Será que é a mecânica que define se um jogo vai ou não ter uma boa colocação no ranking? Parece que a mecânica que as pessoas mais gostam é a gestão de mão e a que menos gostam é a de sistema por impulsos!


![Nota média do ranking por mecânica](https://lh5.googleusercontent.com/kgpSucaBu4Dp8PhRCRho2xcUlzUkbGsQML27uQWvkGvKAlT5suRMscZRfAny45o34XS0Y2WVct78d9OFf5dAMqa74y-TEtkuKee0AIYz3wdzWcBsIJck1st3XLFXoELFzpEME8yC)


Bem, de acordo com o gráfico acima, o que mais me surpreende é que, apesar da mecânica de gestão de mão ser a mais comum entre os designers de jogos de tabuleiro, ela não é uma mecânica tão querida assim pelo público. Enquanto que a mecânica de Jogadores com diferentes habilidades ainda está entre as primeiras colocadas.


![Quantidade média de avaliações por mecânica](https://lh3.googleusercontent.com/jwD0gD8Qj1GHMcFBu27-borT48UVi2A11r5hlzJ6koJkOP5mykN3o5yqpFi145rL4Kk0-shsONU0golZS9Np-rCJ79ydcD8i4ehOt1rGQ6ZvIb4FxdDcNYa2zTNU3BYVCkIfHdF9)

E é agora que seu cérebro explode de vez! De acordo com o gráfico acima, aquelas mecânicas que estão mais relacionadas a jogos de RPG e party games são as mais jogadas! 


![Frequêcia do conjunto de mecânicas em jogos](https://lh3.googleusercontent.com/-9bp3XqTAtQGzuQgrH7Gblb-OOmq_XEpIAjThb3dDaYLZ50_aJLsoWU-uhG2HnVrJ7L76_y_H8r-MK0HGN3qiN_WE6WikUHMcSIl8F8SBFeO3vH0-LcaOsHQinAH9lH6ZOLVbfvJ)


Agora quais são as mecânicas que mais ocorrem juntas? O gráfico acima mostra isso! (o gráfico só mostra os 50 primeiros). Como a gestão de mão é a mecânica mais presente nos jogos, é normal que ela apareça mais vezes em conjuntos com outras mecânicas. Porque não damos uma olhada nos jogos que contém o conjunto mais frequente?


![10 jogos mais bem colocados no ranking com Seleção de Cartas e Gestão de Mão](https://lh4.googleusercontent.com/2Xb4RXBbroTY5LFCYm-p5eQW-_o-F05FdLm0klkbq0jyNIqPgjkotlxeSFEGZpcXjDPpWLwQ1ID4zrSCx6Pi0GjN0Dp8SCr6gMuCBRGQNVcgf9f30emRGsYTt5Qbjxz9bDFnViQP)


E no conjunto de mecânicas menos frequente?


![10 jogos mais bem colocados no ranking com Seleção de Cartas e Alocação de Trabalhadores](https://lh5.googleusercontent.com/xxQRnRwH2h2_dvjDMkKwJ6FJ74TY2MS9WCAIX8sqgMRbA4kEh0jb2e-dqry0LjDRJL1scPgQkwauxAN65Mk5ilQgFPaFdkRVM7gwUJ0VPbZAYIT-vuFIWrjUUF-W1Pyk7u2h3qyC)


Termino por aqui essa análise rápida dos jogos ranqueados na Ludopedia! Obrigado por embarcarem nessa junto comigo!
