# Detalhamento dos logs do Kubernetes

No Kubernetes, os _logs_ de solução de problemas são ouro.

Mas aqui está o problema: Nem todos os _logs_ são iguais. Nem todas as localizações dos logs são óbvias.

Seja para depurar um pod com falha, um atraso no agendamento ou um problema repentino no cluster, você precisa saber exatamente onde procurar. Isso pode economizar horas e proteger sua produção.

A maioria dos engenheiros pára nos _logs_ do container ou usa apenas logs do <u>kubectl</u>.

Engenheiros experientes vão mais a fundo. Eles verificam logs de nós, logs do <u>Kubelet</u>, _logs_ do control plane, _logs_ de container runtime e _logs_ de _plug-ins_ CNI.

Para facilitar, os _logs_ do Kubernetes é divido em duas visões práticas.

**Primeiro**, é apresentada abaixo uma tabela que descreve os principais tipos de _log_ do Kubernetes, seus caminhos de arquivo e o que cada um significa.

Use-a como uma referência rápida ao solucionar problemas.

![image](https://github.com/user-attachments/assets/489f70fe-41ed-413e-be60-904fe56b9d27)

**Em seguida**, é apresentado um layout visual de como esses _logs_ são estruturados no diretório var _log_.

Isso ajuda você a acompanhar o problema desde o nível do container até o _control plane_.

![image](https://github.com/user-attachments/assets/aa313351-2160-4dd7-8530-972d7b0537d9)

**A experiência diz que:**

> ➤ Sempre verifique os _logs_ do contêiner e os _logs_ do pod ao diagnosticar problemas do contêiner.
> 
> ➤ Revise os arquivos de _log_ de erros no servidor de API do kubelet e no planejador para descobrir problemas ocultos.
> 
> ➤ Para pods presos no estado ContainerCreating, inspecione os _logs_ CNI, como flannel _log_ ou calico _log_.
> 
> ➤ Use mensagens syslog dmesg _log_ e _auth log_ para examinar problemas de nível de nó ou de sistema
> 
> ➤ Para problemas de acesso e permissão, verifique os _logs_ de auditoria do servidor API, especialmente com RBAC

**Quando você sabe onde estão os logs, você para de tentar adivinhar e começa a consertar.**

**Fonte:** techopsexamples.com
