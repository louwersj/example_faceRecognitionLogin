FROM oraclelinux:7-slim

copy ./frontend-service/containerconfig/localhost.conf /tmp/

RUN yum -y install nginx && \
    yum -y install openssl && \
    #openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout localhost.key -out localhost.crt -config /tmp/localhost.conf && \
    openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout localhost.key -out localhost.crt -subj "/C=NL/ST=Utrecht/L=Utrecht/O=Dis/CN=localhost" && \
    cp localhost.crt /etc/ssl/certs/localhost.crt && \
    cp localhost.key /etc/ssl/private/localhost.key
    
EXPOSE 80 443

CMD [ "ngnix" ]
