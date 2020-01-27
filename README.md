# TP1-BORDAIS-HUGO

Après l'installation de la VM
=============================

J'ai installé nodejs, et nginx à l'aide des commandes suivantes :

``bash
sudo apt install nodejs
``

``bash
sudo apt install nginx
``

J'ai ensuite modifié mes ports, je suis allé dans "Settings>Network>Advanced>Port Forwarding". J'ai ajouté 3 ports comme ceci:

Http  | TCP | 127.0.0.1 | 8000 | 10.0.2.15 | 80
Https | TCP | 127.0.0.1 | 4443 | 10.0.2.15 | 443
Ssh   | TCP | 127.0.0.1 | 2222 | 10.0.2.15 | 2

Je travail actuellement en ssh à l'aide de la commande :

``bash
ssh hugo@127.0.0.1 -p 2222
``

Création d'un fichier index.html

```html
<!DOCTYPE html>
<​html​> <​body​>
B3 Devops - TP 1
</​body​> </​html​>
```

Création d'un fichier pour configurer le site :

```bash
server {

	listen 80;

	server_name monsite.com;
	root /var/www/monsite;
	index index.html;

}
```

Ensuite il faut penser à unlink le fichier "default" :

```bash
cd /etc/nginx/sites-enabled
unlink default
```

Enfin redémarrer : 
```bash
nginx -t
service nginx reload
```

Ensuite visualiser le resultat en allant sur un navigateur et rechercher :
127.0.0.1\8000
