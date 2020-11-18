## Example

### Using:

```bash
docker pull freeyeti/dev-in-docker:node-yarn
docker run -p 9000:9000 -v $(pwd):/code -it freeyeti/dev-in-docker:node-yarn bash
```

### Build:

```bash
./build node-yarn
docker push freeyeti/dev-in-docker:node-yarn
```

## Images

### Nodejs and Yarnpkg

`freeyeti/dev-in-docker:node-yarn`

### Python3 with GDAL

`freeyeti/dev-in-docker:python3-gis`

### Python3 with pyspark + GDAL + mapnik

`freeyeti/dev-in-docker:python3-pyspark`