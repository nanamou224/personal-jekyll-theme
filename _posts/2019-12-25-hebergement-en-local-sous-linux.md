---
layout: post
section-type: post
title: Hébergement de pages en local sous linux
category: exploitation web
tags: [ 'reverse_shell', 'web', 'hacking', 'ctf' ]
---

---------------------------------------------
#### Mise en garde
Le but de cet article est de vous apprendre à héberger votre "shell code" en local pour pouvoir demander à une machine distante de se connecter à la vôtre et non pas vous apprendre à mettre en place "un serveur d'hébergement multiutilisateur sous Linux"! 

---------------------------------------------

#### Pré requis 
1-Avoir installer et configurer le serveur web Apache2 <br/>
2-Avoir installer et configurer l'interpreteur PHP <br/>
3-Avoir installer et configurer le seveur de base de données MySQL

---------------------------------------------

#### Méthode 1: Serveur Apache2
**Etape 1**: placer ses pages dans le répertoire: `/var/www/` <br/>
**Etape 2**: démarrer les services d'Apache2
  <pre><code data-trim class="yaml">
      #méthode 1
      sudo /etc/init.d/apache2 start 
  </code></pre> <br/>
   <pre><code data-trim class="yaml">
      #méthode 2
      sudo service apache2 start
  </code></pre> <br/>

**Etape 3**: naviguer vers l'adresse IP de sa machine linux `http://10.23.201.17:80`, par exemple.
  
---------------------------------------------

#### Méthode 2: Serveur python
**Etape 1**: se placer dans le répertoire où se trouve les pages à héberger 
<pre><code data-trim class="yaml">
    #exemple du repertoire par défaut de kali linux
    cd /usr/share/webshell/php
  </code></pre> <br/>
**Etape 2**: lancer la commande <br/>
<pre><code data-trim class="yaml"> 
    #se mettre à l'écoute sous le port 8080 
    sudo python -m SimpleHTTPServer 8080
  </code></pre> <br/>
**Etape 3**: naviguer vers l'adresse IP de sa machine linux `http://10.23.201.17:8080`, par exemple.
.