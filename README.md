# CKAD_Game_of_Pods
Kubernetes exercises from Kodekloud's Game of Pods course for local use.
Some exercises are still being tweaked for use via Minikube; as things stand:
- Drupal_Bravo - Running but need to sort connection between db and drupal
- GOP_Fileserver_Pento - Runs in Kubernetes but issues with accessing service
- Redis_Cluster - Works 100%, just make sure to either:
    1) Use kubectl get pods -l app=redis-cluster -o jsonpath='{range.items[*]}{.status.podIP}:6379 '
    2) use above and reference appropriately with command: kubectl exec -it redis-cluster-0 -- redis-cli --cluster create --cluster-replicas 1 $(kubectl get pods -l app=redis-cluster -o jsonpath='{range.items[*]}{.status.podIP}:6379 ')   
- Iron_Gallery - Code correct, testing needed
- Voting_App - Testing needed, code matches exercises