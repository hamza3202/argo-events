<p>

Packages:

</p>

<ul>

<li>

<a href="#argoproj.io%2fv1alpha1">argoproj.io/v1alpha1</a>

</li>

</ul>

<h2 id="argoproj.io/v1alpha1">

argoproj.io/v1alpha1

</h2>

<p>

<p>

Package v1alpha1 is the v1alpha1 version of the API.

</p>

</p>

Resource Types:

<ul>

</ul>

<h3 id="argoproj.io/v1alpha1.AWSLambdaTrigger">

AWSLambdaTrigger

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerTemplate">TriggerTemplate</a>)

</p>

<p>

<p>

AWSLambdaTrigger refers to specification of the trigger to invoke an AWS
Lambda function

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>functionName</code></br> <em> string </em>

</td>

<td>

<p>

FunctionName refers to the name of the function to invoke.

</p>

</td>

</tr>

<tr>

<td>

<code>accessKey</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#secretkeyselector-v1-core">
Kubernetes core/v1.SecretKeySelector </a> </em>

</td>

<td>

<p>

AccessKey refers K8 secret containing aws access key

</p>

</td>

</tr>

<tr>

<td>

<code>secretKey</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#secretkeyselector-v1-core">
Kubernetes core/v1.SecretKeySelector </a> </em>

</td>

<td>

<p>

SecretKey refers K8 secret containing aws secret key

</p>

</td>

</tr>

<tr>

<td>

<code>namespace</code></br> <em> string </em>

</td>

<td>

<em>(Optional)</em>

<p>

Namespace refers to Kubernetes namespace to read access related secret
from. Must be defined if either accesskey or secretkey secret selector
is specified.

</p>

</td>

</tr>

<tr>

<td>

<code>region</code></br> <em> string </em>

</td>

<td>

<p>

Region is AWS region

</p>

</td>

</tr>

<tr>

<td>

<code>payload</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<p>

Payload is the list of key-value extracted from an event payload to
construct the request payload.

</p>

</td>

</tr>

<tr>

<td>

<code>parameters</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

Parameters is the list of key-value extracted from event’s payload that
are applied to the trigger resource.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.ArgoWorkflowOperation">

ArgoWorkflowOperation (<code>string</code> alias)

</p>

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.ArgoWorkflowTrigger">ArgoWorkflowTrigger</a>)

</p>

<p>

<p>

ArgoWorkflowOperation refers to the type of the operation performed on
the Argo Workflow

</p>

</p>

<h3 id="argoproj.io/v1alpha1.ArgoWorkflowTrigger">

ArgoWorkflowTrigger

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerTemplate">TriggerTemplate</a>)

</p>

<p>

<p>

ArgoWorkflowTrigger is the trigger for the Argo Workflow

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>source</code></br> <em>
<a href="#argoproj.io/v1alpha1.ArtifactLocation"> ArtifactLocation </a>
</em>

</td>

<td>

<p>

Source of the K8 resource file(s)

</p>

</td>

</tr>

<tr>

<td>

<code>operation</code></br> <em>
<a href="#argoproj.io/v1alpha1.ArgoWorkflowOperation">
ArgoWorkflowOperation </a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

Operation refers to the type of operation performed on the argo workflow
resource. Default value is Submit.

</p>

</td>

</tr>

<tr>

<td>

<code>parameters</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<p>

Parameters is the list of parameters to pass to resolved Argo Workflow
object

</p>

</td>

</tr>

<tr>

<td>

<code>GroupVersionResource</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#groupversionresource-v1-meta">
Kubernetes meta/v1.GroupVersionResource </a> </em>

</td>

<td>

<p>

(Members of <code>GroupVersionResource</code> are embedded into this
type.)

</p>

<p>

The unambiguous kind of this object - used in order to retrieve the
appropriate kubernetes api client for this resource

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.ArtifactLocation">

ArtifactLocation

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.ArgoWorkflowTrigger">ArgoWorkflowTrigger</a>,
<a href="#argoproj.io/v1alpha1.StandardK8sTrigger">StandardK8sTrigger</a>)

</p>

<p>

<p>

ArtifactLocation describes the source location for an external minio

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>s3</code></br> <em> Argo Events common.S3Artifact </em>

</td>

<td>

<p>

S3 compliant minio

</p>

</td>

</tr>

<tr>

<td>

<code>inline</code></br> <em> string </em>

</td>

<td>

<p>

Inline minio is embedded in sensor spec as a string

</p>

</td>

</tr>

<tr>

<td>

<code>file</code></br> <em>
<a href="#argoproj.io/v1alpha1.FileArtifact"> FileArtifact </a> </em>

</td>

<td>

<p>

File minio is minio stored in a file

</p>

</td>

</tr>

<tr>

<td>

<code>url</code></br> <em> <a href="#argoproj.io/v1alpha1.URLArtifact">
URLArtifact </a> </em>

</td>

<td>

<p>

URL to fetch the minio from

</p>

</td>

</tr>

<tr>

<td>

<code>configmap</code></br> <em>
<a href="#argoproj.io/v1alpha1.ConfigmapArtifact"> ConfigmapArtifact
</a> </em>

</td>

<td>

<p>

Configmap that stores the minio

</p>

</td>

</tr>

<tr>

<td>

<code>git</code></br> <em> <a href="#argoproj.io/v1alpha1.GitArtifact">
GitArtifact </a> </em>

</td>

<td>

<p>

Git repository hosting the minio

</p>

</td>

</tr>

<tr>

<td>

<code>resource</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#unstructured-unstructured-v1">
Kubernetes meta/v1/unstructured.Unstructured </a> </em>

</td>

<td>

<p>

Resource is generic template for K8s resource

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.Backoff">

Backoff

</h3>

<p>

<p>

Backoff for an operation

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>duration</code></br> <em> time.Duration </em>

</td>

<td>

<p>

Duration is the duration in nanoseconds

</p>

</td>

</tr>

<tr>

<td>

<code>factor</code></br> <em> float64 </em>

</td>

<td>

<p>

Duration is multiplied by factor each iteration

</p>

</td>

</tr>

<tr>

<td>

<code>jitter</code></br> <em> float64 </em>

</td>

<td>

<p>

The amount of jitter applied each iteration

</p>

</td>

</tr>

