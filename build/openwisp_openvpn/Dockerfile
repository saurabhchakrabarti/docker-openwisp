FROM kylemanna/openvpn:latest

RUN apk add --no-cache tzdata postgresql-client supervisor && \
    rm -rf /var/cache/apk/* /tmp/*
CMD ["sh", "init_command.sh"]
EXPOSE 1194

ENV MODULE_NAME=openvpn \
    DASHBOARD_APP_SERVICE=dashboard \
    DASHBOARD_INTERNAL=dashboard.internal \
    API_INTERNAL=api.internal \
    DB_NAME=openwisp_db \
    TZ=UTC \
    DB_USER=admin \
    DB_PASS=admin \
    DB_HOST=postgres \
    DB_PORT=5432 \
    DB_SSLMODE=disable \
    DB_SSLKEY=None \
    DB_SSLCERT=None \
    DB_SSLROOTCERT=None \
    DB_OPTIONS={} \
    VPN_NAME=default

COPY ./common/init_command.sh \
     ./common/utils.sh \
     ./openwisp_openvpn/ ./
