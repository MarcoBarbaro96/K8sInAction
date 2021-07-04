[DockerFile]
La FROM definisce l'immagine che si utilizzerà. In ADD si aggiunge il file app.js nella root dell'immagine. 
Con ENTRYPOINT  si definiscono i comandi che si dovranno eseguire quando qualcuno caricherà l'immagine.
***
[Comandi Docker]

$docker build -t kubia 

$docker run --name kubia-container -p 8080:8080 -d kubia 
 
 questo comando serve per far partire un nuovo container chiamato kubia-container che sarà presa dall'immaigne di Kubia. Il flag -d significa che continuerà anche in background. La porta 8080 (local) sarà mappata sulla porta 8080 del container in modo tale da essere accessicibile in localhost:8080.


 $docker ps  serve per vedere la lista dei container.

 ----
 $kubectl get pods = Lista dei pods per avere più info si utilizza describe pod

 Ogni pod ha un suo indirizzo IP che è visibile solo all'interno del cluster, per accedere dall'esterno abbiamo bisogno di esporre il ReplicationController attraverso il loadbalancer: 
 
 -kubectl expose replicationcontroller kubia --type=LoadBalancer --name kubia-http