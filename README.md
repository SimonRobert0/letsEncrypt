# letsEncrypt

## Create proxy :
docker network create nginx-proxy

## In docker-compose.yml project file
super-api:
    image: node:latest
    expose:
      - 3636
    ports:
      - 3636:3636
    environment:
        - VIRTUAL_HOST=domaine
        - VIRTUAL_PORT=3636
        - LETSENCRYPT_HOST=domaine
        - LETSENCRYPT_EMAIL=email

networks:
  default:
    external:
      name: nginx-proxy