<tr>

<td>

<code>steps</code></br> <em> int </em>

</td>

<td>

<p>

Exit with error after this many steps

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.ConfigmapArtifact">

ConfigmapArtifact

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.ArtifactLocation">ArtifactLocation</a>)

</p>

<p>

<p>

ConfigmapArtifact contains information about minio in k8 configmap

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>name</code></br> <em> string </em>

</td>

<td>

<p>

Name of the configmap

</p>

</td>

</tr>

<tr>

<td>

<code>namespace</code></br> <em> string </em>

</td>

<td>

<p>

Namespace where configmap is deployed

</p>

</td>

</tr>

<tr>

<td>

<code>key</code></br> <em> string </em>

</td>

<td>

<p>

Key within configmap data which contains trigger resource definition

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.CustomTrigger">

CustomTrigger

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerTemplate">TriggerTemplate</a>)

</p>

<p>

<p>

CustomTrigger refers to the specification of the custom trigger.

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>serverURL</code></br> <em> string </em>

</td>

<td>

<p>

ServerURL is the url of the gRPC server that executes custom trigger

</p>

</td>

</tr>

<tr>

<td>

<code>secure</code></br> <em> bool </em>

</td>

<td>

<p>

Secure refers to type of the connection between sensor to custom trigger
gRPC

</p>

</td>

</tr>

<tr>

<td>

<code>certFilePath</code></br> <em> string </em>

</td>

<td>

<p>

CertFilePath is path to the cert file within sensor for secure
connection between sensor and custom trigger gRPC server.

</p>

</td>

</tr>

<tr>

<td>

<code>serverNameOverride</code></br> <em> string </em>

</td>

<td>

<p>

ServerNameOverride for the secure connection between sensor and custom
trigger gRPC server.

</p>

</td>

</tr>

<tr>

<td>

<code>triggerBody</code></br> <em> string </em>

</td>

<td>

<p>

TriggerBody is the custom trigger resource specification that custom
trigger gRPC server knows how to interpret.

</p>

</td>

</tr>

<tr>

<td>

<code>parameters</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<p>

Parameters is the list of parameters that is applied to resolved custom
trigger trigger object.

</p>

</td>

</tr>

<tr>

<td>

<code>payload</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<p>

Payload is the list of key-value extracted from an event payload to
construct the request payload.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.DataFilter">

DataFilter

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.EventDependencyFilter">EventDependencyFilter</a>)

</p>

<p>

<p>

DataFilter describes constraints and filters for event data Regular
Expressions are purposefully not a feature as they are overkill for our
uses here See Rob Pike’s Post:
<a href="https://commandcenter.blogspot.com/2011/08/regular-expressions-in-lexing-and.html">https://commandcenter.blogspot.com/2011/08/regular-expressions-in-lexing-and.html</a>

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>path</code></br> <em> string </em>

</td>

<td>

<p>

Path is the JSONPath of the event’s (JSON decoded) data key Path is a
series of keys separated by a dot. A key may contain wildcard characters
‘\*’ and ‘?’. To access an array value use the index as the key. The dot
and wildcard characters can be escaped with ‘\&rsquo;. See
<a href="https://github.com/tidwall/gjson#path-syntax">https://github.com/tidwall/gjson\#path-syntax</a>
for more information on how to use this.

</p>

</td>

</tr>

<tr>

<td>

<code>type</code></br> <em> <a href="#argoproj.io/v1alpha1.JSONType">
JSONType </a> </em>

</td>

<td>

<p>

Type contains the JSON type of the data

</p>

</td>

</tr>

<tr>

<td>

<code>value</code></br> <em> \[\]string </em>

</td>

<td>

<p>

Value is the allowed string values for this key Booleans are passed
using strconv.ParseBool() Numbers are parsed using as float64 using
strconv.ParseFloat() Strings are taken as is Nils this value is ignored

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.DependencyGroup">

DependencyGroup

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.SensorSpec">SensorSpec</a>)

</p>

<p>

<p>

DependencyGroup is the group of dependencies

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>name</code></br> <em> string </em>

</td>

<td>

<p>

Name of the group

</p>

</td>

</tr>

<tr>

<td>

<code>dependencies</code></br> <em> \[\]string </em>

</td>

<td>

<p>

Dependencies of events

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.EventDependency">

EventDependency

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.SensorSpec">SensorSpec</a>)

</p>

<p>

<p>

EventDependency describes a dependency

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>name</code></br> <em> string </em>

</td>

<td>

<p>

Name is a unique name of this dependency

</p>

</td>

</tr>

<tr>

<td>

<code>gatewayName</code></br> <em> string </em>

</td>

<td>

<p>

GatewayName is the name of the gateway from whom the event is received

</p>

</td>

</tr>

<tr>

<td>

<code>eventName</code></br> <em> string </em>

</td>

<td>

<p>

EventName is the name of the event

</p>

</td>

</tr>

<tr>

<td>

<code>filters</code></br> <em>
<a href="#argoproj.io/v1alpha1.EventDependencyFilter">
EventDependencyFilter </a> </em>

</td>

<td>

<p>

Filters and rules governing toleration of success and constraints on the
context and data of an event

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.EventDependencyFilter">

EventDependencyFilter

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.EventDependency">EventDependency</a>)

</p>

<p>

<p>

EventDependencyFilter defines filters and constraints for a event.

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>name</code></br> <em> string </em>

</td>

<td>

<p>

Name is the name of event filter

</p>

</td>

</tr>

<tr>

<td>

<code>time</code></br> <em> <a href="#argoproj.io/v1alpha1.TimeFilter">
TimeFilter </a> </em>

</td>

<td>

<p>

Time filter on the event with escalation

</p>

</td>

</tr>

<tr>

<td>

<code>context</code></br> <em> Argo Events common.EventContext </em>

</td>

<td>

<p>

Context filter constraints

</p>

</td>

</tr>

<tr>

<td>

<code>data</code></br> <em> <a href="#argoproj.io/v1alpha1.DataFilter">
\[\]DataFilter </a> </em>

</td>

<td>

<p>

Data filter constraints with escalation

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.FileArtifact">

FileArtifact

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.ArtifactLocation">ArtifactLocation</a>)

</p>

<p>

<p>

FileArtifact contains information about an minio in a filesystem

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>path</code></br> <em> string </em>

