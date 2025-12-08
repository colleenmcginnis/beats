## 8.19.19-TEST-ONLY [beats-release-notes-8.19.19-TEST-ONLY]

_This release also includes: [Deprecations](/release-notes/deprecations.md#beats-8.19.19-TEST-ONLY-deprecations)._


### Features and enhancements [beats-8.19.19-TEST-ONLY-features-enhancements]


**All**

* Introduce cloud connectors flow.  

**Filebeat**

* Add support for direct HTTP request rate limit setting in CEL input.  
* Add AWS auth method for CEL and HTTP JSON inputs.  
* Add client address and name to submitted Redis slowlogs.  
* Log unpublished event count and exit publish loop on input context cancellation.  
* Upgrade CEL mito library to v1.24.0.  
* Add file-based auth provider for CEL and HTTP JSON inputs.  [#47506](https://github.com/elastic/beats/issues/47506)

  The CEL and HTTP JSON inputs now support reading authentication tokens from
  files, enabling integration with various secret providers like Vault,
  Kubernetes secret projections, etc. Tokens are automatically refreshed based on
  a configurable interval without requiring restarts.
  

**Metricbeat**

* K8s_container_allocatable.  

  Updates kubernetes cpu and memory metrics to use allocatable values instead of capacity values.
* Add extra debug logging to simplify troubleshooting in prometheus module. [#47477](https://github.com/elastic/beats/pull/47477) [#15693](https://github.com/elastic/beats/issues/15693)

**Osquerybeat**

* Add browser_history table to Osquery extension for cross-platform browser history analysis.  
* Add amcache hive support for osquery extension in Windows.  
* Add status reporting for osquerybeat lifecycle and osqueryd management.  
* Add osqueryd process health monitoring with metrics exposed via beats monitoring endpoint.  
* Add record filtering/scoping support to the osquery extension.  
* Updates documentation for the amcache tables in the osquery extension.  
* Add marshalling support for embedded structs in the osquery extension.  
* Update column definition encoding to support embedded structs.  

**Packetbeat**

* Add status reporter interface to packetbeat.  

**Winlogbeat**

* Adds &#39;process.args_count&#39; to winlogbeat windows security ingest pipeline.  


### Fixes [beats-8.19.19-TEST-ONLY-fixes]


**All**

* Fixes zero time encoding for unix timestamps.  

**Filebeat**

* Prevent panic during startup if dissect processor has invalid field name in tokenizer.  

**Metricbeat**

* Improve defensive checks to prevent panics in meraki module.  

**Packetbeat**

* Rpc_fragment_sanitization. [#47803](https://github.com/elastic/beats/pull/47803) 
* Add check for incorrect length values in postgres datarow parser.  

