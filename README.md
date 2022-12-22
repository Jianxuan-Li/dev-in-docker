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

### Latest update:

- freeyeti/dev-in-docker:pyinstaller5.7.0-poetry1.3.1
- freeyeti/cedarhill-dev:python3.10-weasyprint
- freeyeti/dev-in-docker:python3.10-gdal3.4.1