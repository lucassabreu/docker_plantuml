[![](https://badge.imagelayers.io/lucassabreu/plantuml.svg)](https://imagelayers.io/?images=lucassabreu/plantuml:latest 'lucassabreu/plantuml')
[![Docker pulls](https://img.shields.io/docker/pulls/lucassabreu/plantuml.svg)](https://hub.docker.com/r/lucassabreu/plantuml/)
[![Latest Tag](https://img.shields.io/github/tag/lindt/docker_plantuml.svg)](https://hub.docker.com/r/lucassabreu/plantuml/)

# docker_plantuml

Docker Container for [PlantUML](http://plantuml.com)

## Motivation

To use plantuml, it needs to be downloaded, java needs to be installed, graphviz needs to be installed, and these things need to be chained.
This docker container does this for you. And allows you to pipe by default into plantuml, so it's neat for script usage.

## Usage

```sh
cat test.uml | docker run --rm -i lucassabreu/plantuml > test.svg
```

The default will output svg. If png output is wanted, call it like this:

```sh
cat test.uml | docker run --rm -i lucassabreu/plantuml -p -tpng > test.png
```

You can also process multiple files at once using:

```sh
docker run --rm -i -v "$(pwd):/puml" lucassabreu/plantuml -tsvg -progress "/puml/*.puml"
```
