# test-embedded-diagrams
Test of embedded mermaid diagrams

# Introduction

Following up the article [include-diagrams-markdown-files-mermaid](https://github.blog/2022-02-14-include-diagrams-markdown-files-mermaid/), this repo is just a test of embedded mermaid diagrams

## Terraform example

```mermaid
flowchart LR
    classDef red fill:#f96
    subgraph rg: aks
    aAks(aks)
    aIp(public ip)
    end
    dDns --> aIp
    subgraph ext_DNS
    dDns(dns)
    end
    aAks --> aks
    subgraph aks
        aIp --> sNg
        subgraph ns: nginx-ingress
        sNg(service) --> pNg(pod)
        end
        subgraph ns: workload
        iAc --> sAc(service):::red --> pAc(pod):::red
        pNg --> iAc(ingress):::red
        end
    end
    pAc --> mFire
    subgraph rg: db
        mServer(mariadb) --> mDb(database)
        mFire(firewall) --> mDb
    end
```
