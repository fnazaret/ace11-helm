
# IBM APP CONNECT ENTERPRISE

![IIB Logo](https://ot4i.github.com/iib-helm/ibm-integration-bus-dev/IBM_Integration_Bus_Icon.svg)

IBM® App Connect Enterprise combines the existing industry-trusted IBM Integration Bus (IIB) technologies with IBM App Connect Professional and with new cloud native technologies, to deliver a platform that supports the full breadth of integration needs across a modern digital enterprise.

Using the App Connect Toolkit, you can develop integration solutions and deploy them to the dedicated runtime of IBM App Connect Enterprise and to App Connect on IBM Cloud. You can use an extensive range of administration and systems management options to manage your integration solutions. 

# Introduction

This chart deploys a single IBM App Connect Enterprise for Developers integration node into an IBM Cloud Private or other Kubernetes environment.

## Installing the Chart

To install the chart with the release name `rel1`:

```bash
helm install --name rel1 ace11-dev --set license=accept
```

This command accepts the [IBM App Connect Enterprise for Developers license](LICENSE) and deploys an App Connect Enterprise for Developers server on the IBM Cloud Private cluster. The [configuration](#configuration) section lists the parameters that can be configured during installation.

> **Tip**: See all the resources deployed by the chart using `kubectl get all -l release=rel1`

## Uninstalling the Chart

To uninstall/delete the `rel1` release:

```bash
helm delete rel1
```

The command removes all the Kubernetes components associated with the chart.

## Configuration
The following table lists the configurable parameters of the `ace11-dev` chart and their default values.

| Parameter                        | Description                                     | Default                                                    |
| -------------------------------- | ----------------------------------------------- | ---------------------------------------------------------- |
| `license`                        | Set this to accept the terms of the IBM license | `Not accepted`                                     |
| `image.repository`               | Image full name including repository            | `ibmcom/ace`                                                |
| `image.tag`                      | Image tag                                       | `11.0.0.0`                                                        |
| `image.pullPolicy`               | Image pull policy                               | `IfNotPresent`                                             |
| `image.pullSecret`               | Image pull secret, if you are using a private Docker registry | `nil`                                        |
| `service.type`                   | Kubernetes service type for exposing ports       | `NodePort`                                  |
| `resources.limits.cpu`          | Kubernetes CPU limit for the ACE container | `2`                                                   |
| `resources.limits.memory`       | Kubernetes memory limit for the ACE container | `2048Mi`                                              |
| `resources.requests.cpu`        | Kubernetes CPU request for the ACE container | `1`                                                 |
| `resources.requests.memory`     | Kubernetes memory request for the ACE container | `512Mi`                                            |
| `servername`              | IBM App Connect Enterprise integration server name                           | `ACE_SERVER`                                        |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart.

> **Tip**: You can use the default [values.yaml](values.yaml)

[View the IBM App Connect Enterprise Dockerfile repository on Github](https://github.com/ot4i/ace-docker/)

[View the Official IBM App Connect Enterprise for Developers Docker Image in Docker Hub](https://hub.docker.com/r/ibmcom/ace/)

[Learn more about IBM App Connect Enterprise](https://www.ibm.com/support/knowledgecenter/en/SSTTDS_11.0.0/com.ibm.ace.home.doc/help_home.htm)

[Learn more about IBM App Connect Enterprise and Docker](https://www.ibm.com/support/knowledgecenter/en/SSTTDS_11.0.0/com.ibm.etools.mft.doc/bz91300_.htm)

[Learn more about IBM App Connect Enterprise and Lightweight Integration](https://ibm.biz/LightweightIntegrationLinks)

_Copyright IBM Corporation 2018. All Rights Reserved._

_The IBM App Connect Enterprise logo is copyright IBM and is provided for use for the purposes of IBM Cloud Private. You will not use the IBM App Connect Enterprise logo in any way that would diminish the IBM or IBM App Connect Enterprise image. IBM reserves the right to end your privilege to use the logo at any time in the future at our sole discretion. Any use of the IBM App Connect Enterprise logo affirms that you agree to adhere to these conditions._
