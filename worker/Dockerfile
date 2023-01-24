FROM node:16-alpine

WORKDIR /app

COPY package.json .

RUN npm install

COPY . . 

CMD ["npm","run","start"] 
#Only difference in prod file is command : It is npm run start as compared to npm run dev in dev mode. 
#This npm run dev/start does not happen automatically, it is actual scripts that are defined in package.json. Open it and we see under scripts section we have 'dev' and 'start' sections.