</td>

<td>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.GitArtifact">

GitArtifact

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.ArtifactLocation">ArtifactLocation</a>)

</p>

<p>

<p>

GitArtifact contains information about an minio stored in git

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>url</code></br> <em> string </em>

</td>

<td>

<p>

Git URL

</p>

</td>

</tr>

<tr>

<td>

<code>cloneDirectory</code></br> <em> string </em>

</td>

<td>

<p>

Directory to clone the repository. We clone complete directory because
GitArtifact is not limited to any specific Git service providers. Hence
we don’t use any specific git provider client.

</p>

</td>

</tr>

<tr>

<td>

<code>creds</code></br> <em> <a href="#argoproj.io/v1alpha1.GitCreds">
GitCreds </a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

Creds contain reference to git username and password

</p>

</td>

</tr>

<tr>

<td>

<code>namespace</code></br> <em> string </em>

</td>

<td>

<em>(Optional)</em>

<p>

Namespace where creds are stored.

</p>

</td>

</tr>

<tr>

<td>

<code>sshKeyPath</code></br> <em> string </em>

</td>

<td>

<em>(Optional)</em>

<p>

SSHKeyPath is path to your ssh key path. Use this if you don’t want to
provide username and password. ssh key path must be mounted in sensor
pod.

</p>

</td>

</tr>

<tr>

<td>

<code>filePath</code></br> <em> string </em>

</td>

<td>

<p>

Path to file that contains trigger resource definition

</p>

</td>

</tr>

<tr>

<td>

<code>branch</code></br> <em> string </em>

</td>

<td>

<em>(Optional)</em>

<p>

Branch to use to pull trigger resource

</p>

</td>

</tr>

<tr>

<td>

<code>tag</code></br> <em> string </em>

</td>

<td>

<em>(Optional)</em>

<p>

Tag to use to pull trigger resource

</p>

</td>

</tr>

<tr>

<td>

<code>ref</code></br> <em> string </em>

</td>

<td>

<em>(Optional)</em>

<p>

Ref to use to pull trigger resource. Will result in a shallow clone and
fetch.

</p>

</td>

</tr>

<tr>

<td>

<code>remote</code></br> <em>
<a href="#argoproj.io/v1alpha1.GitRemoteConfig"> GitRemoteConfig </a>
</em>

</td>

<td>

<em>(Optional)</em>

<p>

Remote to manage set of tracked repositories. Defaults to “origin”.
Refer
<a href="https://git-scm.com/docs/git-remote">https://git-scm.com/docs/git-remote</a>

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.GitCreds">

GitCreds

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.GitArtifact">GitArtifact</a>)

</p>

<p>

<p>

GitCreds contain reference to git username and password

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>username</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#secretkeyselector-v1-core">
Kubernetes core/v1.SecretKeySelector </a> </em>

</td>

<td>

</td>

</tr>

<tr>

<td>

<code>password</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#secretkeyselector-v1-core">
Kubernetes core/v1.SecretKeySelector </a> </em>

</td>

<td>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.GitRemoteConfig">

GitRemoteConfig

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.GitArtifact">GitArtifact</a>)

</p>

<p>

<p>

GitRemoteConfig contains the configuration of a Git remote

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>name</code></br> <em> string </em>

</td>

<td>

<p>

Name of the remote to fetch from.

</p>

</td>

</tr>

<tr>

<td>

<code>urls</code></br> <em> \[\]string </em>

</td>

<td>

<p>

URLs the URLs of a remote repository. It must be non-empty. Fetch will
always use the first URL, while push will use all of them.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.HTTPSubscription">

HTTPSubscription

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.Subscription">Subscription</a>)

</p>

<p>

<p>

HTTPSubscription holds the context of the HTTP subscription of events
for the sensor.

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>port</code></br> <em> int </em>

</td>

<td>

<p>

Port on which sensor server should run.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.HTTPTrigger">

HTTPTrigger

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerTemplate">TriggerTemplate</a>)

</p>

<p>

<p>

HTTPTrigger is the trigger for the HTTP request

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>serverURL</code></br> <em> string </em>

</td>

<td>

<p>

ServerURL refers to the URL to send HTTP request to.

</p>

</td>

</tr>

<tr>

<td>

<code>payload</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<p>

Payload is the list of key-value extracted from an event payload to
construct the HTTP request payload.

</p>

</td>

</tr>

<tr>

<td>

<code>tls</code></br> <em> <a href="#argoproj.io/v1alpha1.TLSConfig">
TLSConfig </a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

TLS configuration for the HTTP client.

</p>

</td>

</tr>

<tr>

<td>

<code>method</code></br> <em> string </em>

</td>

<td>

<em>(Optional)</em>

<p>

Method refers to the type of the HTTP request. Refer
<a href="https://golang.org/src/net/http/method.go">https://golang.org/src/net/http/method.go</a>
for more info. Default value is POST.

</p>

</td>

</tr>

<tr>

<td>

<code>parameters</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<p>

Parameters is the list of key-value extracted from event’s payload that
are applied to the HTTP trigger resource.

</p>

</td>

</tr>

<tr>

<td>

<code>timeout</code></br> <em> int </em>

</td>

<td>

<em>(Optional)</em>

<p>

Timeout refers to the HTTP request timeout in seconds. Default value is
10 seconds

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.JSONType">

JSONType (<code>string</code> alias)

</p>

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.DataFilter">DataFilter</a>)

</p>

<p>

<p>

JSONType contains the supported JSON types for data filtering

</p>

</p>

<h3 id="argoproj.io/v1alpha1.K8sResourcePolicy">

K8sResourcePolicy

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerPolicy">TriggerPolicy</a>)

</p>

<p>

<p>

K8sResourcePolicy refers to the policy used to check the state of K8s
based triggers using using labels

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>labels</code></br> <em> map\[string\]string </em>

</td>

<td>

<p>

Labels required to identify whether a resource is in success state

</p>

</td>

</tr>

<tr>

<td>

<code>backoff</code></br> <em> k8s.io/apimachinery/pkg/util/wait.Backoff
</em>

</td>

<td>

<p>

Backoff before checking resource state

</p>

</td>

</tr>

<tr>

<td>

<code>errorOnBackoffTimeout</code></br> <em> bool </em>

