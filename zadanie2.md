# Budowanie
FROM openjdk:11 AS build

LABEL author="Mateusz Zajaczkowski"

# Katalog roboczy
WORKDIR /app

# Kompilacja
RUN javac Server.java

# Uruchomienie
FROM openjdk:11-jre-slim

# Katalog roboczy
WORKDIR /app

# Kopiowanie skompilowanych plików z poprzedniego etapu
COPY --from=build /app/Server.class .

ENV SERVER_PORT=8080

# Wykonanie polecenia startowego
CMD ["java", "Server"]