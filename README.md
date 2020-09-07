# MITM Postman

A tool that creates a Postman collection from App / Web API calls. Having [mitmproxy](https://mitmproxy.org/) installed is a prerequisite.

Filter by:

1. Host
2. Path

## Setup

Install mitm proxy

```sh
pip3 install mitmproxy
```

Clone mitm_postman

```sh
git clone git@github.com:raunakp/mitm_postman.git
```

```sh
cd mitm_postman
```

## Example

Run the command to start the proxy server and create the postman collection for the APIs calls from the client to a particular domain

```sh
mitmdump --set upstream_cert=false --set host_filter="datacenter.example.com" --set path_filter="/api/v1/people/" --set collection_name="people_apis" --ssl-insecure -p 9500 -q -s "lib/postman.py"
```

Configure the proxy settings on the client (port 9500)