version: '3'
services:
  drupal_cont:
    ports: 
      - "8080:80"
    networks:
      - drupalnetwork1
    volumes:
      - ./drupal/:/var/www/html/sites/default/:rw
    image: drupal
    depends_on:
      - postgres_cont
  
  postgres_cont:
    networks:
      - drupalnetwork1
    volumes:
      - ./postgres/:/docker-entrypoint-initdb.d/
    environment:
      - POSTGRES_PASSWORD=123
    image: postgres:9.6.2-alpine
    volumes:
      - pgdata:/var/lib/postgresql/data
volumes:
  pgdata:
networks:
  drupalnetwork1:
    driver: bridge
