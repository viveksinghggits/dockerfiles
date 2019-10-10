##################
### BASE IMAGE ###
##################
FROM elasticsearch:6.6.2
WORKDIR /usr/share/elasticsearch
ENV PATH /usr/share/elasticsearch/plugins/search-guard-6/tools:/usr/share/elasticsearch/bin:$PATH
RUN ln -sf /etc/pki/ca-trust/extracted/java/cacerts /opt/jdk-11.0.1/lib/security/cacerts
COPY config/elasticsearch.yml config/log4j2.properties config/
RUN elasticsearch-plugin install -b https://releases.floragunn.com/search-guard-6/6.6.2-25.5/search-guard-6-6.6.2-25.5.zip
RUN wget https://downloads.search-guard.com/resources/certificates/certificates.zip --directory-prefix=/usr/share/elasticsearch/config/
RUN unzip /usr/share/elasticsearch/config/certificates.zip -d /usr/share/elasticsearch/config
COPY config/sg_internal_users.yml plugins/search-guard-6/sgconfig
EXPOSE 9200 9300
