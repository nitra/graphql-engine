FROM fedormelexin/graphql-engine-arm64:v2.1.0-beta.2.cli-migrations-v3
RUN apt-get update && apt-get install -y \
    --no-install-recommends \
    tdsodbc \
    postgresql-client-14 \
    && rm -rf /var/lib/apt/lists/* 

# [FreeTDS][SQL Server]Unicode data in a Unicode-only collation or ntext data cannot be sent to clients
ENV TDSVER=7.4

RUN echo "[FreeTDS]\n\
    Description = FreeTDS unixODBC Driver\n\
    Driver = /usr/lib/aarch64-linux-gnu/odbc/libtdsodbc.so" >> /etc/odbcinst.ini