# Dio-Projeto-Modelagem-de-Dados
Dio Projeto Modelagem de Dados

1. Tabela tabela_usuario
Armazena os dados dos usuários, incluindo:
id_usuario: Identificador único para o usuário (chave primária).
nome_completo: Nome completo do usuário.
usuario: Nome de usuário (login).
email: Endereço de email do usuário.
data_nascimento: Data de nascimento do usuário.
senha: Senha para o login.
data_cadastro: Data em que o usuário se cadastrou.
Essa tabela é a principal fonte de informações sobre os usuários e está relacionada com outras tabelas por meio do id_usuario.

2. Tabela tabela_img_usuario
Armazena imagens de perfil dos usuários:
id_usuario: Referência opcional ao usuário (chave estrangeira relacionada à tabela tabela_usuario).
numero_img: Identificador único da imagem (chave primária).
img_usuario: O arquivo de imagem em formato BLOB (Binary Large Object).
Essa tabela pode armazenar imagens de perfil dos usuários, com a relação entre usuários e suas imagens definida pela chave estrangeira id_usuario.

3. Tabela tabela_receitas
Armazena informações sobre as receitas criadas pelos usuários:
cod_receitas: Código único para cada receita (chave primária).
id_usuario: Referência ao usuário que criou a receita (chave estrangeira).
categoria: Categoria da receita (exemplo: sobremesa, prato principal).
nome_receita: Nome da receita.
data_publicacao: Data de publicação da receita.
porcao: Quantidade de porções que a receita rende.
tempo_preparo: Tempo necessário para o preparo da receita.
mod_preparoX_var: Até cinco etapas para o modo de preparo.
ingredientes_mpX_var: Até cinco campos para os ingredientes.
Esta tabela gerencia todas as informações relacionadas às receitas criadas e publicadas pelos usuários.

4. Tabela tabela_img_receita
Armazena imagens relacionadas às receitas:
cod_img: Código único para a imagem (chave primária).
cod_receitas: Referência à receita à qual a imagem está associada (chave estrangeira).
titulo_img_receita: Título ou descrição da imagem.
img_receita: Arquivo de imagem em formato BLOB.
Esta tabela permite associar uma ou mais imagens às receitas.

5. Tabela tabela_comentario
Armazena os comentários feitos pelos usuários sobre as receitas:
cod_comentario: Código único para o comentário (chave primária).
id_usuario: Referência ao usuário que fez o comentário (chave estrangeira).
data_comentario: Data em que o comentário foi feito.
comentario: Texto do comentário (até 400 caracteres).
Esta tabela permite que os usuários façam comentários nas receitas, criando interações na plataforma.

6. Relacionamentos entre Tabelas
Chaves Estrangeiras (Foreign Keys):
A tabela tabela_img_usuario está relacionada à tabela_usuario por meio do id_usuario.
A tabela tabela_receitas está relacionada à tabela_usuario por meio do id_usuario, indicando o autor da receita.
A tabela tabela_img_receita está relacionada à tabela_receitas por meio do cod_receitas, associando imagens às receitas.
A tabela tabela_comentario está relacionada à tabela_usuario por meio do id_usuario, indicando o autor do comentário.
Resumo
Este projeto cria uma estrutura de banco de dados robusta para uma plataforma de compartilhamento de receitas, com funcionalidades que permitem o gerenciamento de usuários, imagens de perfil e receitas, além de permitir que os usuários façam comentários nas receitas.