</td>

<td>

<p>

ErrorOnBackoffTimeout determines whether sensor should transition to
error state if the trigger policy is unable to determine the state of
the resource

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.KafkaTrigger">

KafkaTrigger

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerTemplate">TriggerTemplate</a>)

</p>

<p>

<p>

KafkaTrigger refers to the specification of the Kafka trigger.

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>url</code></br> <em> string </em>

</td>

<td>

<p>

URL of the Kafka broker.

</p>

</td>

</tr>

<tr>

<td>

<code>topic</code></br> <em> string </em>

</td>

<td>

<p>

Name of the topic. More info at
<a href="https://kafka.apache.org/documentation/#intro_topics">https://kafka.apache.org/documentation/\#intro\_topics</a>

</p>

</td>

</tr>

<tr>

<td>

<code>partition</code></br> <em> int </em>

</td>

<td>

<p>

Partition to write data to.

</p>

</td>

</tr>

<tr>

<td>

<code>parameters</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<p>

Parameters is the list of parameters that is applied to resolved Kafka
trigger object.

</p>

</td>

</tr>

<tr>

<td>

<code>requiredAcks</code></br> <em> int </em>

</td>

<td>

<p>

RequiredAcks used in producer to tell the broker how many replica
acknowledgements Defaults to 1 (Only wait for the leader to ack).

</p>

</td>

</tr>

<tr>

<td>

<code>compress</code></br> <em> bool </em>

</td>

<td>

<em>(Optional)</em>

<p>

Compress determines whether to compress message or not. Defaults to
false. If set to true, compresses message using snappy compression.

</p>

</td>

</tr>

<tr>

<td>

<code>flushFrequency</code></br> <em> int </em>

</td>

<td>

<em>(Optional)</em>

<p>

FlushFrequency refers to the frequency in milliseconds to flush batches.
Defaults to 500 milliseconds.

</p>

</td>

</tr>

<tr>

<td>

<code>tls</code></br> <em> <a href="#argoproj.io/v1alpha1.TLSConfig">
TLSConfig </a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

TLS configuration for the Kafka producer.

</p>

</td>

</tr>

<tr>

<td>

<code>payload</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<p>

Payload is the list of key-value extracted from an event payload to
construct the request payload.

</p>

</td>

</tr>

<tr>

<td>

<code>partitioningKey</code></br> <em> string </em>

</td>

<td>

<p>

The partitioning key for the messages put on the Kafka topic. Defaults
to broker url.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.KubernetesResourceOperation">

KubernetesResourceOperation (<code>string</code> alias)

</p>

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.StandardK8sTrigger">StandardK8sTrigger</a>)

</p>

<p>

<p>

KubernetesResourceOperation refers to the type of operation performed on
the K8s resource

</p>

</p>

<h3 id="argoproj.io/v1alpha1.NATSSubscription">

NATSSubscription

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.Subscription">Subscription</a>)

</p>

<p>

<p>

NATSSubscription holds the context of the NATS subscription of events
for the sensor

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>serverURL</code></br> <em> string </em>

</td>

<td>

<p>

ServerURL refers to NATS server url.

</p>

</td>

</tr>

<tr>

<td>

<code>subject</code></br> <em> string </em>

</td>

<td>

<p>

Subject refers to NATS subject name.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.NodePhase">

NodePhase (<code>string</code> alias)

</p>

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.NodeStatus">NodeStatus</a>,
<a href="#argoproj.io/v1alpha1.SensorStatus">SensorStatus</a>)

</p>

<p>

<p>

NodePhase is the label for the condition of a node

</p>

</p>

<h3 id="argoproj.io/v1alpha1.NodeStatus">

NodeStatus

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.SensorStatus">SensorStatus</a>)

</p>

<p>

<p>

NodeStatus describes the status for an individual node in the sensor’s
FSM. A single node can represent the status for event or a trigger.

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>id</code></br> <em> string </em>

</td>

<td>

<p>

ID is a unique identifier of a node within a sensor It is a hash of the
node name

</p>

</td>

</tr>

<tr>

<td>

<code>name</code></br> <em> string </em>

</td>

<td>

<p>

Name is a unique name in the node tree used to generate the node ID

</p>

</td>

</tr>

<tr>

<td>

<code>displayName</code></br> <em> string </em>

</td>

<td>

<p>

DisplayName is the human readable representation of the node

</p>

</td>

</tr>

<tr>

<td>

<code>type</code></br> <em> <a href="#argoproj.io/v1alpha1.NodeType">
NodeType </a> </em>

</td>

<td>

<p>

Type is the type of the node

</p>

</td>

</tr>

<tr>

<td>

<code>phase</code></br> <em> <a href="#argoproj.io/v1alpha1.NodePhase">
NodePhase </a> </em>

</td>

<td>

<p>

Phase of the node

</p>

</td>

</tr>

<tr>

<td>

<code>startedAt</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#microtime-v1-meta">
Kubernetes meta/v1.MicroTime </a> </em>

</td>

<td>

<p>

StartedAt is the time at which this node started

</p>

</td>

</tr>

<tr>

<td>

<code>completedAt</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#microtime-v1-meta">
Kubernetes meta/v1.MicroTime </a> </em>

</td>

<td>

<p>

CompletedAt is the time at which this node completed

</p>

</td>

</tr>

<tr>

<td>

<code>message</code></br> <em> string </em>

</td>

<td>

<p>

store data or something to save for event notifications or trigger
events

</p>

</td>

</tr>

<tr>

<td>

<code>event</code></br> <em> Argo Events common.Event </em>

</td>

<td>

<p>

Event stores the last seen event for this node

</p>

</td>

</tr>

<tr>

<td>

<code>updatedAt</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#microtime-v1-meta">
Kubernetes meta/v1.MicroTime </a> </em>

</td>

<td>

<p>

UpdatedAt refers to the time at which the node was updated.

</p>

</td>

</tr>

<tr>

<td>

<code>resolvedAt</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#microtime-v1-meta">
Kubernetes meta/v1.MicroTime </a> </em>

</td>

<td>

<p>

ResolvedAt refers to the time at which the node was resolved.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.NodeType">

NodeType (<code>string</code> alias)

</p>

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.NodeStatus">NodeStatus</a>)

</p>

<p>

