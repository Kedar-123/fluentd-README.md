# Fluentd package

Fluentd collects events from various data sources and writes them to files, RDBMS, NoSQL, IaaS, SaaS, Hadoop and so on.

## Configuration Reference

You can configure the following:

### Fluentd common paramerers 

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|image.pullPolicy|Fluentd image pull policy|String|IfNotPresent|
|image.registry|Fluentd forwarder image registry override|String|""|
|forwarder.image.repository|Fluentd forwarder image repository override|String|""|
|forwarder.image.tag|Fluentd forwarder image tag override (immutable tags are recommended)|String|""|
|forwarder.daemonUser|Forwarder daemon user and group (set to root by default because it reads from host paths)|String|root|
|forwarder.daemonGroup|Fluentd forwarder daemon system group	String|root|
|forwarder.podSecurityContext.runAsUser|User ID for forwarder's containers|integer|0|
|forwarder.podSecurityContext.runAsGroup|Group ID for forwarder's containers|integer|0|
|forwarder.podSecurityContext.fsGroup|Group ID for forwarder's containers filesystem|integer|0|
|forwarder.terminationGracePeriodSeconds|Duration in seconds the pod needs to terminate gracefully|integer|30|
|forwarder.service.type|Kubernetes service type (ClusterIP, NodePort, or LoadBalancer) for the forwarders|String|ClusterIP|
|forwarder.service.sessionAffinity|Session Affinity for Kubernetes service, can be "None" or "ClientIP"|String|None|
|forwarder.startupProbe.enabled|Enable startupProbe|String|false|
|forwarder.startupProbe.initialDelaySeconds|Initial delay seconds for startupProbe|integer|60|
|forwarder.startupProbe.periodSeconds|Period seconds for startupProbe|integer|10|
|forwarder.startupProbe.timeoutSeconds|Timeout seconds for startupProbe|integer|5|
|forwarder.startupProbe.failureThreshold|Failure threshold for startupProbe|integer|6|
|forwarder.startupProbe.successThreshold|Success threshold for startupProbe|integer|1|
|forwarder.livenessProbe.enabled|Enable livenessProbe|String|TRUE|
|forwarder.livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe	integer|60|
|forwarder.livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|10|
|forwarder.livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|5|
|forwarder.livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|6|
|forwarder.livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|
|forwarder.readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe|integer|5|
|forwarder.readinessProbe.periodSeconds|Period seconds for readinessProbe	integer|10|
|forwarder.readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|5|
|forwarder.readinessProbe.failureThreshold|Failure threshold for readinessProbe|integer|6|
|forwarder.readinessProbe.successThreshold|Success threshold for readinessProbe|integer|1|
|forwarder.updateStrategy.type|Set up update strategy|String|RollingUpdate|
|forwarder.resources.limits|The resources limits for the container|String|{}|
|forwarder.resources.requests|The requested resources for the container|String|{}|
|aggregator.enabled|Enable Fluentd aggregator statefulset	String|TRUE|
|aggregator.image.registry|Fluentd aggregator image registry override|String|""|
|aggregator.image.repository|Fluentd aggregator image repository override|String|""|
|aggregator.image.tag|Fluentd aggregator image tag override (immutable tags are recommended)|String|""|
|aggregator.replicaCount|Number of aggregator pods to deploy in the Stateful Set"|integer|1|
|aggregator.podSecurityContext.runAsUser|User ID for aggregator's containers|integer|1001|
aggregator.podSecurityContext.runAsGroup	Group ID for aggregator's containers	integer	1001
aggregator.podSecurityContext.fsGroup	Group ID for aggregator's containers filesystem	integer	1001
aggregator.terminationGracePeriodSeconds	"
Duration in seconds the pod needs to terminate gracefully"	integer	30
aggregator.port	Port the Aggregator container will listen for logs. Leave it blank to ignore.	integer	24224
aggregator.startupProbe.enabled	"
Enable startupProbe"	String	TRUE
aggregator.startupProbe.initialDelaySeconds	"
Initial delay seconds for startupProbe"	integer	60
aggregator.startupProbe.periodSeconds	"
Period seconds for startupProbe"	integer	10
aggregator.startupProbe.timeoutSeconds	"
Timeout seconds for startupProbe"	integer	5
aggregator.startupProbe.failureThreshold	Failure threshold for startupProbe	integer	6
aggregator.startupProbe.successThreshold	Success threshold for startupProbe	integer	1
aggregator.livenessProbe.enabled	"
Enable livenessProbe"	String	TRUE
aggregator.livenessProbe.initialDelaySeconds	"
Initial delay seconds for livenessProbe"	integer	60
aggregator.livenessProbe.periodSeconds	"
Period seconds for livenessProbe"	integer	10
aggregator.livenessProbe.timeoutSeconds	Timeout seconds for livenessProbe	integer	5
aggregator.livenessProbe.failureThreshold	Failure threshold for livenessProbe	integer	6
aggregator.livenessProbe.successThreshold	Success threshold for livenessProbe	integer	1
aggregator.readinessProbe.enabled	"
Enable readinessProbe"	String	TRUE
aggregator.readinessProbe.initialDelaySeconds	Initial delay seconds for readinessProbe	integer	5
aggregator.readinessProbe.periodSeconds	"
Period seconds for readinessProbe"	integer	10
aggregator.readinessProbe.timeoutSeconds	aggregator.readinessProbe.timeoutSeconds	integer	5
aggregator.readinessProbe.failureThreshold	Failure threshold for readinessProbe	integer	6
aggregator.readinessProbe.successThreshold	Success threshold for readinessProbe	integer	1
aggregator.resources.limits	The resources limits for the container	String	{}
aggregator.resources.requests	"
The requested resources for the container"	String	{}
aggregator.autoscaling.minReplicas	Minimum number of replicas for the HPA	integer	2
aggregator.autoscaling.maxReplicas	Maximum number of replicas for the HPA	integer	5
aggregator.persistence.size	"
Persistent Volume size"	integer	"
10Gi"
aggregator.updateStrategy.type	"
Set up update strategy."	String	RollingUpdate
metrics.service.type	"
Prometheus metrics service type"	String	ClusterIP
metrics.service.port	Prometheus metrics service port	integer	24231
metrics.service.sessionAffinity	"
Session Affinity for Kubernetes service, can be ""None"" or ""ClientIP"""	String	none
