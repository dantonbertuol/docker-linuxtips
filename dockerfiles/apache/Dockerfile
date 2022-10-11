FROM debian

# o parametro -y e para atribuir yes automaticamente se pedir confirmacao de instalacao
# todos os comandos no mesmo RUN para executar na mesma camada - cada RUN cria uma camada
RUN apt-get update && apt-get install -y apache2 && apt-get clean

ENV APACHE_LOCK_DIR="/var/lock"
ENV APACHE_PID_FILE="/var/run/apache2.pid"
ENV APACHE_RUN_USER="www-data"
ENV APACHE_RUN_GROUP="www-data"
ENV APACHE_LOG_DIR="/var/log/apache2"

LABEL description="Webserver"

# Quando e mapeado um volume no dockerfile o docker cria automaticamente
# na sua maquina este volume mas com um nome 'estranho' var/lib/docker/volumes
VOLUME /var/www/html/
# Porta 80 do container vai estar em execucao
EXPOSE 80

# Principal processo do container - ira executar quando executar o container
ENTRYPOINT [ "/usr/sbin/apachectl" ]

# Quando e definido um entrypoint que e o processo principal
# O CMD passa a executar somente parametros do processo principal
CMD [ "-D", "FOREGROUND" ]