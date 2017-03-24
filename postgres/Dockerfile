FROM postgres:9.4

ENV POSTGIS_MAJOR 2.1
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        postgresql-9.4-postgis-2.1 \
    && rm -rf /var/lib/apt/lists/*


ENTRYPOINT ["docker-entrypoint.sh"]
EXPOSE 5432
CMD ["postgres"]