<p>

NodeType is the type of a node

</p>

</p>

<h3 id="argoproj.io/v1alpha1.NotificationType">

NotificationType (<code>string</code> alias)

</p>

</h3>

<p>

<p>

NotificationType represent a type of notifications that are handled by a
sensor

</p>

</p>

<h3 id="argoproj.io/v1alpha1.OpenFaasTrigger">

OpenFaasTrigger

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerTemplate">TriggerTemplate</a>)

</p>

<p>

<p>

OpenFaasTrigger refers to the trigger type of OpenFass

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>gatewayURL</code></br> <em> string </em>

</td>

<td>

<p>

GatewayURL refers to the OpenFaas Gateway URL.

</p>

</td>

</tr>

<tr>

<td>

<code>payload</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

Payload is the list of key-value extracted from an event payload to
construct the request payload.

</p>

</td>

</tr>

<tr>

<td>

<code>parameters</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

Parameters is the list of key-value extracted from event’s payload that
are applied to the HTTP trigger resource.

</p>

</td>

</tr>

<tr>

<td>

<code>username</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#secretkeyselector-v1-core">
Kubernetes core/v1.SecretKeySelector </a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

Username refers to the Kubernetes secret that holds the username
required to log into the gateway.

</p>

</td>

</tr>

<tr>

<td>

<code>password</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#secretkeyselector-v1-core">
Kubernetes core/v1.SecretKeySelector </a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

Password refers to the Kubernetes secret that holds the password
required to log into the gateway.

</p>

</td>

</tr>

<tr>

<td>

<code>namespace</code></br> <em> string </em>

</td>

<td>

<em>(Optional)</em>

<p>

Namespace to read the password secret from. This is required if the
password secret selector is specified.

</p>

</td>

</tr>

<tr>

<td>

<code>functionName</code></br> <em> string </em>

</td>

<td>

<p>

FunctionName refers to the name of OpenFaas function that will be
invoked once the trigger executes

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.Sensor">

Sensor

</h3>

<p>

<p>

Sensor is the definition of a sensor resource

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>metadata</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#objectmeta-v1-meta">
Kubernetes meta/v1.ObjectMeta </a> </em>

</td>

<td>

Refer to the Kubernetes API documentation for the fields of the
<code>metadata</code> field.

</td>

</tr>

<tr>

<td>

<code>spec</code></br> <em> <a href="#argoproj.io/v1alpha1.SensorSpec">
SensorSpec </a> </em>

</td>

<td>

<br/> <br/>

<table>

<tr>

<td>

<code>dependencies</code></br> <em>
<a href="#argoproj.io/v1alpha1.EventDependency"> \[\]EventDependency
</a> </em>

</td>

<td>

<p>

Dependencies is a list of the events that this sensor is dependent on.

</p>

</td>

</tr>

<tr>

<td>

<code>triggers</code></br> <em> <a href="#argoproj.io/v1alpha1.Trigger">
\[\]Trigger </a> </em>

</td>

<td>

<p>

Triggers is a list of the things that this sensor evokes. These are the
outputs from this sensor.

</p>

</td>

</tr>

<tr>

<td>

<code>template</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#podtemplatespec-v1-core">
Kubernetes core/v1.PodTemplateSpec </a> </em>

</td>

<td>

<p>

Template contains sensor pod specification. For more information, read
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.11/#pod-v1-core">https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.11/\#pod-v1-core</a>.

</p>

</td>

</tr>

<tr>

<td>

<code>subscription</code></br> <em>
<a href="#argoproj.io/v1alpha1.Subscription"> Subscription </a> </em>

</td>

<td>

<p>

Subscription refers to the modes of events subscriptions for the sensor.
At least one of the types of subscription must be defined in order for
sensor to be meaningful.

</p>

</td>

</tr>

<tr>

<td>

<code>circuit</code></br> <em> string </em>

</td>

<td>

<p>

Circuit is a boolean expression of dependency groups

</p>

</td>

</tr>

<tr>

<td>

<code>dependencyGroups</code></br> <em>
<a href="#argoproj.io/v1alpha1.DependencyGroup"> \[\]DependencyGroup
</a> </em>

</td>

<td>

<p>

DependencyGroups is a list of the groups of events.

</p>

</td>

</tr>

<tr>

<td>

<code>errorOnFailedRound</code></br> <em> bool </em>

</td>

<td>

<p>

ErrorOnFailedRound if set to true, marks sensor state as
<code>error</code> if the previous trigger round fails. Once sensor
state is set to <code>error</code>, no further triggers will be
processed.

</p>

</td>

</tr>

<tr>

<td>

<code>serviceLabels</code></br> <em> map\[string\]string </em>

</td>

<td>

<p>

ServiceLabels to be set for the service generated

</p>

</td>

</tr>

<tr>

<td>

<code>serviceAnnotations</code></br> <em> map\[string\]string </em>

</td>

<td>

<p>

ServiceAnnotations refers to annotations to be set for the service
generated

</p>

</td>

</tr>

</table>

</td>

</tr>

<tr>

<td>

<code>status</code></br> <em>
<a href="#argoproj.io/v1alpha1.SensorStatus"> SensorStatus </a> </em>

</td>

<td>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.SensorResources">

SensorResources

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.SensorStatus">SensorStatus</a>)

</p>

<p>

<p>

SensorResources holds the metadata of the resources created for the
sensor

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>deployment</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#objectmeta-v1-meta">
Kubernetes meta/v1.ObjectMeta </a> </em>

</td>

<td>

<p>

Deployment holds the metadata of the deployment for the sensor

</p>

</td>

</tr>

<tr>

<td>

<code>service</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#objectmeta-v1-meta">
Kubernetes meta/v1.ObjectMeta </a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

Service holds the metadata of the service for the sensor

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.SensorSpec">

SensorSpec

</h3>

<p>

(<em>Appears on:</em> <a href="#argoproj.io/v1alpha1.Sensor">Sensor</a>)

</p>

<p>

<p>

SensorSpec represents desired sensor state

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>dependencies</code></br> <em>
<a href="#argoproj.io/v1alpha1.EventDependency"> \[\]EventDependency
</a> </em>

</td>

<td>

<p>

Dependencies is a list of the events that this sensor is dependent on.

</p>

</td>

</tr>

