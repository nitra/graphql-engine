FROM fedormelexin/graphql-engine-arm64:v2.0.10.cli-migrations-v3
RUN apt-get update && apt-get install -y \
    --no-install-recommends \
    tdsodbc \
    && rm -rf /var/lib/apt/lists/* 

RUN echo "[FreeTDS]\n\
    Description = FreeTDS unixODBC Driver\n\
    Driver = /usr/lib/aarch64-linux-gnu/odbc/libtdsodbc.so" >> /etc/odbcinst.ini