Budowanie obrazu
```
docker build -t jenkins:2.426.1-1 .
```
Uruchomienie Jenkins na docker
```
./prepare.sh
./run.sh
```
Generowanie klucza SSH dla agentów
```
ssh-keygen -f ./ssh
```
Dodanie prywatnego klucza w Credentials
```
http://localhost:8080/manage/credentials/store/system/domain
```
Podniesienie agenta na docker
```
docker run -d --name=agent-01 -p 10022:22 -e "JENKINS_AGENT_SSH_PUBKEY=ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCVBtregL5Ce4s0+bIrq5IACNYFMFbBkoFJuYd3THr3ELdcq+/PcvaJKD5wwJOwJkViTAQa7t205yE9GHa+mdxPYOKO4GI1sksf92kMCSqkeZrSleBKgKF686HkXnwEhawq3n2aC+CEwXbhorCMOizzgBIwNdCMFiE2qprE/hIJhkl/S5nuqEql5ULFrHRsmFvO1X5iMzz/iSPpTMWb9xMtgFNzQfyX51m4MoD+qnefxAKxtFj/sUCOslkWwll86n9GukzC0mbB5cSZnoPaz8tbk4nTcXPeCqSKdBAq3ULFaxoXG29I6a1G9wgJ7t+n/Q4thEjYO3CkwRDCGjVRJQE67TBt3yUdiyEbtFbvdj8B9EkVhVuwQm8xBfYOZBwMMpnUM9oCcQwa8yEWN1P1rBhUg/FAL37dvp2jtzBSyr1h9PAnHk9yOBoOUzpVJjM41Y7PdCTwa7rapjSNVJOXnZolg6b3JXMSxx4TSflZs53rxSvmPueOtXyAGZfCwwjPBas=" jenkins/ssh-agent:jdk17
```
Dodanie agenta w Jenkins (wymaga pluginu Docker)
```
http://localhost:8080/manage/cloud/
```
