# 🚀 TP : Diagnostic de Performance & SRE

Bienvenue dans ce lab pratique. Vous allez apprendre à identifier des goulots d'étranglement (bottlenecks) sur un serveur Linux.

## 🛠️ Installation
1. Clonez le dépôt : `git clone https://github.com/votre-nom/SRE-Performance-Lab.git`
2. Lancez l'environnement : `docker compose up -d`
3. Connectez-vous : `docker exec -it sre-performance-lab bash`

## 🧪 Les Scénarios de Sabotage
Exécutez ces commandes une par une et remplissez votre rapport.

### Scénario 1 : La Crise du Disque
`stress-ng --hdd 1 --hdd-opts direct --timeout 300s &`
* **Objectif** : Comprendre le statut `D` dans htop et le `%iowait`.

### Scénario 2 : La Suffocation RAM
`stress-ng --vm 1 --vm-bytes 4.5G --timeout 300s &`
* **Objectif** : Observer l'activation du Swap et l'usage de `free -h`.

### Scénario 3 : Le Mur CPU
`stress-ng --cpu $(nproc) --timeout 300s &`
* **Objectif** : Comparer un Load Average saturé par le calcul vs par le disque.
