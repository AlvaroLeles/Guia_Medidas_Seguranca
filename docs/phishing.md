# Phishing

Ataques de phishing fazem parte da internet desde os anos 90. Quando começou, era possível criar ataques de phishing com facilidade, pois o SMTP (Simple Mail Transfer Protocol, ou Protocolo Simples de Transferência de Correio), utilizado para enviar e receber e-mails, não autenticava o remetente do e-mail. Sendo assim, qualquer pessoa podia mandar um e-mail para qualquer outra, alegando ser quem quisesse e afirmando ser de qualquer organização que quisesse, possibilitando que impostores executasse ataques de phishing.

Em um ataque de phishing bem-sucedido, a vítima confia no e-mail recebido pois acredita que a identidade do suposto remetente na seção "De:" do e-mail está correta. Além disso, a vítima, confiando na veracidade do e-mail, clica em um link que redireciona para um formulário de login em um site falso e inadvertidamente entrega sua senha ao atacante.

A partir disso, a primeira recomendação contra esse tipo de ataque é implementar autenticação de dois fatores ao invés de contar apenas com a senha, fazendo com que seja necessário não apenas saber algo (a senha), mas também ter algo (chave de segurança ou um dispositivo móvel) ou ser algo (utilizando biometria).

## Autenticação de Dois Fatores

As principais razões que impulsionam a necessidade de se usar autenticação de dois fatores são as muitas violações que geram mais credenciais comprometidas, alimentando o conjunto de dados roubados dos atacantes, o que fortalece as próximas tentativas de invadir uma organização. Soma-se a isso o fato de que clientes e funcionários geralmente não escolhem senhas fortes.

Toda organização poderia fazer uso de autenticação de dois fatores com certa facilidade, visto que estão disponíveis no mercado várias opções para tipos de projetos diferentes, como o Microsoft Office 365 e o Slack para ferramentas de produtividade e colaboração, AWS e Azure para serviços em nuvem e o GitHub para repositórios de código-fonte.

Habilitar autenticação de dois fatores utilizando os dispositivos móveis de seus funcionários é recomendável já que a maioria dos funcionários possuem esses dispositivos. Independentemente das prioridades de uma organização, a defesa contra ataques de phishing pode ser rapidamente aprimorada ao habilitar autenticação de dois fatores por meio de aplicativos autenticadores de dispositivos móveis que podem ser baixados na maioria dos celulares.

## Chaves de Segurança

Um dos fatores secundários de autenticação mais bem avaliados até o momento para eliminar ameaças de phishing é o uso de chaves de segurança em hardware.

Similar a um motorista que insere uma chave para ligar um carro, os funcionários utilizam uma chave de segurança em seu ambiente de trabalho (laptops, desktops, celulares) para poderem fazer login em sites e aplicativos da organização. Uma chave de segurança é geralmente um token, similar a um pendrive, que autentica um funcionário apenas quando está conectado e o funcionário toca na chave.

Este guia não tem como objetivo explicar tecnicamente como funciona o processo, mas a essência é que o hardware da chave de segurança é utilizado para gerar uma confirmação autenticada de que o usuário legítimo deseja fazer login em um site específico, e não um criado por um impostor. A assinatura digital gerada pelo hardware da chave de segurança funciona como uma segunda senha que permite apenas ao usuário legítimo fazer login, apenas no site legítimo.

Utilizar abordagens de autenticação de dois fatores no geral não tornam um site à prova de phishing. Os atacantes sempre podem configurar um site falso que encaminha credenciais de um usuário para o site legítimo, força o site legítimo a enviar um código de dois fatores para o usuário como um SMS, e depois solicita que o usuário informe o código de dois fatores no site falso, fornecendo ao atacante ambos fatores necessários para se passar pelo usuário no site legítimo. Porém, fazendo uso de chaves de segurança, como navegador da web verifica o se o nome de domínio do site corresponde ao nome no certificado do site, um atacante precisaria falsificar também o certificado do site falso para enganar a chave de segurança.

