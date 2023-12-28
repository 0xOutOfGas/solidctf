FROM nginx:1.22-alpine

COPY proxy/eth-jsonrpc-access.js /etc/nginx
COPY proxy/nginx.conf /etc/nginx

COPY genesis.json.template /genesis.json.template
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

#COPY --from=ethereum/client-go:v1.10.26 /usr/local/bin/geth /usr/local/bin/
#COPY --from=ethereum/client-go:v1.13.1 /usr/local/bin/geth /usr/local/bin/
COPY --from=ethereum/client-go:v1.13.7 /usr/local/bin/geth /usr/local/bin/

EXPOSE 8545

ENTRYPOINT ["/entrypoint.sh"]
