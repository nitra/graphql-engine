# build

For more information, see <https://github.com/nitra/graphql-engine>.

## arm

```bash
docker buildx build arm64/ --progress=plain --platform linux/arm64 --tag nitra/graphql-engine:manifest-arm64

docker buildx build arm64/ --progress=plain --platform linux/arm64 --tag nitra/graphql-engine:manifest-arm64 --push
```

## x86

```bash
docker buildx build amd64/ --progress=plain --platform linux/amd64 --tag nitra/graphql-engine:manifest-amd64

docker run -ti --entrypoint=/bin/sh nitra/graphql-engine:manifest-amd64
```

## update in Registry

auth:

```bash
gcloud auth configure-docker eu.gcr.io
```

stable:

```bash
docker pull hasura/graphql-engine:v2.6.2.debian.amd64
docker tag hasura/graphql-engine:v2.6.2.debian.amd64 eu.gcr.io/abinbev-ua/graphql-engine:v2.6.2
docker push eu.gcr.io/abinbev-ua/graphql-engine:v2.6.2
```

latest:

```bash
docker pull hasura/graphql-engine:v2.6.0-beta.2.debian.amd64
docker tag hasura/graphql-engine:v2.6.0-beta.2.debian.amd64 eu.gcr.io/abinbev-ua/graphql-engine:v2.6.0
docker push eu.gcr.io/abinbev-ua/graphql-engine:v2.6.0
```
