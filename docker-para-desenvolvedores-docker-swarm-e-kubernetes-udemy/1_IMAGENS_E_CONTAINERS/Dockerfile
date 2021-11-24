FROM node

WORKDIR /app

COPY package*.json .

RUN npm install

# COPIA TUDO O QUE ESTÁ DO DIRETÓRIO PARA O DIRETÓRIO DO CONTAINER
COPY . .

EXPOSE 3000

CMD ["node", "app.js"]