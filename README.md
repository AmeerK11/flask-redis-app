# Flask + Redis Docker App
ITCS 6190 - Hands-On L3

## What This Is
A simple web app built with Flask that tracks how many times the page has been visited. It uses Redis to store the count and runs everything through Docker Compose.

## How to Run It

### 1. Set up PostgreSQL
```bash
docker pull postgres
docker run -d -p 5432:5432 --name postgres1 -e POSTGRES_PASSWORD=pass12345 postgres
docker exec -it postgres1 bash
psql -d postgres -U postgres
```

### 2. Start the app
```bash
docker compose up
```

### 3. Open in your browser
```
http://localhost:8000
```

### 4. Shut it down when done
```bash
docker compose down
```

## What I Learned
Going into this I didn't really know much about Docker. I knew it had something to do with containers but that was about it. After going through this I got a much better understanding of how it all fits together you write a Dockerfile to package your app, and then use Docker Compose to get multiple services like Flask and Redis talking to each other. The part that clicked for me was realizing the containers communicate using their service names, not IP addresses. Also got some hands on experience with PostgreSQL which was cool.