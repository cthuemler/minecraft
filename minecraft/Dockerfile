FROM eclipse-temurin:11

WORKDIR /minecraft

RUN curl -JLO "https://api.modpacks.ch/public/modpack/93/2114/server/linux" && chmod +x serverinstall_93_2114

RUN ./serverinstall_93_2114

RUN sed -i "s|-Xmx4096M|-Xmx14336M|g" start.sh
RUN sed -i "s|-Xms2048M|-Xms8192M|g" start.sh

COPY eula.txt eula.txt
COPY server.properties ./

ENTRYPOINT ./start.sh