# Wikibase Streaming Suite 

WDQS is disabled by default

## Features
* Wikibase with exposed SSE RDF streaming endpoint 

## Start with
Rename example-env to .env and edit to your liking

then

´$ docker compose --env-file .env -f docker-compose-streaming.yml up --wait --build --env-file .env '

## Game plan
1) clone all the parts ✅
2) get wikibase-deploy to build (without WDQS) ✅
3) dockerize:
    * [wikidata-query-rdf](https://github.com/wikimedia/wikidata-query-rdf)
      1) done
      2) published fork
      3) published image to docker-hub
    * [eventgate](https://gitlab.wikimedia.org/repos/data-engineering/eventgate)
      1) done
      2) published fork
      3) published image to docker-hub
    * [eventstreams](https://gitlab.wikimedia.org/repos/data-engineering/eventstreams)
      1) done
      2) published fork
      3) published image to docker-hub
    * [KafkaSSE](https://github.com/wikimedia/KafkaSSE)
      1) done
      2) published fork
      3) published image to docker-hub
4) integrate [mediawiki-extensions-EventBus](https://www.mediawiki.org/wiki/Extension:EventBus) into Wikibase somehow
5) integrate the pieces needed for streaming updates into my fork of wikibase suite
6) test the whole thing
7) add health checks to the docker-compose
8) published image to docker-hub
9) celebrate for 3 days 🎉