<tr>

<td>

<code>triggers</code></br> <em> <a href="#argoproj.io/v1alpha1.Trigger">
\[\]Trigger </a> </em>

</td>

<td>

<p>

Triggers is a list of the things that this sensor evokes. These are the
outputs from this sensor.

</p>

</td>

</tr>

<tr>

<td>

<code>template</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#podtemplatespec-v1-core">
Kubernetes core/v1.PodTemplateSpec </a> </em>

</td>

<td>

<p>

Template contains sensor pod specification. For more information, read
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.11/#pod-v1-core">https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.11/\#pod-v1-core</a>.

</p>

</td>

</tr>

<tr>

<td>

<code>subscription</code></br> <em>
<a href="#argoproj.io/v1alpha1.Subscription"> Subscription </a> </em>

</td>

<td>

<p>

Subscription refers to the modes of events subscriptions for the sensor.
At least one of the types of subscription must be defined in order for
sensor to be meaningful.

</p>

</td>

</tr>

<tr>

<td>

<code>circuit</code></br> <em> string </em>

</td>

<td>

<p>

Circuit is a boolean expression of dependency groups

</p>

</td>

</tr>

<tr>

<td>

<code>dependencyGroups</code></br> <em>
<a href="#argoproj.io/v1alpha1.DependencyGroup"> \[\]DependencyGroup
</a> </em>

</td>

<td>

<p>

DependencyGroups is a list of the groups of events.

</p>

</td>

</tr>

<tr>

<td>

<code>errorOnFailedRound</code></br> <em> bool </em>

</td>

<td>

<p>

ErrorOnFailedRound if set to true, marks sensor state as
<code>error</code> if the previous trigger round fails. Once sensor
state is set to <code>error</code>, no further triggers will be
processed.

</p>

</td>

</tr>

<tr>

<td>

<code>serviceLabels</code></br> <em> map\[string\]string </em>

</td>

<td>

<p>

ServiceLabels to be set for the service generated

</p>

</td>

</tr>

<tr>

<td>

<code>serviceAnnotations</code></br> <em> map\[string\]string </em>

</td>

<td>

<p>

ServiceAnnotations refers to annotations to be set for the service
generated

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.SensorStatus">

SensorStatus

</h3>

<p>

(<em>Appears on:</em> <a href="#argoproj.io/v1alpha1.Sensor">Sensor</a>)

</p>

<p>

<p>

SensorStatus contains information about the status of a sensor.

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>phase</code></br> <em> <a href="#argoproj.io/v1alpha1.NodePhase">
NodePhase </a> </em>

</td>

<td>

<p>

Phase is the high-level summary of the sensor.

</p>

</td>

</tr>

<tr>

<td>

<code>startedAt</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#time-v1-meta">
Kubernetes meta/v1.Time </a> </em>

</td>

<td>

<p>

StartedAt is the time at which this sensor was initiated

</p>

</td>

</tr>

<tr>

<td>

<code>completedAt</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#time-v1-meta">
Kubernetes meta/v1.Time </a> </em>

</td>

<td>

<p>

CompletedAt is the time at which this sensor was completed

</p>

</td>

</tr>

<tr>

<td>

<code>message</code></br> <em> string </em>

</td>

<td>

<p>

Message is a human readable string indicating details about a sensor in
its phase

</p>

</td>

</tr>

<tr>

<td>

<code>nodes</code></br> <em> <a href="#argoproj.io/v1alpha1.NodeStatus">
map\[string\]github.com/argoproj/argo-events/pkg/apis/sensor/v1alpha1.NodeStatus
</a> </em>

</td>

<td>

<p>

Nodes is a mapping between a node ID and the node’s status it records
the states for the FSM of this sensor.

</p>

</td>

</tr>

<tr>

<td>

<code>triggerCycleCount</code></br> <em> int32 </em>

</td>

<td>

<p>

TriggerCycleCount is the count of sensor’s trigger cycle runs.

</p>

</td>

</tr>

<tr>

<td>

<code>triggerCycleStatus</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerCycleState"> TriggerCycleState
</a> </em>

</td>

<td>

<p>

TriggerCycleState is the status from last cycle of triggers execution.

</p>

</td>

</tr>

<tr>

<td>

<code>lastCycleTime</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#time-v1-meta">
Kubernetes meta/v1.Time </a> </em>

</td>

<td>

<p>

LastCycleTime is the time when last trigger cycle completed

</p>

</td>

</tr>

<tr>

<td>

<code>resources</code></br> <em>
<a href="#argoproj.io/v1alpha1.SensorResources"> SensorResources </a>
</em>

</td>

<td>

<p>

Resources refers to metadata of the resources created for the sensor

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.StandardK8sTrigger">

StandardK8sTrigger

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerTemplate">TriggerTemplate</a>)

</p>

<p>

<p>

StandardK8sTrigger is the standard Kubernetes resource trigger

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>GroupVersionResource</code></br> <em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#groupversionresource-v1-meta">
Kubernetes meta/v1.GroupVersionResource </a> </em>

</td>

<td>

<p>

(Members of <code>GroupVersionResource</code> are embedded into this
type.)

</p>

<p>

The unambiguous kind of this object - used in order to retrieve the
appropriate kubernetes api client for this resource

</p>

</td>

</tr>

<tr>

<td>

<code>source</code></br> <em>
<a href="#argoproj.io/v1alpha1.ArtifactLocation"> ArtifactLocation </a>
</em>

</td>

<td>

<p>

Source of the K8 resource file(s)

</p>

</td>

</tr>

<tr>

<td>

<code>operation</code></br> <em>
<a href="#argoproj.io/v1alpha1.KubernetesResourceOperation">
KubernetesResourceOperation </a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

Operation refers to the type of operation performed on the k8s resource.
Default value is Create.

</p>

</td>

</tr>

<tr>

<td>

<code>parameters</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<p>

Parameters is the list of parameters that is applied to resolved K8s
trigger object.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.StatusPolicy">

StatusPolicy

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerPolicy">TriggerPolicy</a>)

</p>

<p>

<p>

StatusPolicy refers to the policy used to check the state of the trigger
using response status

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>allow</code></br> <em> \[\]int </em>

</td>

<td>

<p>

