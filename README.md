## Build

```
docker build -t cellxgenevipgateway:latest .
```

## Run

```
docker run -it --rm \
-v ./cellxgene-data:/cellxgene-data \
-p 50015:5005 \
cellxgenevipgateway:latest
```

## base

```
FROM python:3.9

RUN pip install cellxgene-gateway 'MarkupSafe<2.1'

ENV CELLXGENE_DATA=/cellxgene-data
ENV CELLXGENE_LOCATION=/usr/local/bin/cellxgene

CMD ["cellxgene-gateway"]
```