Até o momento, as chaves de segurança oferecem a defesa mais eficaz contra phishing. O Google relatou que, após implantar chaves de segurança no início de 2017 para seus mais de 85 mil funcionários, eles não registraram nenhum ataque de phishing bem-sucedido ou invasão de conta mais de um ano depois. Relatou também, em 2019, que as chaves de segurança eram 100\% eficazes contra bots automatizados, ataques de phishing em massa e ataques direcionados.

## Tokens OTP Dedicados

Uma opção para um segundo fator baseado em algo que o usuário tem são tokens OTP (One-Time Password ou Senha de Uso Único), onde, depois que um usuário insere suas credenciais, eles são solicitados a inserir um código gerado por um sistema dedicado. Esse código é unico e válido apenas por um curto período, o que fornece uma camada adicional de segurança.

Códigos OTP permitem que o cliente prove ao servidor que ele conhece uma chave compartilhada usada para gerar criptograficamente um código OTP. Esse código difere a cada vez, mas é baseado na chave compartilhada. Esse processo fornece uma forma dinâmica e temporária de autenticação, uma vez que o código muda regularmente, tornando mais difícil para os invasores preverem ou reproduzirem o código.

Para configurar um OTP, o usuário se registra no servidor e um nome de usuário, senha e uma chave compartilhada são acordados. Uma vez registrado, o usuário pode fazer login com os dois fatores. Primeiro, o servidor solicita um nome de usuário e senha, o primeiro fator. O servidor verifica as credenciais, e se forem consideradas autênticas, o servidor verifica então um segundo fator, o código OTP, único a partir do dispositivo que o gerou.

### Autenticação de Dois Fatores em Aplicativos Móveis

À medida que dispositivos móveis passaram a poder executar aplicativos de software, é compreensível que aplicações que aproveitem do poder computacional desses dispositivos passaram a gerar código OTP. Google Authenticator e Microsoft Authenticator são exemplos de aplicativos autenticadores móveis de dois fatores.

Alguns aplicativos autenticadores oferecem funcionalidades que permitem aos usuários simplesmente aprovar um login ao receber uma solicitação de autenticação via push no celular. Internamente, esses aplicativos fornecem o código de autenticação ao servidor sem a interação direta do usuário, tornando o processo de login mais conveniente. No entanto, quando um atacante obtém acesso às credenciais de um usuário, eles podem persuadir esse usuário a clicar em "aprovar", mesmo quando o usuário não está fazendo login, dando ao atacante acesso à conta. Usuários muitas vezes clicam rapidamente em qualquer coisa que atrapalhe o uso de seus celulares.

Portanto, em ambientes sensíveis, pode valer a pena exigir que os funcionários digitem os códigos dos aplicativos autenticadores, ao invés de simplesmente clicar para aprovar um login.

### OTP Baseado em SMS

Em casos em que o usuário não tem um aplicativo autenticador em seu celular, um servidor pode enviar o código de dois fatores para o celular do usuário via SMS (Short Message Service, ou Serviço de Mensagens Curtas).

Um ponto negativo é que o SMS não é criptografado e pode ser suscetível a ataques man-in-the-middle, onde um terceiro captura dados que em tráfego. Por exemplo, se um usuário possui um malware em seu celular que pode ler todas suas mensagens SMS e consequentemente, todos os códigos de dois fatores enviados por esse método.

### OTP Baseado em E-mail

Outro método de autenticação de dois fatores para fazer login em um site sensível ou corporativo é enviar o código de segundo fator para o e-mail do usuário ao invés do SMS. Se o usuário puder comprovar que pode fazer login em seu e-mail registrado e acessar o código OTP enviado para o e-mail, será permitido fazer o login. Entretanto, se um atacante conseguir comprometer o e-mail do usuário, o atacante também poderá roubar os códigos de dois fatores enviados para o e-mail.

## Autenticação de Múltiplos Fatores

