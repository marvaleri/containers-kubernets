# Como rodar? (Sistema Operacional Linux)
<br>
<p>Após clonar o repositório, inicie o minikube com o seguinte comando </p> 

~~~
minikube start
~~~
<br>
<p>Depois rode</p>

~~~
eval $(minikube docker-env)
~~~
<br>
<p>Então baixe as imagens do apache e nginx</p> 

~~~
docker build -t apache-custom:v2 -f ./servers/apache/arquivo-apache ./servers/apache
docker build -t nginx-custom:v2 -f ./servers/nginx/arquivo-nginx ./servers/nginx
~~~
<br>
<p>O próximo passo é criar os pods</p> 

~~~
kubectl apply -f ./apache.yaml
kubectl apply -f ./nginx.yaml
~~~
<br>
<p>E para visualizar os pods e os services criados utilize os comandos</p> 

~~~
kubectl get pods
kubectl get services
~~~
<br>
<p>Para visualizar cada service rodando no navegador use o comando</p> 

~~~
minikube service --all
~~~
<br>
<p>Por fim, pare o minikube</p>

~~~
minikube stop
~~~

