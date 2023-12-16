# Vulnerabilidades de Software

A engenharia de software é uma área considerada por muitos como difícil e exige competências como criatividade, lógica e certas vezes grande complexidade. Soma-se a isso o fato de ser uma área relativamente nova se comparada a outras engenharias como a engenharia civil. A maioria dos governos ainda não adota códigos de desenvolvimento de software seguro e para a maioria dos casos, não é necessário possuir uma licença para desenvolver aplicações de software que sustentam redes elétricas, comércio eletrônico ou sistemas de comunicação, além de outras áreas consideradas de infraestrutura crítica. Desenvolvedores e usuários de software devem ter ciência que todo software possui vulnerabilidades, seja por conta de bugs ou falhas de design.

Em organizações que desenvolvem a própria aplicação, o software pode estar suscetível às chamadas vulnerabilidades de software de primeira parte, ou seja, vulnerabilidades que estão presentes no próprio código da aplicação da organização e que podem ser exploradas por agentes maliciosos.

Já em organizações que utilizam software desenvolvido por terceiros, o que corresponde à maioria delas, é necessário estar atento às vulnerabilidades de software de terceiros. Essas vulnerabilidades podem ser identificadas tanto pela organização desenvolvedora do software quanto por outros pesquisadores de segurança em algum momento após seu lançamento.

## Vulnerabilidades de Primeira Parte

### Fase de Desenvolvimento

Na fase de desenvolvimento de uma aplicação, a melhor prática para identificar proativamente vulnerabilidades de design de segurança é realizar uma revisão do design de segurança do produto. Este processo envolve revisar os documentos de design e arquitetura do produto antes mesmo do desenvolvimento em código começar. Defeitos identificados nesta etapa podem economizar custos de manutenção no futuro, assim como a dor de cabeça causada por um defeito exposto após o lançamento do produto. Uma fonte relevante para agregar segurança ao produto é o Centro IEEE para Design Seguro, que fornece códigos de desenvolvimento para assuntos como internet das coisas e software para dispositivos médicos, além de orientações que auxiliam a evitar falhas de design de segurança em softwares.

Depois do desenvolvimento do código-fonte, testes estáticos de segurança auxiliam a encontrar vulnerabilidades no código sem a necessidade de executá-lo. Vulnerabilidades como estouro de buffer e injeção de código são exemplos de problemas que testes estáticos ajudam a identificar, a partir de características do código-fonte.

Além dos testes estáticos, análises de composição de software também auxiliam na identificação do uso de componentes de terceiros, como bibliotecas ou frameworks, que foram escritos pela própria organização.

Por fim, revisões manuais de código devem ser realizadas por desenvolvedores, sejam eles internos ou externos, para identificar vulnerabilidades no código-fonte. Trechos de código que realizam funções sensíveis à segurança dos dados como manipulação ou criptografia deles precisam ser revisados manualmente. Apesar dessa prática consumir tempo, é necessário alocar um revisor especializado neste processo para identificar vulnerabilidades sutis.

### Fase de Testes

Após o desenvolvimento de um sistema, ele precisa ser testado, seja por testes unitários ou por um conjunto de testes onde o sistema maior tem responsabilidade, como testes de integração. Além destes, testes dinâmicos e interativos de segurança também agregam na busca de vulnerabilidades durante o desenvolvimento do produto.

Testes dinâmicos de segurança têm como objetivo procurar vulnerabilidades executando conjuntos automatizados de testes no código-fonte. Esses testes são considerados como testes de caixa-preta, já que envolvem o envio de entradas para o programa em execução e a observação de saídas, sem envolver uma análise do próprio código em si, ao contrário dos testes estáticos, que são classificados como caixa-branca e procuram por vulnerabilidades analisando o código-fonte.

Testes interativos são semelhantes aos testes dinâmicos, mas ao invés de testar conjuntos de testes automatizados pré elaborados, é combinado testes humanos com os automatizados para tentar encontrar vulnerabilidades. Testes interativos são classificados como caixa-branca já que costumam analisar também o código-fonte, de modo que, ao encontrar uma vulnerabilidade, é possível identificar o local no código que produziu a vulnerabilidade. É importante ter em mente que testes interativos exigem um conjunto abrangente de testes automatizados e manuais para resultar em conclusões assertivas.

Testes de penetração consistem em pessoas qualificadas no assunto de testes que utilizam um conjunto de técnicas de teste, como as dinâmicas ou interativas para tentar encontrar vulnerabilidades na aplicação. Geralmente esse tipo de teste é executado um pouco antes do lançamento do produto e tem como objetivo simular ataques de agentes maliciosos, preparando o produto para o contato com os variados tipos de pessoas que podem utilizar a aplicação.

