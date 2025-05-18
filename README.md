# CKAD_Game_of_Pods

Kubernetes exercises from Kodekloud's Game of Pods course for local use, some edits have been made from the Kodekloud Solution [repo](https://github.com/kodekloudhub/game-of-pods) as there were some issues in practice.
As things stand:

## Drupal_Bravo

Works 100%, had to edit the Kodekloud MySql deployment for MYSQL_USER as "root" is created by default already.

## GOP_Fileserver_Pento

Works 100%, the Kodekloud version has incorrect selectors used in the service and pod.

## Redis_Cluster

Works 100%, just make sure to:

1. Use `kubectl get pods -l app=redis-cluster -o jsonpath='{range.items[*]}{.status.podIP}:{.spec.containers[*].ports[0].containerPort} '`
1. Use above and append the output to appropriately with command: `kubectl exec -it redis-cluster-0 -- redis-cli --cluster create --cluster-replicas 1 <STEP 1 OUTPUT>`

## Iron_Gallery

Works 100%, just ensure to have an Ingress Controller e.g. Nginx configured appropriately for the Cluster for internal testing, for external, just use <Node IP>:<NodePort> as per usual.

## Voting_App

Works 100% - No changes required.
