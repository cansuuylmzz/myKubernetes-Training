##  minikube start

## kubectl get pods -A

1- namespace oluşturacağız. iki farklı yolu var. ya direk komutla yada yaml dosya ile oluşturulabilir. yaml dosyaasını yanda oluşturduk namespace.yml olarak. namespace dosyasını şimdi çalıştırmak uygulamak gerek. codes olan dizine geçip aşağıdaki komutu çalıştırmalıyız.
## kubectl apply -f namespace.yaml

sbm-training namespace içerisine nginx-pod ismiyle bir pod oluşturuldu. --image=nginx:latest  bu bir docker imajı nginx in en son versiyonlu imajını kullanarak bir pod oluşturduk.
## kubectl run nginx-pod --image=nginx:latest -n sbm-training



