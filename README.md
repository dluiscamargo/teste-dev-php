####Linux Ubuntu 20.04.6 LTS## 
- - Ambiente de desenvolvimento:
	- PHP v8.3.16
	- Composer
	- nvm
	- NODE
	- velet-linux
	- takeout: banco de dados, redis, mailhog,meilisearch
	- MySQL
	- vim
	- Docker
	
- Install php: 'sudo apt-install php -y'

- Install composer [Composer]'(https://getcomposer.org/download/)'

- Install nvm

- Install node nvm install node

- Install velet-linux: https://cpriego.github.io/valet-linux/index#installation (antes de instalar o valet linux pare o APACHE2) 

  "Valet Linux é um ambiente de desenvolvimento Laravel para Linux minimalistas. Sem Vagrant, sem arquivo /etc/hosts. Você pode até compartilhar seus sites publicamente usando túneis locais. O Valet Linux configura seu sistema para sempre executar o Nginx em segundo plano quando sua máquina for iniciada. Em seguida, usando DnsMasq, o Valet faz proxy de todas as solicitações no domínio *.test para apontar para sites instalados em sua máquina local.Em outras palavras, um ambiente de desenvolvimento Laravel extremamente rápido que usa cerca de 7 MB de RAM. Valet Linux não é um substituto completo para Vagrant ou Homestead, mas oferece uma ótima alternativa se você deseja princípios flexíveis, prefere velocidade extrema ou está trabalhando em uma máquina com uma quantidade limitada de RAM."	
  
- Install docker https://docs.docker.com/engine/install/ubuntu/

- Install o Takeout https://github.com/tighten/takeout
   - composer global require "tightenco/takeout:~2.9"
   - tekeout enable mysql
   - tekeout enable redis
   - takeout enable mailhog
   - takeout enable meilisearch
   - takeout list (lista todas as maquinas virtuais)
   
- "Takeout é uma ferramenta CLI para criar pequenos contêineres Docker, um para cada uma das dependências do seu ambiente de desenvolvimento. Ele foi criado para ser pareado com uma ferramenta como Laravel Valet . Atualmente, ele é compatível com macOS, Linux, Windows 10 e WSL2. Com takeout enable mysqlo MySQL em execução, você nunca mais precisará se preocupar em gerenciar ou consertar o Homebrew MySQL. Mas você também pode habilitar facilmente ElasticSearch, PostgreSQL, MSSQL, Mongo, Redis e mais, com um comando simples. Para uma lista atual de serviços, veja as classes disponíveis neste diretório: https://github.com/tighten/takeout/tree/main/app/Services"

"WARNING: Error loading config file: /home/user/.docker/config.json -stat /home/user/.docker/config.json: permission denied", para rodar o tekeout enable.
 - https://docs.docker.com/engine/install/linux-postinstall/
        - sudo groupadd docker
        - sudo usermod -aG docker $USER
        - newgrp docker
        - docker run hello-world
        - sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
        - sudo chmod g+rwx "$HOME/.docker" -R
------------------------------------------------------------------------------------------
Laravel install:

