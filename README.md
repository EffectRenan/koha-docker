
Instalação docker-compose:
  Faça o download desse repositório: git clone https://codigos.ufsc.br/renan.rocha/koha-ufsc.git
  Navegue até o diretório: cd Koha-UFSC
  Execute: docker-compose up

Variáveis do arquivo docker-compose.yaml:

    Alterações importantes:
      DB_ROOT_PASSWORD e MYSQL_ROOT_PASSWORD: Senha do usuário root para o mariadb
      MASTER_PASSWORD: Senha do usuário master

      Observação: As variáveis DB_ROOT_PASSWORD e MYSQL_ROOT_PASSWORD devem ter o mesmo valor.

    Complementar:
      LIBRARY_NAME: Nome da biblioteca para instalação 
      SLEEP: Tempo de espera para tentar realizar uma nova conexão com o mariadb caso houver erro
      INTRAPORT: Porta que irá hospedar o painel administrativo
      DB_HOST: Nome do container do mariadb (definido em container_name)

      Observação: Caso houver alteração na variável INTRAPORT, esse novo valor deve ser exportado em ports.
      Exemplo INTRAPORT: 5555
        ports:
          - 5555:5555


Acesso administrativo: http://<Endereço ou IP do host>:8080
Credencias de acesso:
    Usuário: koha_<Nome definido em LIBRARY_NAME>, padrão: koha_koha
    Senha: Senha definida na variável MASTER_PASSWORD
