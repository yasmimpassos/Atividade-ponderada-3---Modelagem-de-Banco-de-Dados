# Atividade ponderada 3 - Modelagem de Banco de Dados
![Banco de dados relacional](/assets/banco_de_dados.png)
O banco de dados construído foi pensado com base nos requisitos definidos desde a primeira sprint. Inicialmente, todos os usuários se cadastram como usuários e posteriormente um usuário pode criar uma organização. Além disso, todos podem criar uma oportunidade de voluntariado ou publicação, estando estas relacionadas ou não a uma organização. Por fim, os usuários podem se inscrever ou fazer uma contraproposta em uma oportunidade de voluntariado.

Desse modo, foi construído o banco de dados relacionais pensando em seis tabelas, sendo elas:

- Usuários
    - id (chave primária e chave estrangeira nas tabelas: Organizações, Publicações, Oportunidades, Inscrições e Contrapropostas)
    - nome
    - email
    - data_de_nascimento
    - telefone
    - area_de_interesse
    - motivacao
    - publicar_perfil
    - senha
    - cidade
    - genero
    - linkedin
- Organizações
    - id (chave primária e chave estrangeira nas tabelas: Publicações e Oportunidades)
    - nome
    - cnpj
    - area_de_acao
    - email
    - telefone
    - site
    - linkedin
    - descricao
    - id_usuarios
- Publicações
    - id (chave primária)
    - titulo
    - descricao
    - anexos
    - id_usuario_autor
    - id_organizacao_autora
- Oportunidades
    - id (chave primária e chave estrangeira nas tabelas: Inscrições e Contrapropostas)
    - titulo
    - descricao
    - area_de_atuacao
    - data_de_abertura
    - data_de_fechamento
    - carga_horaria
    - qtd_vagas
    - id_usuario_autor
    - id_organização_autora
- Inscrições
    - id (chave primária)
    - nome
    - objetivo
    - id_usuario
    - id_oportunidade
- Contrapropostas
    - id (chave primária e chave estrangeira nas tabelas: Organizações, Publicações, Oportunidades, Inscrições e Contrapropostas)
    - nome
    - proposta
    - id_usuario
    - id_oportunidade

As relações entre elas são:

- Usuários e Publicações: do tipo 1:N, pois um usuário pode criar várias publicações, mas uma publicação só pode estar relacionada a um usuário de acordo com a nossa regra de negócios.
- Usuários e Organizações: do tipo N:N, pois um usuário pode criar ou participar de várias organizações, assim como uma organização pode ter vários usuários.
- Usuários e Oportunidades: do tipo 1:N, pois um usuário pode criar diversas oportunidades, mas uma oportunidade só pode ser criada por um usuário, conforme a nossa regra de negócios.
- Usuários e Inscrições: do tipo 1:N, pois um usuário pode fazer várias inscrições, mas uma inscrição só pode estar relacionada a um usuário.
- Usuários e Contrapropostas: do tipo 1:N, pois um usuário pode fazer várias contrapropostas, mas uma contraproposta só pode estar relacionada a um usuário.
- Organizações e Publicações: do tipo 1:N, pois uma organização pode ter várias publicações, enquanto uma publicação só pode estar relacionada a uma organização, de acordo com a nossa regra de negócio.
- Organizações e Oportunidades: do tipo 1:N, pois uma organização pode ter várias oportunidades, enquanto uma oportunidade só pode estar relacionada a uma organização, de acordo com a nossa regra de negócio.
- Oportunidades e Inscrições: do tipo 1:N, pois uma mesma oportunidade pode estar relacionada a várias inscrições, mas uma inscrição só pode estar relacionada a uma oportunidade.
- Oportunidades e Contrapropostas: do tipo 1:N, pois uma mesma oportunidade pode estar relacionada a várias contrapropostas, mas uma contraproposta só pode estar relacionada a uma oportunidade.