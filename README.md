# Elasticsearch Test

This is a project for testing out Elasticsearch on a local machine.

## Installation

1. `cd ~ && git clone https://github.com/VBoB13/es_test.git`
2. Create your environment and install python packages with `python -m pip install -r requirements.txt`
3. Download Elasticsearch:

```
curl -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-8.4.2-darwin-x86_64.tar.gz
curl https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-8.4.2-darwin-x86_64.tar.gz.sha512 | shasum -a 512 -c -
tar -xzf elasticsearch-8.4.2-darwin-x86_64.tar.gz
cd elasticsearch-8.4.2/
```

4. `export ES_HOME=/path/to/your/elasticsearch-8.4.2`
5. Add `discovery.type: single-node` to the `$ES_HOME/config/elasticsearch.yml` file.
6. Then add `action.auto_create_index: .monitoring*,.watches,.triggered_watches,.watcher-history*,.ml*` to the same file.
7. Run your Elasticsearch with `$ES_HOME/bin/elasticsearch`
8. Test with `curl --cacert $ES_HOME/config/certs/http_ca.crt -u elastic http://localhost:9200`
9. Then either run the `es_test.py` file **OR** the Jupyter Notebook file (Elasticsearch.ipynb)
