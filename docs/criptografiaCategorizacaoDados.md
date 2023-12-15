# Criptografia e Categorização de Dados

Dados podem estar em alguns estados, e cada estado apresenta características e cuidados diferentes. Podem estar em repouso, armazenados em algum local, em movimento, transmitidos pela rede, ou em uso, na memória de um dispositivo, e a confidencialidade de dados considerados sensíveis deve ser protegida em qualquer um desses estados.

O objetivo desta seção é apresentar conceitos sobre a disposição de dados sensíveis em diferentes estados. Para obter informações mais técnicas sobre criptografia, recomenda-se pesquisar e estudar algorítimos de criptografia em materiais bibliográficos ou em centros de recomendações focados na segurança de dados sensíveis, como a OWASP.

## Dados em Repouso

Em incidentes onde dispositivos são perdidos ou roubados, caso os dados armazenados não estejam criptografados, têm-se uma violação de dados. A criptografia de dados armazenados pode ser feita pelo sistema operacional ou pelo próprio disco rígido, criptografando os dados no disco com uma chave de criptografia que não deve ser armazenada de forma clara no dispositivo. Sistemas operacionais modernos oferecem algum tipo de criptografia em nível de armazenamento e ativar essa funcionalidade de criptografia evita que incidentes de perda ou roubo de dispositivos se tornem violações de dados.

Quando a criptografia é usada como uma ferramenta para proteger a confidencialidade dos dados, é de extrema importância escolher o local ideal onde armazenar as chaves de criptografia e decidir quais pessoas terão acesso a elas. Embora sejam mais incomuns, ataques que roubam fisicamente um dispositivo que armazena dados sensíveis ainda existem, portanto, ao utilizar dispositivos que contenham informações sensíveis, é necessário cuidar para que os dados estejam criptografados a nível de disco rígido.

## Dados em Movimento

No momento que que os dados sensíveis estão sendo trafegados de um dispositivo para outro através da rede, é necessário garantir que esses dados não podem ser capturados por agentes externos a essa comunicação. Para isso, pode-se criptografar os dados com uma chave que é conhecida apenas pelas extremidades da comunicação. Os dados são então criptografados antes da transmissão pela rede e só são descriptografados ao serem recebidos pelo interessado legítimo.

Muitos são os protocolos que podem ser utilizados para garantir a integridade dos dados durante o tráfego, mas um dos mais utilizados pelos navegadores e servidores da web é o TLS. Após estabelecer uma conexão de rede, o TLS utiliza uma chave pública que combina com a chave privada conhecida apenas pelas extremidades da comunicação, para criptografar o tráfego de dados nesse canal.

## Dados em Uso

Por fim, é necessário garantir a segurança de dados sensíveis também quando estão em uso. Para isso, recomenda-se não descriptografar dados sensíveis na memória padrão do dispositivo, mas sim deixar para processar esses dados criptografados em um enclave seguro, que é uma região protegida da memória do dispositivo, que apresenta um ambiente de execução confiável, com sua própria CPU e memórias dedicadas. A memória nesse ambiente e os registradores do processador usados no enclave seguro são criptografados com chaves que são inacessíveis fora desse ambiente.