- composer global require laravel/installer (install laravel)
- laravel new testDaniel (Laravel v11.38.2 (PHP v8.3.16))
	- Would you like to install a starter kit? 
	  R= Laravel Breeze 
	
	- Which Breeze stack would you like to install? 
	  R= Blade with Alpine
        
        - Would you like dark mode support?
          R= no
        
        - Which testing framework do you prefer?
          R= PHPUnit
        
        - Which database will your application use?
          R= MySQL
        
        - Default database updated. Would you like to run the default database migration
          R= Yes
        
        - The database 'testdaniel' does not exist on the 'mysql' connection.  
          Would you like to create it? 
          R= Yes
         
        - Creating migration table ..................................... 40.73ms DONE
          INFO  Running migrations.  
           0001_01_01_000000_create_users_table ........................ 139.57ms DONE
           0001_01_01_000001_create_cache_table ......................... 55.32ms DONE
           0001_01_01_000002_create_jobs_table ......................... 144.03ms DONE
            - Login/Register (url: http://testdaniel.test/dashboard)
         - INFO  Discovering packages.  

	  laravel/breeze ....................................................... DONE
	  laravel/pail ......................................................... DONE
	  laravel/sail ......................................................... DONE
	  laravel/tinker ....................................................... DONE
	  nesbot/carbon ........................................................ DONE
	  nunomaduro/collision ................................................. DONE
	  nunomaduro/termwind .................................................. DONE
               	  	   
----------------------------------------------------------------------------------------
- php artisan migrate
- sudo apt install php-redis
- composer require laravel/horizon (test redis)
  - php artisan horizon(url: http://testDaniel.test/horizon/dashboard)
- composer require laravel/breeze --dev
- php artisan breeze:install (test DB)
- php artisan migrate:fresh
	0001_01_01_000000_create_users_table ........................ 177.67ms DONE
  	0001_01_01_000001_create_cache_table ......................... 64.62ms DONE
  	0001_01_01_000002_create_jobs_table ......................... 152.16ms DONE
  	2025_01_21_133520_create_personal_access_tokens_table ........ 93.75ms DONE
  	
----------------------------------------------------------------------------------------
Extras:
 - install Z Shell
  - sudo apt install zsh -y 
 
 - install ohmyzsh
  - https://ohmyz.sh/ 
  - sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" 
  
  - Spaceship Prompt: https://github.com/spaceship-prompt/spaceship-prompt 
  - git clone https://github.com/spaceship-prompt/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1
  - ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
  - vim ~/.zshrc alterar (ZSH_THEME="test") para ZSH_THEME="spaceship" :wq no vim para salvar
  resultado: 
  	➜ vim ~/.zshrc   
       ~/code/testDaniel via 🐘 v8.3.16 took 2m 7,6s …


----------------------------------------------------------------------------------------



## Teste para Desenvolvedor PHP/Laravel

Bem-vindo ao teste de desenvolvimento para a posição de Desenvolvedor PHP/Laravel. 

O objetivo deste teste é desenvolver uma API Rest para o cadastro de fornecedores, permitindo a busca por CNPJ ou CPF, utilizando Laravel no backend.

## Descrição do Projeto

### Backend (API Laravel):

#### CRUD de Fornecedores:
- **Criar Fornecedor:**
  - Permita o cadastro de fornecedores usando CNPJ ou CPF, incluindo informações como nome/nome da empresa, contato, endereço, etc.
  - Valide a integridade e o formato dos dados, como o formato correto de CNPJ/CPF e a obrigatoriedade de campos.

- **Editar Fornecedor:**
  - Facilite a atualização das informações de fornecedores, mantendo a validação dos dados.

- **Excluir Fornecedor:**
  - Possibilite a remoção segura de fornecedores.

- **Listar Fornecedores:**
  - Apresente uma lista paginada de fornecedores, com filtragem e ordenação.

#### Migrations:
- Utilize migrations do Laravel para definir a estrutura do banco de dados, garantindo uma boa organização e facilidade de manutenção.

## Requisitos

### Backend:
- Implementar busca por CNPJ na [BrasilAPI](https://brasilapi.com.br/docs#tag/CNPJ/paths/~1cnpj~1v1~1{cnpj}/get) ou qualquer outro endpoint público.

## Tecnologias a serem utilizadas
- Framework Laravel (PHP) 9.x ou superior
- MySQL ou Postgres

## Critérios de Avaliação
- Adesão aos requisitos funcionais e técnicos.
- Qualidade do código, incluindo organização, padrões de desenvolvimento e segurança.
- Documentação do projeto, incluindo um README detalhado com instruções de instalação e operação.

## Bônus
- Implementação de Repository Pattern.
- Implementação de testes automatizados.
- Dockerização do ambiente de desenvolvimento.
- Implementação de cache para otimizar o desempenho.

## Entrega
- Para iniciar o teste, faça um fork deste repositório; Se você apenas clonar o repositório não vai conseguir fazer push.
- Crie uma branch com o nome que desejar;
- Altere o arquivo README.md com as informações necessárias para executar o seu teste (comandos, migrations, seeds, etc);
- Depois de finalizado, envie-nos o pull request;