Integração contínua e implantação contínua (CI/CD) são conceitos que se tornaram muito populares no desenvolvimento de software, promovendo agilidade no desenvolvimento e refatoração de aplicações, além de velocidade na implantação das mesmas. Esses conceitos tratam de pequenas alterações frequentes em repositórios de código e automação na implantação do código nos mais diversos ambientes, automatizando tanto a testagem, fazendo uso de testes contínuos, quanto a implantação do programa em produção.

Ao construir pipelines de CI/CD, os desenvolvedores podem escolher quais ferramentas de testes estáticos e dinâmicos irão utilizar para monitorar as frequentes e contínuas modificações de código em desenvolvimento.

### Fase de Produção

Depois que um projeto de software foi testado e colocado em produção, técnicas de autodefesa da aplicação em tempo de execução podem ser utilizadas para identificar ataques que tentem explorar vulnerabilidades não descobertas pelos desenvolvedores nas fases anteriores. As tecnologias de autodefesa analisam a entrada real dos usuários e monitoram ou bloqueiam ataques realizados.

Nesta fase, também é possível realizar testes de penetração para encontrar novas vulnerabilidades, mas nesse momento, é necessário ter extrema cautela ao fazê-lo, já que a exploração de uma nova vulnerabilidade em ambiente de produção pode colocar os dados reais em risco.

## Vulnerabilidades de Terceiros

Muitos negócios dependem de software hoje em dia, entretanto, todos os softwares possuem bugs, e alguns desses bugs podem representar vulnerabilidades de segurança que precisam ser identificadas. Dessas vulnerabilidades, as de maior gravidades precisam ser corrigidas ou mitigadas o quanto antes, para que uma exploração da vulnerabilidade não aconteça e consequentemente, um vazamento de dados.

### Identificação e Validação

A principal tecnologia necessária para identificar vulnerabilidades em software de terceiros é o escâner de vulnerabilidades. Esses escâneres conseguem analisar a rede e identificar quais máquinas estão em execução e quais softwares estão sendo utilizados nelas. Esse processo é realizado através dos endereços de IP disponíveis na rede escaneada, se comunicando com as aplicações em execução em cada porta desses endereços, obtendo informações sobre as aplicações por meio de respostas e comportamentos. Com base nessas informações, o escâner consegue identificar vulnerabilidades nas aplicações que estão em execução na rede.

Após identificar as vulnerabilidades, é necessário validá-las, para descartar situações de falso positivo. Depois de validada, cada vulnerabilidade precisa ser rastreada, pois deixar de resolver uma vulnerabilidade que seja pode ser o suficiente para que um atacante comprometa o sistema.

Além dos falsos positivos, é preciso lidar também com os falsos negativos, que são situações onde o escâner não detectou uma vulnerabilidade. Para evitar esse tipo de problema, é importante que uma organização faça uso de mais de um escâner simultaneamente em sua rede.

### Priorização

O rastreamento de vulnerabilidades por parte dos escâneres pode resultar na identificação de muitas vulnerabilidades, com isso, se faz necessário priorizar quais vulnerabilidades serão corrigidas primeiro. Para isso deve-se analisar questões como existência da vulnerabilidade em várias organizações simultaneamente, existência de ataques para a vulnerabilidade específica, facilidade de exploração da vulnerabilidade, etc. O mercado oferece uma variedade de produtos que auxiliam as organizações a priorizarem o risco das vulnerabilidades de terceiros, levando em consideração o contexto da arquitetura de rede da organização.

Tendo priorizado as vulnerabilidades, é necessário determinar o esforço necessário para corrigir as vulnerabilidades de maior risco, testar a correção e avaliar o impacto que a implementação dessa correção terá nos usuários e nos sistemas dependentes. É importante considerar de forma cuidadosa esses impactos, pois a correção de uma vulnerabilidade pode exigir um grande esforço em diversas áreas do sistema dependentes do ponto corrigido, podendo ser necessário estimar, desenvolver, testar e implantar novas alterações em ambientes de produção.

### Atualização de Endpoints

Uma classe de vulnerabilidades importante que precisa ser gerenciada são as vulnerabilidades nos pontos finais (endpoint), dispositivos ou aplicações finais em um canal de comunicação. Fornecedores de sistemas operacionais por exemplo, frequentemente identificam vulnerabilidades em seus softwares.

Correções para corrigir vulnerabilidades em endpoints devem ser implementadas regularmente. Sistemas operacionais disponibilizam atualizações ou correções regularmente, e estas devem ser aplicadas nos endpoints da rede com certa frequência, para garantir que uma vulnerabilidade que já possui correções disponíveis não se mantenha exposta na rede por muito tempo.