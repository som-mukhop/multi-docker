#Build Phase
FROM node:16-alpine as builder 
WORKDIR /app
COPY ./package*.json ./
RUN npm install
COPY . .
RUN ["npm","run","build"] 

#/app/build --> will have all contents that we want to copy over from build stage to prod state

#Prod Phase
FROM nginx
EXPOSE 3000
#We need to copy the default.conf for nginx inside client to the nginx container
#Here we have the routing details to port 3000.
#Check the default.conf inside client/nginx folder
COPY nginx/default.conf /etc/nginx/conf.d/default.d 
COPY --from=builder /app/build  /usr/share/nginx/html


