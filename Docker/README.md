# Local testing

Build Docker image and tag:
```
docker build . -t huazhou/lange_symposium_workshop_2022
```

Push docker image tag to Docker Hub:
```
docker push huazhou/lange_symposium_workshop_2022:latest
```

Run a container on local machine:
```
docker-compose up
```
Make sure to modify the volume line in `docker-compose.yml` to the correct path to the local mimic data file folder. Point browser to the URL (with token) displayed on terminal, e.g., `http://127.0.0.1:8888/lab?token=1e2ac1bebc02b17b74833a36435499fc47a40c81c2d80548` for the JupyterLab interface. Open a terminal within JupyterLab and `git clone https://github.com/LangeSymposium/2022-July-Workshop.git`.

# Kubernetes on GCP

Tutorial on [Zero-to-JupyterHub](https://zero-to-jupyterhub.readthedocs.io/).

Install `kubectl`:
```
sudo apt-get install kubectl
```

Create a cluster:
```
gcloud container clusters create \
  --machine-type n2-standard-8 \
  --num-nodes 2 \
  --zone us-west2-a \
  --cluster-version latest \
  lange-symposium-workshop
```

Give your account permissions to perform all administrative actions needed.
```
kubectl create clusterrolebinding cluster-admin-binding \
  --clusterrole=cluster-admin \
  --user=huazhou@g.ucla.edu
```

Create a node pool for users (optional):
```
gcloud beta container node-pools create user-pool \
  --machine-type n1-standard-2 \
  --num-nodes 0 \
  --enable-autoscaling \
  --min-nodes 0 \
  --max-nodes 3 \
  --node-labels hub.jupyter.org/node-purpose=user \
  --node-taints hub.jupyter.org_dedicated=user:NoSchedule \
  --zone us-west2-a \
  --cluster lange-symposium-workshop
```

Install helm:
```
curl https://raw.githubusercontent.com/helm/helm/HEAD/scripts/get-helm-3 | bash
```

Install JupyterHub by helm:
```
helm repo add jupyterhub https://jupyterhub.github.io/helm-chart/
helm repo update
helm upgrade --cleanup-on-fail \
  --install jhub-1-5-0 jupyterhub/jupyterhub \
  --namespace jhub \
  --create-namespace \
  --version 1.2.0 \
  --values config.yaml
```
Note release name cannot be numeric like 20220622 (took me hours to figure out).

List container cluster:
```
gcloud container clusters list
```

List Kubernetes service:
```
kubectl get service --namespace jhub
```

List pods:
```
kubectl get pod --namespace jhub
```

If any changes to `config.yaml`, upgrade Kubernetes cluster by
```
helm upgrade --cleanup-on-fail \
  jhub-1-5-0 jupyterhub/jupyterhub \
  --namespace jhub \
  --version=1.2.0 \
  --values config.yaml
```

# On July 17th (day before workshop)

Freeze Docker image `huazhou/lange_symposium_workshop_2022` by a tag. Change the tag in `docker-compose.yml` and `config.yaml` from `latest` to the new tag.

Scale the cluster:
```
gcloud container clusters resize \
    <YOUR-CLUSTER-NAME> \
    --num-nodes <NEW-SIZE> \
    --zone us-west2-a
```

# MIMIC-IV data

Create a zonal-SSD `mimic-iv` for MIMIC IV v1.0 data.
```
gcloud compute disks create mimic-iv --size=10GB --type=pd-ssd --project=lange-symposium-workshop-2022 --zone=us-west2-a --source-snapshot=https://www.googleapis.com/compute/v1/projects/biostat-203b-2022winter/global/snapshots/mimic-iv
```

<https://cloud.google.com/kubernetes-engine/docs/how-to/persistent-volumes/preexisting-pd>
```

```
