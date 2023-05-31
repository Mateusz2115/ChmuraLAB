Należy podać polecenia niezbędne do:
a. zbudowania opracowanego obrazu kontenera,
docker build -t my_image

b. uruchomienia kontenera na podstawie zbudowanego obrazu,
docker run -p 8080:8080 my_image

c. sposobu uzyskania informacji, które wygenerował serwer w trakcie uruchamiana kontenera
(patrz: punkt 1a),
docker logs my_image

d. sprawdzenia, ile warstw posiada zbudowany obraz.
docker history my_image