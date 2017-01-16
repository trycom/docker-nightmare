# Docker-Nightmare headless node image

A `node:latest` compiled with `nightmare` support running in `xvfb`.

## Usage:

In your project, use this image:

```
FROM ivanvanderbyl/docker-nightmare:latest

ADD . /workspace
```

Then build the image:

```shell
docker build -t myscraper .
```

Run your nightmare script (assuming it was called index.js):

```shell
docker run myscraper:latest --rm index.js
```

### Technical details

- Node is latest from docker hub, so probably 7.2+ at time of writing
- Your script is executed with Xvfb running in the background on display `:99.0` at `1280x2000x24`
- `node` is executed with `--harmony-async-await` flag.
