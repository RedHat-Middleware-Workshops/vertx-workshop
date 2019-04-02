# Build

To build the documentation:

* Using Fish:

```
docker run -it -v (pwd):/documents/ asciidoctor/docker-asciidoctor "./build.sh" "html"
```

* Using Bash

```
docker run -it -v $(pwd):/documents/ asciidoctor/docker-asciidoctor "./build.sh" "html"
```
    
    



* Using Workshopper local
```
cd workshopper-guides
docker run -it --rm -p 8080:8080 -v $(pwd):/app-data \
      -e LOG_TO_STDOUT=true \
      -e CONTENT_URL_PREFIX="file:///app-data" \
      -e WORKSHOPS_URLS="file:///app-data/_workshop-guides-che.yml" \
      quay.io/osevg/workshopper:latest
```