A autenticação de múltiplos fatores se refere ao uso de mais de um fator para autenticação. A autenticação de dois fatores é uma forma de autenticação de múltiplos fatores, porém, mais do que apenas dois fatores podem ser utilizados na autenticação de múltiplos fatores.

Outros fatores que podem ser utilizados ao realizar uma autenticação são:

- Tipo de dispositivo e características de configuração do dispositivo;
- Localização do usuário;
- Comportamento do usuário em aplicativos (por exemplo, com que frequência o usuário acessa um aplicativo);
- Características do usuário (por exemplo, padrões de digitação);
- Impressão digital (TouchID);
- Reconhecimento facial (FaceID).

Dessa forma, mesmo que um atacante consiga roubar as credenciais de um usuário, e também consiga comprometer um código OTP de segundo fator, é possível acreditar que um ou mais fatores adicionais (como os mencionados acima) revelem que na verdade é um invasor tentando fazer login. Por exemplo, se o atacante não usar o mesmo tipo de celular que o usuário legítimo, então, ao incorporar características sobre o dispositivo como parte da verificação de autenticação, a tentativa de login pode ser bloqueada.

## Proteger os Domínios com SPF, DKIM e DMARC

Quando bancos começaram a oferecer serviços aos consumidores online, alguns dos ataques de -phishing mais populares envolviam o envio de e-mails que se faziam passar pelo banco para os consumidores, solicitando que clicasse em um link no e-mail para fazer login no site do banco. O e-mail poderia ser enviado a partir do domínio do banco no campo "De:" do e-mail (por exemplo, "De: Suporte ao Cliente<suporte@banco.com\>"), pois o remetente não é autenticado como parte do SMTP. Usuários que recebem esses e-mails de -phishing tendem a acreditar que um e-mail está realmente sendo enviado pelo banco quando o domínio pode ser facilmente falsificado.

Existem alguns protocolos que dificultam a falsificação de e-mails de organizações. Para evitar que um golpista envie um e-mail ilegítimo se passando por uma organização, é possível utilizar os padrões SPF, DKIM e DMARC.

O SPF (Sender Policy Framework) permite que organizações especifiquem quais endereços de IP estão autorizados a enviar e-mails em nome da organização. A lista de IPs autorizados pode ser adicionada aos registros DNS da organização. Os registros DNS são normalmente usados para traduzir nomes de domínio em endereços IP quando um cliente deseja se conectar a um servidor.

Com o SPF, quando um programa de e-mails recebe uma mensagem, ele pode procurar qual é o endereço IP autorizado correspondente ao domínio do remetente e verificar se o IP real de onde a mensagem foi enviado é o mesmo que o IP listado em seu registro DNS. Se for, o e-mail é considerado válido. Caso contrário, o e-mail é rotulado como spam ou é excluído. O DMARC (Domain-based Message
Authentication, Reporting, and Conformance, ou Mensagem Baseada em Domínio de Autenticação, Relatório e Conformidade) pode ser utilizado para especificar o que um programa de e-mail deve fazer se o endereço IP não corresponder.

Ao invés de apenas autenticar e-mail com base no endereço IP, o protocolo DKIM (DomainKeys Identified Mail) pode ser usado para assinar digitalmente todas as mensagens legítimas originadas de uma organização, utilizando criptografia de chaves públicas e privadas para assinar as mensagens . Os e-mails são assinados usando uma chave provida conhecida apenas pela organização. A chave pública correspondente é publicada nos registros DNS da organização, e os programas de e-mail podem verificar as assinaturas digitais em e-mails assinados com DKIM usando a chave pública.

## Domínios Parecidos

Atacantes podem forjar e-mails de domínios semelhantes. Por exemplo, utilizar "site5eguro.com" ao invés de "siteseguro.com".

