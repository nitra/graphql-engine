FROM hasura/graphql-engine:v2.8.4.cli-migrations-v3.ubuntu.arm64
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
