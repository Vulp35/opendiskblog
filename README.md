## About

This site uses [Docker Compose](https://docs.docker.com/compose/install/) and the [squidfunk/mkdocs-material](https://hub.docker.com/r/squidfunk/mkdocs-material/) image.


## How to preview the site[^1]

To run the docker container in preview mode:
```BASH
docker compose up
```

This will use the `compose.yaml` to run MkDocs as a live preview server on the Docker host port `8000`.

[mkdocs-material preview as you write](https://squidfunk.github.io/mkdocs-material/creating-your-site/#previewing-as-you-write)

## How to build the site[^2]

To actually build the `/site` folder, use the following:
```BASH
docker compose run --rm mkdocs-material build
```

This will build the static site from the Markdown files.


## How to publish to GitHub Pages[^3]



## Adding other plugins

### From Getting Started[^4]

Material for MkDocs only bundles selected plugins in order to keep the size of the official image small. If the plugin you want to use is not included, you can add them easily. Create a `Dockerfile` and extend the official image:


```Dockerfile
FROM squidfunk/mkdocs-material
RUN pip install mkdocs-macros-plugin
RUN pip install mkdocs-glightbox
```

Next, build the image with the following command:

```bash
docker build -t squidfunk/mkdocs-material .
```

The new image will have additional packages installed and can be used exactly like the official image. 

## References

Other inks with useful documentation:
[mkdocs-material setup](https://squidfunk.github.io/mkdocs-material/setup/)
[mkdocs-material getting started](https://squidfunk.github.io/mkdocs-material/getting-started/)
[mkdocs-material plugins](https://squidfunk.github.io/mkdocs-material/plugins/)
[mkdocks-material referance](https://squidfunk.github.io/mkdocs-material/reference/)
[Deploy to Custom Domain](https://www.mkdocs.org/user-guide/deploying-your-docs/#custom-domains)


[^1]: [mkdocs-material preview as you write](https://squidfunk.github.io/mkdocs-material/creating-your-site/#previewing-as-you-write)

[^2]: [mkdocs-material building your site](https://squidfunk.github.io/mkdocs-material/creating-your-site/#building-your-site)

[^3]: [mkdocs-material publish to github pages](https://squidfunk.github.io/mkdocs-material/publishing-your-site/#github-pages)

[^4]: https://squidfunk.github.io/mkdocs-material/getting-started/#with-docker
