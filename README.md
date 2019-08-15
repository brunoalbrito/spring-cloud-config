# Spring Cloud Config

Esse projeto tem como objetivo ser um exemplo simples de implementação de um serviço Spring Cloud Config e um serviço Rest que utiliza dele para consumir suas configurações.

## Introdução 

Quando estamos criando um microsserviço o primeiro, o primeiro passo que nos deparamos é como devemos configurar nossa aplicação. Como destacados no 3º tópico (Configurações)  dos 12 Factor, as configurações devem estar em arquivos e não em váriavies de ambiente ou diretamente no código, pois, uma aplicação deve poder ser iniciada sem a dependência de váriavies do sistema. Na stack Spring, muitas configurações ficam no application.properties (ou yml).

Inicialmente essas configurações não mudam, mas existem coisas como a URL de conexão com banco de dados ou features que dependem de flags que indicam qual deve ser sua ação. Para isso ser alterado, é necessário parar a aplicação e fazer um novo deploy com as alterações necessárias.

Afim de solucionar esse problema, precisamos de um remote config. Esse projeto exemplo, traz uma implementação do Spring Cloud Config, que tem como objetivo ser um microsserviço que disponibiliza essas configurações para outros microsserviços utilizarem.  A partir da alteração dessas configurações, com apenas a chamada de um end-point Rest é possível alterar as configurações do projeto em produção. Normalmente os arquivos de configurações são disponibilizados em um versionador, no nosso caso o GitHub. Como indica a imagem a baixo: