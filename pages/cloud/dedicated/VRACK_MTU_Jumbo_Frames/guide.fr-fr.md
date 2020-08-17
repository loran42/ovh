---
Titre : 'Jumbo Frames'
Slug : 'vrack'
Excerpt : 'Découvrez comment configurer les JUMBO frames'
section : 'Debutant'
---

**Derniére mise à jour le 17/08/2020


## Objectif

Configurer votre distribution Linux à utiliser les JUMBO FRAMES.

## Pré requis

La connectivité réseau et les droits root.

A savoir : la taille MTU doit être identique sur tous les hôtes d'un même sous-réseau. 

## En pratique

<b> Vérifier sa MTU : <br/></b> 
ip link show | grep mtu

<b> Définir une nouvelle taille et tester la commande :</b>  
ip link set nom de l’interface mtu 9000

<b> Pour rendre le changement permanent : </b><br/> 
Editez le fichier <u>/etc/network/interface</u> et ajoutez-y les lignes suivantes :

<p><b>#pour une interface gérée par DHCP</b><br/>
Auto <u>nom de l’interface</u><br/>
Iface <u>nom de l’interface</u> inet dhcp<br/>
Pre-up  /bin/ip  link set dev <u>nom de l’interface</u> up mtu 9000</p>


<b>Attention !</b> <br/>
Bien verifier le chemin du binaire <b>« ip »</b>. Dans certaines distribution il peut se trouver dans <u>/usr/bin/ip</u>.


## Aller plus loin
Échangez avec notre communauté d'utilisateurs sur <https://community.ovh.com/>.