Para criar o e-mail de phishing mais convincente possível, pode-se imaginar que um atacante deseje que esse e-mail pareça ser de "siteseguro.com". No entando, se SPF, DKIM e DMARC forem utilizados, um atacante pode ter que recorrer ao uso de um domínio semelhante, como "site5eguro.com" a ponto da diferença não ser percebida rapidamente. Além disso, os atacantes podem aproveitar vários conjuntos de caracteres internacionais para registrar domínios parecidos que tenham caracteres extremamente similares aos caracteres do idioma correspondente, tornando a diferença ainda menos perceptível. Por fim, um atacante pode até criar registros SPF, DKIM e DMARC para os domínios semelhantes a fim de aumentar a legitimidade de seus e-mails de ataque.

Além de proteger seus domínios legítimos contra falsificações, é importante também registrar proativamente o maior número possível de domínios semelhantes e erros ortográficos dos domínios de sua organização. Também é uma boa prática monitorar se e quando atacantes registram domínios semelhantes aos da organização. Como pode haver um número infinito de variações, dados os muitos conjuntos de caracteres internacionais, serviços de monitoramento de marca e domínio podem ser usados para ajudar na detecção de registros de domínios maliciosos.

Uma última dica é ajudar os funcionários a identificar quando os e-mails não são enviados por partes internas legítimas, marcando o e-mails como "externos", inserindo marcações como "[EXTERNO]" na linha de assunto do e-mail. Essas marcações podem ser implementadas identificando mensagens que não tenham uma assinatura DKIM válida pela própria organização como externas.

## Preenchimento de Credenciais e Controle de Conta

