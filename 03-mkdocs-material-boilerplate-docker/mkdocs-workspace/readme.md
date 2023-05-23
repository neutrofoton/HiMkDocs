Building container in this path to simulate using mkdocs-config.yml in the built in image.

``` bash
# run container usinng config inside the image
docker run -it -p 8000:8000 -v $PWD:/root mkdocsboiler --dev-addr 0.0.0.0:8000
```