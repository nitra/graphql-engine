FROM hasura/graphql-engine:v2.2.0.cli-migrations-v3
RUN apt-get update && apt-get install -y \
    --no-install-recommends \
    tdsodbc \
    wget \
    ca-certificates \
    gnupg \
    && rm -rf /var/lib/apt/lists/* 

# [FreeTDS][SQL Server]Unicode data in a Unicode-only collation or ntext data cannot be sent to clients
ENV TDSVER=7.4

RUN echo "[FreeTDS]\n\
    Description = FreeTDS unixODBC Driver\n\
    Driver = /usr/lib/aarch64-linux-gnu/odbc/libtdsodbc.so" >> /etc/odbcinst.ini

# pg_dump for postrges 14
RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ buster-pgdg main" >>  /etc/apt/sources.list.d/pgdg.list && \
    sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ buster-pgdg main" > /etc/apt/sources.list.d/pgdg.list' && \
    wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add - && \
    apt-get update && apt-get install -y \
    --no-install-recommends \
    postgresql-client-14 \
    && rm -rf /var/lib/apt/lists/* 