#### Bastion Install ####

```
bash
curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash
sudo mv kustomize /usr/local/bin/
sudo dnf install docker -y
sudo dnf install java-11-openjdk-devel -y
sudo dnf install maven -y

JAVA_11=$(alternatives --display java | grep 'family java-11-openjdk' | cut -d' ' -f1)
sudo alternatives --set java $JAVA_11

#export JAVA_HOME=/usr/lib/jvm/java-11-openjdk

curl -LO https://github.com/tektoncd/cli/releases/download/v0.23.1/tkn_0.23.1_Linux_x86_64.tar.gz
sudo tar xvzf tkn_0.23.1_Linux_x86_64.tar.gz -C /usr/local/bin/ tkn
rm tkn_0.23.1_Linux_x86_64.tar.gz

sudo wget https://github.com/argoproj/argo-cd/releases/download/v2.3.3/argocd-linux-amd64
sudo mv argocd-linux-amd64 /usr/local/bin/argocd
sudo chmod a+x /usr/local/bin/argocd
```