Allow refers to the list of allowed response statuses. If the response
status of the the trigger is within the list, the trigger will marked as
successful else it will result in trigger failure.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.Subscription">

Subscription

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.SensorSpec">SensorSpec</a>)

</p>

<p>

<p>

Subscription holds different modes of subscription available for sensor
to consume events.

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>http</code></br> <em>
<a href="#argoproj.io/v1alpha1.HTTPSubscription"> HTTPSubscription </a>
</em>

</td>

<td>

<em>(Optional)</em>

<p>

HTTP refers to the HTTP subscription of events for the sensor.

</p>

</td>

</tr>

<tr>

<td>

<code>nats</code></br> <em>
<a href="#argoproj.io/v1alpha1.NATSSubscription"> NATSSubscription </a>
</em>

</td>

<td>

<em>(Optional)</em>

<p>

NATS refers to the NATS subscription of events for the sensor

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.TLSConfig">

TLSConfig

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.HTTPTrigger">HTTPTrigger</a>,
<a href="#argoproj.io/v1alpha1.KafkaTrigger">KafkaTrigger</a>)

</p>

<p>

<p>

TLSConfig refers to TLS configuration for the HTTP client

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>caCertPath</code></br> <em> string </em>

</td>

<td>

<p>

CACertPath refers the file path that contains the CA cert.

</p>

</td>

</tr>

<tr>

<td>

<code>clientCertPath</code></br> <em> string </em>

</td>

<td>

<p>

ClientCertPath refers the file path that contains client cert.

</p>

</td>

</tr>

<tr>

<td>

<code>clientKeyPath</code></br> <em> string </em>

</td>

<td>

<p>

ClientKeyPath refers the file path that contains client key.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.TimeFilter">

TimeFilter

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.EventDependencyFilter">EventDependencyFilter</a>)

</p>

<p>

<p>

TimeFilter describes a window in time. DataFilters out event events that
occur outside the time limits. In other words, only events that occur
after Start and before Stop will pass this filter.

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>start</code></br> <em> string </em>

</td>

<td>

<p>

Start is the beginning of a time window. Before this time, events for
this event are ignored and format is hh:mm:ss

</p>

</td>

</tr>

<tr>

<td>

<code>stop</code></br> <em> string </em>

</td>

<td>

<p>

StopPattern is the end of a time window. After this time, events for
this event are ignored and format is hh:mm:ss

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.Trigger">

Trigger

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.SensorSpec">SensorSpec</a>)

</p>

<p>

<p>

Trigger is an action taken, output produced, an event created, a message
sent

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>template</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerTemplate"> TriggerTemplate </a>
</em>

</td>

<td>

<p>

Template describes the trigger specification.

</p>

</td>

</tr>

<tr>

<td>

<code>parameters</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameter"> \[\]TriggerParameter
</a> </em>

</td>

<td>

<p>

Parameters is the list of parameters applied to the trigger template
definition

</p>

</td>

</tr>

<tr>

<td>

<code>policy</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerPolicy"> TriggerPolicy </a> </em>

</td>

<td>

<p>

Policy to configure backoff and execution criteria for the trigger

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.TriggerCycleState">

TriggerCycleState (<code>string</code> alias)

</p>

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.SensorStatus">SensorStatus</a>)

</p>

<p>

<p>

TriggerCycleState is the label for the state of the trigger cycle

</p>

</p>

<h3 id="argoproj.io/v1alpha1.TriggerParameter">

TriggerParameter

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.AWSLambdaTrigger">AWSLambdaTrigger</a>,
<a href="#argoproj.io/v1alpha1.ArgoWorkflowTrigger">ArgoWorkflowTrigger</a>,
<a href="#argoproj.io/v1alpha1.CustomTrigger">CustomTrigger</a>,
<a href="#argoproj.io/v1alpha1.HTTPTrigger">HTTPTrigger</a>,
<a href="#argoproj.io/v1alpha1.KafkaTrigger">KafkaTrigger</a>,
<a href="#argoproj.io/v1alpha1.OpenFaasTrigger">OpenFaasTrigger</a>,
<a href="#argoproj.io/v1alpha1.StandardK8sTrigger">StandardK8sTrigger</a>,
<a href="#argoproj.io/v1alpha1.Trigger">Trigger</a>)

</p>

<p>

<p>

TriggerParameter indicates a passed parameter to a service template

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>src</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameterSource">
TriggerParameterSource </a> </em>

</td>

<td>

<p>

Src contains a source reference to the value of the parameter from a
event event

</p>

</td>

</tr>

<tr>

<td>

<code>dest</code></br> <em> string </em>

</td>

<td>

<p>

Dest is the JSONPath of a resource key. A path is a series of keys
separated by a dot. The colon character can be escaped with ‘.’ The -1
key can be used to append a value to an existing array. See
<a href="https://github.com/tidwall/sjson#path-syntax">https://github.com/tidwall/sjson\#path-syntax</a>
for more information about how this is used.

</p>

</td>

</tr>

<tr>

<td>

<code>operation</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerParameterOperation">
TriggerParameterOperation </a> </em>

</td>

<td>

<p>

Operation is what to do with the existing value at Dest, whether to
‘prepend’, ‘overwrite’, or ‘append’ it.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.TriggerParameterOperation">

TriggerParameterOperation (<code>string</code> alias)

</p>

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerParameter">TriggerParameter</a>)

</p>

<p>

<p>

TriggerParameterOperation represents how to set a trigger destination
resource key

</p>

</p>

<h3 id="argoproj.io/v1alpha1.TriggerParameterSource">

TriggerParameterSource

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerParameter">TriggerParameter</a>)

</p>

<p>

<p>

TriggerParameterSource defines the source for a parameter from a event
event

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>dependencyName</code></br> <em> string </em>

</td>

<td>

<p>

DependencyName refers to the name of the dependency. The event which is
stored for this dependency is used as payload for the parameterization.
Make sure to refer to one of the dependencies you have defined under
Dependencies list.

</p>

</td>

</tr>

<tr>

<td>

<code>contextKey</code></br> <em> string </em>

</td>

<td>

<p>

ContextKey is the JSONPath of the event’s (JSON decoded) context key
ContextKey is a series of keys separated by a dot. A key may contain
wildcard characters ‘\*’ and ‘?’. To access an array value use the index
as the key. The dot and wildcard characters can be escaped with
‘\&rsquo;. See
<a href="https://github.com/tidwall/gjson#path-syntax">https://github.com/tidwall/gjson\#path-syntax</a>
for more information on how to use this.

