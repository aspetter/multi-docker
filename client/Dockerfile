# Build phase in react
FROM node:alpine
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY ./ ./
CMD ["npm", "run", "build"]

# Production hosred on nginx
FROM nginx
EXPOSE 3000
COPY --from=0 /app/build /usr/share/nginx/html
COPY ./nginx/production.conf  /etc/nginx/conf.d/default.conf
