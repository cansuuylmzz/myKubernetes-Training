# kubectl komut çalışmalarım

## minikube start

## minikube status

```
minikube
type: Control Plane
host: Stopped
kubelet: Stopped
apiserver: Stopped
kubeconfig: Stopped

```
## kubectl get pods -o wide -A

```
NAMESPACE     NAME                               READY   STATUS    RESTARTS        AGE   IP             NODE       NOMINATED NODE   READINESS GATES
kube-system   coredns-6f6b679f8f-zd4hm           1/1     Running   2 (6m34s ago)   18d   10.244.0.4     minikube   <none>           <none>
kube-system   etcd-minikube                      1/1     Running   2 (6m34s ago)   18d   192.168.49.2   minikube   <none>           <none>
kube-system   kube-apiserver-minikube            1/1     Running   2 (6m34s ago)   18d   192.168.49.2   minikube   <none>           <none>
kube-system   kube-controller-manager-minikube   1/1     Running   2 (6m34s ago)   18d   192.168.49.2   minikube   <none>           <none>
kube-system   kube-proxy-lrrd7                   1/1     Running   2 (6m34s ago)   18d   192.168.49.2   minikube   <none>           <none>
kube-system   kube-scheduler-minikube            1/1     Running   2 (6m34s ago)   18d   192.168.49.2   minikube   <none>           <none>
kube-system   storage-provisioner                1/1     Running   5 (4m49s ago)   18d   192.168.49.2   minikube   <none>           <none>

```
## kubectl get pods -n sbm-dev
 
```
sb-dev namespace içerisindeki podları listeler.
 
```
## kubectl get pods -n sbm-dev

```
sbm-dev namespace içerisinde hiç bir pod olmadığnı görüyoruz

```
## kubectl get nodes
Tüm nodların listesini döker

```
kubectl get nodes
NAME       STATUS   ROLES           AGE   VERSION
minikube   Ready    control-plane   34h   v1.31.0

```
 
Makineme sadece minikube kurduğum için gelen listede minikube adındaki node geliyor. Aslında şirketteki tüm nodeların isimleri gelecek.


Kubernetes'te pod'larla ilgili bilgi almak için kullanılan temel `kubectl get pods` komutlarının bir listesini tablo şeklinde aşağıda bulabilirsin. 

| Komut                                     | Açıklama                                                     |
|-------------------------------------------|--------------------------------------------------------------|
| `kubectl get pods`                        | Tüm namespace'teki pod'ları listeler (geçerli namespace).     |
| `kubectl get pods --all-namespaces`       | Tüm namespace'lerdeki pod'ları listeler.                     |
| `kubectl get pods -o wide`                | Pod'larla ilgili daha fazla bilgi (Node, IP vb.) verir.       |
| `kubectl get pods --namespace=<ns>`       | Belirtilen namespace'teki pod'ları listeler.                 |
| `kubectl get pods -o yaml`                | Pod'ları YAML formatında listeler.                           |
| `kubectl get pods -o json`                | Pod'ları JSON formatında listeler.                           |
| `kubectl get pods -l <label-key>=<value>` | Belirtilen label'a sahip pod'ları listeler.                  |
| `kubectl get pods -w`                     | Pod'ları izler (watch) ve canlı güncellemeleri gösterir.     |
| `kubectl get pods --field-selector`       | Belirtilen field'a sahip pod'ları listeler (örn: status).    |
| `kubectl get pods -o custom-columns=<key>`| Özel sütunlarla çıktıyı düzenler.                            |
| `kubectl get pods --sort-by=<field>`      | Belirtilen field'a göre sıralar.                             |

Bu komutlar, `kubectl get pods` komutunun çeşitli kullanımlarını gösterir. Bu seçeneklerle pod'larla ilgili geniş bir yelpazede bilgi alabilirsin.


## kubectl top pods -A

```
error: Metrics API not available
```

hata çözümü için aşağıdaki komutu çalıştırıyoruz.

## kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yamlserviceaccount/metrics-server created

## kubectl get pods -o yaml

Pod'ları YAML formatında listeler.
```

apiVersion: v1
items: []
kind: List
metadata:
  resourceVersion: ""

```

## kubectl get pods -o json

Pod'ları JSON formatında listeler.

```
{
    "apiVersion": "v1",
    "items": [],
    "kind": "List",
    "metadata": {
        "resourceVersion": ""
    }
}

```
## git pull && git add . && git commit -m "new commit" && git push

```

Bu komutlar ne yapar:

git pull: Uzak depodan en son değişiklikleri çeker.
git add .: Tüm dosya değişikliklerini sahneye ekler (staging area).
git commit -m "Your commit message": Değişiklikleri belirttiğin commit mesajı ile commit eder.
git push: Commit'leri uzak depoya gönderir.

```

##  kubectl get service -o wide

Tüm namespace'lerdeki pod'ları genişletilmiş bilgiyle (wide formatta) gösterir.


## kubectl get deployment -o yaml -n kube-system | less
komuttan q ile çıkıyoruz.
kube-system olarak yazan yer bizim namespace miz yani podumuz.


## kubectl describe pods storage-provisioner -n kube-system

## kubectl logs etcd-minikube -n kube-system
