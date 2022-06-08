
## helm

### 3

#### pkg

~~~ sh
helm repo add -- openebs https://openebs.github.io/charts
helm repo add -- kubesphare-main https://charts.kubesphere.io/main
helm repo add -- jetstack https://charts.jetstack.io
helm repo add -- harbor https://helm.goharbor.io
helm repo add -- rancher-stable https://releases.rancher.com/server-charts/stable
~~~

~~~ sh
mkdir helm.repos ; cd helm.repos
~~~

~~~ sh
echo  openebs/openebs jetstack/cert-manager harbor/harbor rancher-stable/rancher |
  
  xargs -n1 |
  xargs -i -P0 -- helm pull --untar --untardir {}/.. -- {}

find -maxdepth 2 -mindepth 2
~~~

need `helm dependency build` :

~~~ sh
helm repo add -- ygqygq2 https://ygqygq2.github.io/charts
~~~

~~~ sh
helm pull --untardir ygqygq2 --untar -- ygqygq2/nacos
helm pull --untardir ygqygq2 --untar -- ygqygq2/mysql
~~~

~~~ sh
(cd ygqygq2/nacos && helm dependency build) &
(cd ygqygq2/mysql && helm dependency build) &
wait
~~~

#### ops

~~~ sh
helm install --namespace openebs --create-namespace -- openebs openebs/openebs ; kubectl patch storageclass -p '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"true"}}}' -- openebs-hostpath
while ! helm install --namespace cert-manager --create-namespace --set installCRDs=true -- cert-manager jetstack/cert-manager ; do helm uninstall cert-manager -n cert-manager ; done
helm install --namespace goharbor-hub --create-namespace -- hub harbor/harbor
~~~

~~~ sh
helm install --namespace cattle-system --create-namespace --set hostname=10.100.11.101.sslip.io --set replicas=n --set bootstrapPassword='321 !@# aA ~~' -- rancher rancher-stable/rancher
~~~

~~~ sh
helm install --namespace nacos --create-namespace -- mysql ygqygq2/nacos
helm install --namespace mysql --create-namespace --set root.password='123#@!AaA' -- mysql ygqygq2/mysql
~~~





