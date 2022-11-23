# Running the project

- docker build -t harlun:v0 .
- docker run --env-file .env harlun:v0 sh -c "python manage.py makemigrations && python manage.py migrate"
- or
- docker run -it --env-file .env harlun:v0 sh
    - python manage.py makemigrations && python manage.py migrate
- docker run --env-file .env -p 80:8000 harlun:v0




### Digital Ocean
[ ] Create Services: Kubernetes Cluster, Database Cluster (VPC), Spaces (CDN & CORS), Container, Domains
[ ] 

### Doctl commands
( https://github.com/digitalocean/doctl#examples )
( https://docs.digitalocean.com/reference/doctl/how-to/install/ )
- brew install doctl
- doctl init auth
- Create Token on DO
(Find in Cluster's actions button)
- doctl kubernetes cluster kubeconfig save <hash>
- doctl auth list
(Optional)
- doctl auth switch --context <NAME>
- doctl account get
- doctl kubernets cluster list
- doctl kubernetes cluster kubeconfig show <cluster-id|cluster-name>



### Kubernetes commands
- kubectl options
- kubectl api-resources
- kubectl config current-context
- kubectl config get-contexts
- kubectl get services
- kubectl get all
- kubectl get all --all-namespaces
- kubectl get nodes
- kubectl describe svc <servicename>
- kubectl get svc
- kubectl get svc --all-namespaces
- kubectl get nodes
- kubectl get pods --all-namespaces
- kubectl get pods -o wide
- kubectl delete pod <name>
- kubectl get pods -o wide
- kubectl desribe svc <service>
Ubuntu ping 1:04:00
Check terminal colors
- kubectl exec -it ubuntu -- bash
> ping hello
> curl http://hello:8080
- kubectl delete -f deployment-svc-clusterip.yaml


### NGINX & Cert Manager
( https://github.com/kubernetes/ingress-nginx/blob/main/docs/deploy/index.md#quick-start )
( https://github.com/kubernetes/ingress-nginx/blob/main/docs/deploy/index.md#digital-ocean )

- Use one click install them (from D.O kubernetes markeplace dashboard)

- kubectl get pods --all-namespaces -l app.kubernetes.io/name=ingress-nginx
- kubectl get svc -n ingress-nginx
- kubectl get pods -n cert-manager
-

### Helm
- helm ls -A

### Linux Commands for DevOps (https://medium.com/@halil_tek/the-most-important-linux-commands-that-nobody-teaches-you-1b6919860c8f)
# Utilities
rsync -vap --ignore-existing <source_file> <destination_file>
mkpasswd -l 8
screen # Start a screen session
screen -ls # List running services
screen -r # Attach to session
ldapsearch -x -W -D <username | less# Key Flags

# Monitoring
wall "Maintenance scheduled for 13:30"Broadcast message from Joel@localhost: Maintenance scheduled for 13:30
top
ncdu (Disk usage)
lsof (list opened files)

# Network
nc -vz <host> <port> # Checks the connection between two hosts on a given port
nc -l 8080 | nc <host> 80 # Creating a proxy server
netstat -a # List all network ports
netstat -tlpn # List all listening ports# Key Flags
-s = Show statistics, -v = verbrose, -r = show routing tables, -i display interface table, -g = show group memeberships
nslookup medium.com/tags/devops# Key Flags -port = Change port number for connection, -type = Change type of query. -domain = Sets search list to name
tcpdump
tcpdump -i <interface> <ipaddress or hostname> <port>
dig
whois <domain>

# Ad-hoc 
cat test.json
cat test.json | python -m json.tool
jq . file.json
apt-cache seach <keyword>
diff -u <(ls -l /directory/) <(ls -l /directory/) | colordiff # Example usage of comparing output of two ls commands
date -d 1656685875 Fri, 01 Jul 2022 14:31:15 +0000# Current time as UNIX timestamp
date "+%s"
git log # See how many commits you've made
git rebase -i HEAD~x # x = number of commits you've made# Make changes on the text editor, keeping the last commit as pick and changing the rest to sqash# Edit the commit messages as you'd like, preferbly removing ones from previous commits
git push --force-with-lease

# List systemd services
systemctl -l -t service | less


