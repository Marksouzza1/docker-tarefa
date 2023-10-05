Configuração do Jellyfin com Docker Compose
Este guia fornecerá instruções passo a passo sobre como configurar o Jellyfin, um servidor de mídia pessoal de código aberto, usando o Docker Compose. O Docker Compose facilita a criação e gerenciamento de contêineres Docker para aplicativos complexos como o Jellyfin.

Pré-requisitos
Certifique-se de que você tenha os seguintes pré-requisitos instalados em seu sistema:

Docker
Docker Compose
Conhecimento básico de linha de comando
Passos de Configuração
Siga os passos abaixo para configurar o Jellyfin com o Docker Compose:

Crie um diretório para o seu projeto Jellyfin e navegue até ele:

Crie um arquivo docker-compose.yml para definir os serviços necessários. Você pode usar um editor de texto para criar o arquivo e adicionar o seguinte conteúdo:

            version: '3'
            services:
            jellyfin:
            image: jellyfin/jellyfin
            container_name: jellyfin
            volumes:
            - /caminho/para/sua/biblioteca:/config
            - /caminho/para/suas/mídias:/media
            ports:
              - "8096:8096"
              restart: unless-stopped


Certifique-se de substituir /caminho/para/sua/biblioteca pelo caminho absoluto para a pasta onde você deseja armazenar a configuração do Jellyfin e /caminho/para/suas/mídias pelo caminho absoluto para a pasta onde estão suas mídias.

Salve o arquivo docker-compose.yml.

Execute o comando a seguir para iniciar o Jellyfin

          docker-compose up -d

          
O Docker Compose criará um contêiner Jellyfin usando a imagem oficial e mapeará a porta 8096 do contêiner para a porta 8096 do host.

Após a inicialização bem-sucedida, você pode acessar o Jellyfin em http://localhost:8096 em seu navegador.

Durante a configuração inicial, você precisará definir uma senha de administrador e configurar sua biblioteca de mídia.

      
