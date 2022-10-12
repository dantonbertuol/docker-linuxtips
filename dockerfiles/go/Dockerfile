# Utiliza o golang com o nome 'buildando' (primeiro stage)
FROM golang AS buildando

WORKDIR /app
ADD . /app
RUN go build -o meugo

# A partir daqui usa a distro alpine (segundo stage)
FROM alpine

WORKDIR /giropops
# Ira copiar a partir do 'buildando' o app meu go compilado
# para giropops no alpine
COPY --from=buildando /app/meugo /giropops/
ENTRYPOINT ./meugo