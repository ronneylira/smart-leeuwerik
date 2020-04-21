FROM debian:stable-slim
WORKDIR /app
EXPOSE 80 443

VOLUME ./opt/urserver/

RUN apt-get update
RUN apt-get install wget -y
RUN apt-get install libx11-6 -y
RUN apt-get install libxext6 -y
RUN wget -O urserver.deb http://www.unifiedremote.com/d/linux-x64-deb
RUN dpkg -i urserver.deb 
RUN ls -R ./opt/

COPY entrypoint.sh ./entrypoint.sh
RUN chmod +x entrypoint.sh
ENTRYPOINT ["./entrypoint.sh"]