# srs

![](http://ossrs.net/gif/v1/sls.gif?site=github.com&path=/tmpl/k8s/kubernetes/18523999949/srs)
[![](https://github.com/18523999949/srs/actions/workflows/kubernetes.yml/badge.svg)](https://github.com/18523999949/srs/actions/workflows/kubernetes.yml)

Template repository for deploying SRS to any K8s service by GitHub Actions.

## Usage

**Step 1:** Create K8s cluster, update the kubeconfig, check by `kubectl cluster-info`:

* [TKE(Tencent Kubernetes Engine)](https://console.cloud.tencent.com/tke2/cluster?rid=8), see [doc](https://cloud.tencent.com/document/product/457/54231).
* [ACK(Alibaba Cloud Container Service for Kubernetes)](https://cs.console.aliyun.com/), see [doc](https://help.aliyun.com/document_detail/95108.html).
* [EKS(Amazon Elastic Kubernetes Service)](https://console.aws.amazon.com/eks/home#/clusters), see [doc](https://docs.aws.amazon.com/eks/latest/userguide/create-cluster.html).
* [AKS(Azure Kubernetes Service)](https://portal.azure.com/#create/microsoft.aks), see [doc](https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough-portal).

**Step 2:** Click the <kbd>Use this template</kbd> to create your repository, then set the [secrets](https://github.com/18523999949/srs/settings/secrets/actions):

* `KUBECONFIG` is the config of K8s, for example, the content of `cat $HOME/.kube/config`.

**Step 3:** Run workflow from [Actions](https://github.com/18523999949/srs/actions/workflows/kubernetes.yml) to deploy to your K8s, for example, if your external IP is `139.186.120.60`:

* Website is http://139.186.120.60:8080
* Publish RTMP to rtmp://139.186.120.60/live/livestream
* Play RTMP from rtmp://139.186.120.60/live/livestream
* Play HTTP-FLV from [http://139.186.120.60:8080/live/livestream.flv](http://139.186.120.60:8080/players/srs_player.html?stream=livestream.flv&&autostart=true)
* Play HLS from [http://139.186.120.60:8080/live/livestream.m3u8](http://139.186.120.60:8080/players/srs_player.html?stream=livestream.m3u8&&autostart=true)

Try to motify the [srs.yaml](srs.yaml), then push to your repository, your K8s will be updated automatically.

