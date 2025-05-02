# Detalhamento dos logs do Kubernetes

No Kubernetes, os logs de solução de problemas são ouro.

Mas aqui está o problema. Nem todos os logs são iguais. Nem todas as localizações dos logs são óbvias.

Seja para depurar um pod com falha, um atraso no agendamento ou um problema repentino no cluster, você precisa saber exatamente onde procurar. Isso pode economizar horas e proteger sua produção.

A maioria dos engenheiros para nos logs do contêiner ou usa apenas logs do kubectl.

Engenheiros experientes vão mais a fundo. Eles verificam logs de nós, logs do Kubelet, logs do plano de controle, logs de tempo de execução de contêineres e logs de plug-ins CNI.

Para facilitar, dividi o registro do Kubernetes em duas visões práticas.

**Primeiro**, compartilho uma tabela que descreve os principais tipos de log do Kubernetes, seus caminhos de arquivo e o que cada um significa.

Use-o como uma referência rápida ao solucionar problemas.

![image](https://github.com/user-attachments/assets/489f70fe-41ed-413e-be60-904fe56b9d27)

**Em seguida**, incluo um layout visual de como esses logs são estruturados no diretório var log.

Isso ajuda você a acompanhar o problema do nível do contêiner até o plano de controle.

![image](https://github.com/user-attachments/assets/aa313351-2160-4dd7-8530-972d7b0537d9)

**A experiência diz que:**

> ➤ Sempre verifique os logs do contêiner e os logs do pod ao diagnosticar problemas do contêiner
> 
> ➤ Revise os arquivos de log de erros no servidor de API do kubelet e no planejador para descobrir problemas ocultos
> 
> ➤ Para pods presos no estado ContainerCreating, inspecione os logs CNI, como flannel log ou calico log
> 
> ➤ Use mensagens syslog dmesg log e auth log para examinar problemas de nível de nó ou de sistema
> 
> ➤ Para problemas de acesso e permissão, verifique os logs de auditoria do servidor API, especialmente com RBAC

**Quando você sabe onde estão os logs, você para de tentar adivinhar e começa a consertar.**

**Fonte:** techopsexamples.com
