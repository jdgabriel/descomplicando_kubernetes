# Descomplicando Kubernetes
## DIA - #1
### 1. Ferramentas
#### Docker
```bash
curl -fsSL https://get.docker.com | bash
```
#### kubectl

```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"

sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
#### Kind - Kubernetes in Docker
```bash
# For AMD64 / x86_64
[ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.22.0/kind-linux-amd64
# For ARM64
[ $(uname -m) = aarch64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.22.0/kind-linux-arm64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind
```
### 2. Primeiros passos
Criando seu primeiro cluster com Kind. Necessário ter o Docker rodando.
```bash
kind create --name kind-cluster --config=meu-primeiro-cluster.yaml
```
Criando seu primeiro Pod Kubernetes - Nginx
```bash
kubectl apply -f meu-primeiro-pod.yaml
```