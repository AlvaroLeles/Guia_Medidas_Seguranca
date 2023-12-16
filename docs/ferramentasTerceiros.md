# Ferramentas de Terceiros

Muitas violações de dados começam com comprometimentos envolvendo terceiros. Dificilmente uma organização consegue funcionar completamente sem utilizar nenhuma ferramenta de terceiros. Terceiros se enquadram como fornecedores ou parceiros e geralmente, quanto maior a organização, mais ela pode depender de terceiros. Um exemplo é o vazamento de dados que ocorreu na organização SolarWinds, em 2021, onde aproximadamente 18 mil organizações que tinham a SolarWinds como terceira podem ter sido afetadas.

Se um terceiro tiver acesso a dados ou acesso à rede e esse terceiro for comprometido, a organização que está trabalhando com esse terceiro provavelmente será comprometida também. Se um terceiro não cumprir com requisitos de segurança, isso pode comprometer os requisitos de segurança da organização em si. Todo terceiro pode se tornar o elo mais fraco.

## Segurança de Fornecedores

O tipo mais comum de terceiro é um fornecedor. Para avaliar e gerenciar o risco devido a fornecedores, é essencial fazer um inventário de todos os relacionamentos com fornecedores de terceiros. Dependendo do que é adquirido deles e da natureza do relacionamento, pode ser necessário avaliar a segurança desse terceiro no momento em que o contrato inicial é criado e periodicamente depois.

Por exemplo, se alguma informação sensível é compartilhada com fornecedores, um vazamento que acometer esse fornecedor pode significar um vazamento na organização, já que a organização é a fonte dos dados vazados.

Alguns pontos que devem ser considerados nas relações com fornecedores são:

- Quais dados serão fornecidos e quais serão recebidos? Esses dados são sensíveis? Dados sensíveis estão sendo fornecidos ao fornecedor? Caso esse fornecedor seja comprometido, a organização também estará comprometida?
- Qual o nível de acesso a recursos da organização que o fornecedor tem? Acesso à rede? Acesso à conta? APIs?

Dependendo das respostas para essas perguntas, é necessário considerar como os dados serão armazenados e criptografados pelo fornecedor, como os dados serão protegidos em repouso e em tráfego, como as organizações se comunicarão, como os segmentos de rede que lidam com dados sensíveis serão segregados do restante da rede do fornecedor.

É recomendável pesquisar sobre um fornecedor antes de fechar contrato com ele, buscando por outros projetos em que o mesmo participou, além de auditorias já realizadas e buscando por feedbacks de outras organizações que já trabalharam com esse fornecedor.

Dependendo do quanto é necessário utilizar dos serviços de um fornecedor, pode ser necessário assinar ou renovar o contrato com esse fornecedor mesmo que alguns requisitos de segurança não estejam sendo cumpridos. Nesses casos, é importante monitorar os serviços que passam por esse fornecedor, assim como os dados, e periodicamente realizar monitoramentos para certificar que os dados continuam seguros ou promover melhorias.

## Desenvolvedores, Parceiros e Clientes

Se uma organização permite que desenvolvedores de terceiros ou parceiros acessem dados sobre os clientes, é importante avaliar e monitorar as atividades desses terceiros.

Embora seja comum e difundido que as práticas de segurança dos fornecedores que recebem dados sensíveis devem ser avaliadas, o mesmo vale para os clientes. Se a organização vende dados para seus clientes e um desses clientes for comprometido, o incidente pode ser atribuído à organização que vendeu os dados. Sendo assim, além de avaliar a segurança de fornecedores, é importante também avaliar a segurança dos clientes antes de fornecer dados a eles.