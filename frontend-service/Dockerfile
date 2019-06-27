FROM oraclelinux:7-slim

copy ./containerconfig/localhost.conf /tmp/

RUN yum -y install nginx && \
    yum -y install openssl && \
    openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout localhost.key -out localhost.crt -config localhost.conf && \
    
    

EXPOSE 80 443

CMD [ "ngnix" ]
