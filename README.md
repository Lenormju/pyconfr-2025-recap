# Mon récap de la PyCon France 2025

Sprints : 30-31 octobre

Talks : 01-02 novembre

## Acceuil

Défilé des sponsors, peu d'infos pratiques.

## Keynote - Être un.e allié.e du numérique pour toustes en environnement hostile

Morgane Rozenn Hauguel

J'en avais vu un autre prisme lors du MixIT 2024. Toujours intéressant. Malgré l'effort de présenter des solutions actionnables à la fin, je n'en retiens pas vraiment, dommage.

## Talk court - Tout ce dont votre package a besoin

Joseph Barbier

Malgré le rythme de parole effréné, le fond était intéressant sur les bonne spratiques à adopter pour partager un package Python publiquement. Mais j'ai noté beaucoup d'approximations ou de manquements selon moi.

Propose https://github.com/y-sunflower/python-packaging-essentials comme base, à contribuer.

## ⭐ Talk long - Est-on (juste) payé à écrire du code ?

Guillaume Ayoub

Masterclass, sur le fond et la forme. Est-ce qu'on serait payé.e.s pour jouer/comprendre/construire (pas que du code)/inventer ? Et profiter du chemin, en faisant des choix qui ont du sens.

## Talk court - Doc Busters

Sarah Haïm-Lubczanski, Pauline Rambaud

De bons conseils sur comment produire ou consommer de la doc, sans se comporter en "raton laveur sous amphétamine".

## Talk court - Accro au café ? Prenez des photos et suivez l'utilisation de la machine du bureau !

Rémi Cardona

Intéressante démarche (pour l'exercice) de comment 

## Talk long - The Elegant Dependency Injection Mechanism of FastAPI

Mohamed Rebai

Très théorique, mais complet et raisonablement clair.

## Talk long - How to solve a Python mystery

Aivars Kalvāns

Goldmine of sys tricks for debugging softwares non-intrusively.

https://www.brendangregg.com/linuxperf.html

`/proc` :
* `readlink /proc/123456/cwd`
* `cat /proc/123456/environ | tr '\0' '\n'`
* `ls /proc/123456/fd/*`
* `tail /proc/123456/fd/34`
* `cat /proc/123456/fd/34 > backup.txt`

`strace` :
* `LD_LIBRARY_PATH=`pwd` strace unwind`
* `strace -f -ttt -o output.txt -s 1234 -p $PID`
* `strace -f -ttt -o output.txt -s 1234 $cmd $args`
* epoll_wait, select, pselect, poll, ... : waiting on pultiple sockets
* write, sendto : writing data, no block/wait
* accept : maiting to connect
* connect : waiting to connect without timeout
* read, recvfrom : waiting for data without timeout
* wait4 : child process termination
* futex : lock
* https://filippo.io/linux-syscall-table/

throughput :
* IO per-second x IO size (+ parallelism)
* blocksize for FS versus DB
* `dd if=/dev/zero of=~blob bs=4k count=20480 oflag=direct`
* `nmon`
* `iostat -x`

network :
* ICMP and UDP blocked
* `tcptraceroute` to host:port
* `TCP_NODELAY` when ~25tps or ~40ms
* https://brooker.co.za/blog/2024/05/09/nagle.html
* https://lwn.net/Articles/502585/ TCP: Support configurable delayed-ack parameters
* `cat /prox/sys/net/ipv4/tcp_keepalive_*` (default is 2 hours !)
*  https://www.postgresql.org/docs/current/libpq-connect.html#LIBPQ-KEEPALIVES
*  `export LD_PRELOAD=/path/to/libkeepalive.so; export KEEPIDLE=60; export KEEPINTVL=60:`
  
## Talk court - Virtual Environments and Lockfiles—How Python Is Improving Reproducibility

Ivo Bellin Salarin

* replay EuroPython + article - why it took 4 years to get a lockfile spec
* pip-tools : compile, sync
* https://emily.space/posts/251023-uv uv is the best thing to happen to the Python ecosystem in a decade

## Keynote - Le rêve de tout enfant – devenir DBA ?

Karen Jex

TODO
