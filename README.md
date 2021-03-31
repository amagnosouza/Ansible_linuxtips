# Projeto Ansible + AWS

Projeto de instalação de um cluster Kubernetes + AWS.

## Fases do projeto

```

 - Provisioning => Criar as instâncias/VMs para o cluster.
 - Install_k8s => Criação do cluster, etc.
 - Install helm => Prometheus e outros.
 

```

### Executando os playbooks

```

 0. O primeiro playbook é executado utilizando as credencias locais do usuário. (.aws/credentials)
 1. Executar primeiro o playbook provisioning para criar as maquinas e seus endereços
 2. Com os dados criados em hosts do playbook provisioning, adicionar os valores no arquivo hosts do playbook install_k8s
 3. A execução deve ser feita utilizando a chave staging pois todas as tasks rodarão com o user padrão (ubuntu)
 4. Para executar o playbook install_k8s é necessario instancias com no minimo 2-vcpu e 2Gb Ram. 


```

### Comandos kubernetes

```

 1. kubectl edit svc testando-prometheus-grafana - editar para NodePort
 2. kubectl get svc -> verifica os serviços que estão rodando
 3. kubectl scale deployments/... --replicas=x (x= numero de replicas)
 4. kubectl create deployment nginx --image=nginx
 5. kubectl exec --stdin --tty nome-pod -- /bin/bash



```

#### License

[MIT](https://choosealicense.com/licenses/mit/)
