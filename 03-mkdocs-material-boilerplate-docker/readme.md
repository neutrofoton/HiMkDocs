1. build docker image
   ``` sh
   # build image to run with external config
   docker image build --progress=plain --no-cache -t mkdocsboiler -f Dockerfile-config-external .
   
   # build image to run with internal param
   docker image build --progress=plain --no-cache -t mkdocsboiler -f Dockerfile-config-internal .
   ```
2. Run container
   ``` bash
   # run container using local config (external config)
   docker run -it -p 8000:8000 -v $PWD:/root mkdocsboiler serve --dev-addr 0.0.0.0:8000 --config-file ./mkdocs-config.yml

   # run container usinng config inside the image (internal config)
   docker run -it -p 8000:8000 -v $PWD:/root mkdocsboiler --dev-addr 0.0.0.0:8000
   ```

# Reference
- [peaceiris mkdocs-material-boilerplate version v3.5.3](https://github.com/peaceiris/mkdocs-material-boilerplate)