# Dockerfiles

## About this Repository

This repo is used to store the Dockerfile which can be used to build an
Elasticsearch Docker image. The Dockerfile was generated from the [Elasticsearch
repository](https://github.com/elastic/elasticsearch). Please note that **issues
are disabled on this repo** and that all issues and PRs must be filed in the
[Elasticsearch repository](https://github.com/elastic/elasticsearch).

Elasticsearch is a distributed, RESTful search and analytics engine capable of
solving a growing number of use cases. As the heart of the Elastic Stack, it
centrally stores your data so you can discover the expected and uncover the
unexpected.

# How to use these Dockerfiles
Checkout the repository, and build the docker images by going to the elasticsearch and kibana
directory and running below commands respectively

`docker build -t es_secured:6.6.2 .` and `docker build -t kibana_secured:6.6.2 .`

once you have the images build you can run elasticsearch and kibana using below commands

`docker run -p 9200:9200 -e "ADMIN_PWD=password" -e "discovery.type=single-node" --name elasticsearch  es_secured:6.6.2` and 

`docker run --link elasticsearch:elasticsearch  -p 5601:5601 kibana_secured:6.6.2`

# Change the password to access Kibana UI
You will have to provide the same password in the kibana.yaml file that you provided while running the docker image 
of elastic search.

For more information about Elasticsearch, please visit
https://www.elastic.co/products/elasticsearch.

## Where to get help

- [Elasticsearch Discuss Forums](https://discuss.elastic.co/c/elasticsearch) 
- [Elastic community](https://www.elastic.co/community)
- [Elasticsearch documentation](https://www.elastic.co/guide/en/elasticsearch/reference/master/index.html)

## Where to file issues and PRs for Elasticsearch or the Elasticsearch Docker image

- [Issues](https://github.com/elastic/elasticsearch/issues)
- [PRs](https://github.com/elastic/elasticsearch/pulls)

This software is governed by the [Elastic
License](https://github.com/elastic/elasticsearch/blob/6.4/licenses/ELASTIC-LICENSE.txt),
and includes the full set of [free
features](https://www.elastic.co/subscriptions).

View the detailed release notes
[here](https://www.elastic.co/guide/en/elasticsearch/reference/6.6/es-release-notes.html).
