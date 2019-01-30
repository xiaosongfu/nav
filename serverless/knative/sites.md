https://github.com/knative



## CloudEvents
https://cloudevents.io/
https://github.com/cloudevents/spec


---

knative 是谷歌开源的 serverless 架构方案，旨在提供一套简单易用的 serverless 方案，把 serverless 标准化。目前参与的公司主要是 Google、Pivotal、IBM、Red Hat，2018年7月24日对外发布，当前还处于快速发展的阶段。

对于函数的运维，一般的 serverless 平台（包括 knative）都提供了 logging、metrics、tracing 三个方面的功能。默认情况下，knative 使用 EFK（Elasticsearch、Fluent、Kibana）来收集、查找和分析日志；使用 prometheus + grafana 来收集和索引、展示 metrics 数据；使用 jaeger 来进行调用关系的 tracing。

针对 serverless 衍生出来的运维工具和平台还不够多，如何调试线上问题还没有看到非常好的解决方案。