</p>

</td>

</tr>

<tr>

<td>

<code>dataKey</code></br> <em> string </em>

</td>

<td>

<p>

DataKey is the JSONPath of the event’s (JSON decoded) data key DataKey
is a series of keys separated by a dot. A key may contain wildcard
characters ‘\*’ and ‘?’. To access an array value use the index as the
key. The dot and wildcard characters can be escaped with ‘\&rsquo;. See
<a href="https://github.com/tidwall/gjson#path-syntax">https://github.com/tidwall/gjson\#path-syntax</a>
for more information on how to use this.

</p>

</td>

</tr>

<tr>

<td>

<code>value</code></br> <em> string </em>

</td>

<td>

<p>

Value is the default literal value to use for this parameter source This
is only used if the DataKey is invalid. If the DataKey is invalid and
this is not defined, this param source will produce an error.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.TriggerPolicy">

TriggerPolicy

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.Trigger">Trigger</a>)

</p>

<p>

<p>

TriggerPolicy dictates the policy for the trigger retries

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>k8s</code></br> <em>
<a href="#argoproj.io/v1alpha1.K8sResourcePolicy"> K8sResourcePolicy
</a> </em>

</td>

<td>

<p>

K8sResourcePolicy refers to the policy used to check the state of K8s
based triggers using using labels

</p>

</td>

</tr>

<tr>

<td>

<code>status</code></br> <em>
<a href="#argoproj.io/v1alpha1.StatusPolicy"> StatusPolicy </a> </em>

</td>

<td>

<p>

Status refers to the policy used to check the state of the trigger using
response status

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.TriggerSwitch">

TriggerSwitch

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.TriggerTemplate">TriggerTemplate</a>)

</p>

<p>

<p>

TriggerSwitch describes condition which must be satisfied in order to
execute a trigger. Depending upon condition type, status of dependency
groups is used to evaluate the result.

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>any</code></br> <em> \[\]string </em>

</td>

<td>

<p>

Any acts as a OR operator between dependencies

</p>

</td>

</tr>

<tr>

<td>

<code>all</code></br> <em> \[\]string </em>

</td>

<td>

<p>

All acts as a AND operator between dependencies

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.TriggerTemplate">

TriggerTemplate

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.Trigger">Trigger</a>)

</p>

<p>

<p>

TriggerTemplate is the template that describes trigger specification.

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>name</code></br> <em> string </em>

</td>

<td>

<p>

Name is a unique name of the action to take.

</p>

</td>

</tr>

<tr>

<td>

<code>switch</code></br> <em>
<a href="#argoproj.io/v1alpha1.TriggerSwitch"> TriggerSwitch </a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

Switch is the condition to execute the trigger.

</p>

</td>

</tr>

<tr>

<td>

<code>k8s</code></br> <em>
<a href="#argoproj.io/v1alpha1.StandardK8sTrigger"> StandardK8sTrigger
</a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

StandardK8sTrigger refers to the trigger designed to create or update a
generic Kubernetes resource.

</p>

</td>

</tr>

<tr>

<td>

<code>argoWorkflow</code></br> <em>
<a href="#argoproj.io/v1alpha1.ArgoWorkflowTrigger"> ArgoWorkflowTrigger
</a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

ArgoWorkflow refers to the trigger that can perform various operations
on an Argo workflow.

</p>

</td>

</tr>

<tr>

<td>

<code>http</code></br> <em> <a href="#argoproj.io/v1alpha1.HTTPTrigger">
HTTPTrigger </a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

HTTP refers to the trigger designed to dispatch a HTTP request with
on-the-fly constructable payload.

</p>

</td>

</tr>

<tr>

<td>

<code>openFaas</code></br> <em>
<a href="#argoproj.io/v1alpha1.OpenFaasTrigger"> OpenFaasTrigger </a>
</em>

</td>

<td>

<em>(Optional)</em>

<p>

OpenFaas refers to the trigger designed to invoke openfaas functions
with with on-the-fly constructable payload.

</p>

</td>

</tr>

<tr>

<td>

<code>awsLambda</code></br> <em>
<a href="#argoproj.io/v1alpha1.AWSLambdaTrigger"> AWSLambdaTrigger </a>
</em>

</td>

<td>

<em>(Optional)</em>

<p>

AWSLambda refers to the trigger designed to invoke AWS Lambda function
with with on-the-fly constructable payload.

</p>

</td>

</tr>

<tr>

<td>

<code>custom</code></br> <em>
<a href="#argoproj.io/v1alpha1.CustomTrigger"> CustomTrigger </a> </em>

</td>

<td>

<em>(Optional)</em>

<p>

CustomTrigger refers to the trigger designed to connect to a gRPC
trigger server and execute a custom trigger.

</p>

</td>

</tr>

<tr>

<td>

<code>kafka</code></br> <em>
<a href="#argoproj.io/v1alpha1.KafkaTrigger"> KafkaTrigger </a> </em>

</td>

<td>

<p>

Kafka refers to the trigger designed to place messages on Kafka topic.

</p>

</td>

</tr>

</tbody>

</table>

<h3 id="argoproj.io/v1alpha1.URLArtifact">

URLArtifact

</h3>

<p>

(<em>Appears on:</em>
<a href="#argoproj.io/v1alpha1.ArtifactLocation">ArtifactLocation</a>)

</p>

<p>

<p>

URLArtifact contains information about an minio at an http endpoint.

</p>

</p>

<table>

<thead>

<tr>

<th>

Field

</th>

<th>

Description

</th>

</tr>

</thead>

<tbody>

<tr>

<td>

<code>path</code></br> <em> string </em>

</td>

<td>

<p>

Path is the complete URL

</p>

</td>

</tr>

<tr>

<td>

<code>verifyCert</code></br> <em> bool </em>

</td>

<td>

<p>

VerifyCert decides whether the connection is secure or not

</p>

</td>

</tr>

</tbody>

</table>

<hr/>

<p>

<em> Generated with <code>gen-crd-api-reference-docs</code> on git
commit <code>d0d11e4</code>. </em>

</p>