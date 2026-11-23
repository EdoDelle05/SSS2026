FROM node AS build
WORKDIR /repo

RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*
RUN git clone https://github.com/mmenapace/SomeBankingApp.git .

WORKDIR /repo/frontend

RUN find src/ -type f -exec sed -i 's|http://127.0.0.1:8000|/api|g' {} +

RUN npm i
RUN ./node_modules/.bin/ng build

FROM nginx
COPY --from=build /repo/frontend/dist/SomeBankingFrontend/browser /usr/share/nginx/html/