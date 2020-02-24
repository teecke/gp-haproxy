FROM haproxy:2.1.3-alpine

# Packages
RUN apk add --no-cache certbot

# Copy backup/cleanup scripts
COPY backup /usr/local/bin/backup
COPY cleanup /usr/local/bin/cleanup

# GP service identification
RUN echo "haproxy" > /gp.service
