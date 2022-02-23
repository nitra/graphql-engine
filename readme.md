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
