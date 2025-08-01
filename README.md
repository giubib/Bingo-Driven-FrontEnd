# Bingo-Driven – Front-End

Interface React/Next.js.
(Só dar o *docker up*)

---

## 1) Com Docker Compose


docker compose -f docker-compose.frontend.yml up -d


* UI → [http://localhost:8080](http://localhost:8080)

### Desligar

docker compose -f docker-compose.frontend.yml down



## 2) Docker puro

# garante a rede
docker network inspect my_network >/dev/null 2>&1 || docker network create my_network

# build + run
docker build -t frontend ./Bingo-Driven-FrontEnd

docker run -d --name ui --network my_network \
  -e NEXT_PUBLIC_API_URL=http://api:5000 \
  -p 8080:80 \
  frontend

Deploy Link: https://bingo-driven-front-end.vercel.app

