# Utilizara a imagem do debian
FROM debian

# Label e variavel de ambiente
LABEL app="Giropops"
ENV DANTON="LINDO"

# Comando que sera executado quando a imagem estiver sendo compilada
RUN apt-get update && apt-get install -y stress && apt-get clean

# Comando que ira executar apos a imagem estar em execucao
CMD stress --cpu 1 --vm-bytes 64M --vm 1
