FROM postgres:alpine

RUN apk add --update ca-certificates postgis

ENTRYPOINT ["docker-entrypoint.sh"]
EXPOSE 5432
CMD ["postgres"]