Sendo o objetivo de um atacante adquirir credenciais válidas usuários, uma vez obtidas essas informações, eles podem tentar assumir a conta do usuário. Atacantes podem também comprar grandes quantidades de credenciais na {dark web. Mesmo que essas credenciais adquiridas não sejam para um site sensível específico, os usuários tendem a reutilizar as mesmas senhas em vários sites, e as senhas roubadas nas várias violações que já ocorreram podem funcionar nesses sites sensíveis.

Quando os atacantes testam grandes números de credenciais roubadas em sites-alvo, ocorre um ataque chamado "preenchimento de credenciais". Para se proteger desse tipo de ataque é necessário, principalmente, identificar o uso de robôs e verificar o uso por funcionários de senhas roubadas.

A detecção anti robôs identifica tentativas automatizadas de atacantes de usar credenciais roubadas em um site. Algumas empresas como a Cloudflare oferecem soluções de detecção e mitigação anti robôs que não apenas ajudam a detectar tentativas de ataque de preenchimento de credenciais em um site, como também ajudam a lidar com scrapping e controle de contas, que é quando um ataque de preenchimento de credenciais resulta em um login bem-sucedido.

Como os funcionários podem reutilizar as mesmas senhas tanto na rede corporativa quanto em contas pessoais online, é importante identificar quando isso acontece e fazer com que alterem as senhas corporativas. Atacantes inevitavelmente testarão credenciais roubadas na rede corporativa. Tudo que um atacante precisa é encontrar um funcionário que tenha reutilizado tal senha para assumir uma conta na rede corporativa, obter acesso ao e-mail corporativo e depois tentar expandir sua presença na rede usando o conteúdo disponível na caixa de entrada do funcionário comprometido.

Para identificar casos de reutilização de senha, é necessário verificar todas as senhas dos funcionários em dumps de senha da dark web. Alguns serviços online podem ajudar nessa tarefa. É importante também que em cada vez que um funcionário altere sua senha, essa nova senha seja verificada em repositórios de senhas roubadas.

## Gerenciadores de Senhas

Gerenciadores de senhas são aplicativos que funcionários e usuários podem usar para gerar e gerenciar automaticamente senhas fortes e complexas, únicas para cada site que utilizam. Alguns gerenciadores de senhas também tem integração com navegadores, de modo que o gerenciador pode ajudar a verificar se um site é legítimo antes de enviar uma senha para ele. Quando um gerenciador de senhas gera uma senha para um site no momento do registro, ele também pode registrar o domínio do site legítimo. Se posteriormente o usuário clicar em um link para um site impostor, o site impostor não corresponderá ao domínio legítimo, e o gerenciador de senhas pode aconselhar o usuário a não enviar suas credenciais. Como o gerenciador faz essa verificação com técnicas byte a byte, ele não será enganado por domínios parecidos.

Gerenciadores de senhas exigem o uso consistente por parte dos funcionários para cada site online para funcionar como uma defesa eficaz. Para se defender de um ataque de phishing é necessário acertar todas as vezes. Para um atacante ter sucesso, basta um deslize para se ter um comprometimento inicial.

## Defesas Adicionais

Além de defesas e estratégias de mitigação orientadas a tecnologia, existem também defesas e estratégias de mitigação orientadas a processos e pessoas.

### Treinamento e Testes

Um treinamento anti-phishing é um treinamento para funcionários no qual eles são ensinados sobre os sinais comuns a serem observados em e-mails que podem indicar ataques de phishing ou spear phishing. Alguns exemplos desses sinais são domínios desconhecidos ou incorretos usados no remetende ou em links em um e-mail, anexos inesperados ou pedidos que incluem um senso artificial de urgência, como por exemplo, "você precisa responder imediatamente ou sua conta será desativada".

Esse treinamento geralmente é seguido por testes de phishing enviados pela equipe de segurança da organização. Esses testes são elaborados para parecerem com e-mails de phishing de atacantes, com a exceção de serem inofensivos, e possuirem o objetivo de verificar se os funcionários conseguem evitá-los. Se um funcionário abrir um e-mail de teste de phishing, clicar em um link no e-mail, clicar em um anexo ou inserir suas credenciais em um site impostor vinculado ao e-mail, ocorre um momento de aprendizado em que o funcionário é informado de que caiu em um ataque de phishing de teste. Se o funcionário não cai no ataque, mas ao invés disso relata o e-mail à equipe de segurança da organização, é um sinal de que o trinamento anti-phishing está funcionando, e o funcionário está menos suscetível a um ataque deste tipo.

Com treinamento suficiente, os funcionários podem se tornar parte da linha de defesa da organização, sendo o último elemento na detecção de ataques de phishing que não foram filtrados da caixa de entrada dos funcionários por meio de outras contramedidas.

Realizando treinamentos anti-phishing pelo menos uma vez ao ano e enviando testes de phishing periodicamente, deve ser possível medir se os funcionários de uma organização estão realmente se tornando menos suscetíveis a ataques desse tipo ao longo do tempo.

### Verificações de Complexidade de Senha

Alguns sistemas exigem que os funcionários ou usuários definam senhas que atendam a um conjunto de restrições de complexidade como número de caracteres, possuir letras e números, letras maiúsculas e minúsculas ou símbolos especiais.

Essas verificações de complexidade de senha ajudam a evitar que os usuários escolham senhas frequentemente usadas, mas fracas, como "12345678" ou "senha". No entanto, essas verificações de complexidade por si só não são suficientes. Dada a quantidade de combinações que um processador pode tentar em um período relativamente curto, é, de certa forma, fácil realizar ataques de força bruta, onde se descobre a senha apenas por tentar todas as combinações possíveis.

Entretanto, verificações de complexidade de senha não são recomendadas pelas diretrizes do Instituto Nacional de Padrões e Tecnologia, pois levam a um comportamento de senha inadequado a longo prazo. Além disso, sua eficácia contra a maioria dos ataques sofisticados também é baixa. Caso esse tipo de verificação seja utilizado, o ideal é que seja em conjunto com outras defesas.

### Rotação de Senhas

Alguns sistemas exigem que os usuários troquem suas senhas periodicamente. Por exemplo, em algumas empresas, os funcionários devem trocar suas senhas a cada 90 dias. Geralmente, os funcionários consideram essas políticas como uma inconveniência, e elas não são muito eficazes, já que os funcionários tendem a escolher senhas semelhantes às anteriores ou simplesmente alternam entre duas ou três senhas apenas. As orientações do Instituto Nacional de Padrões e Tecnologia também desaconselham esse tipo de prática, pois também leva a um comportamento inadequado de senha a longo prazo.