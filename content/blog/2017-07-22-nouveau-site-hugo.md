---
title: Nouveau site !
author: Nicolas
date: 2017-07-22
draft: false
url: /2017/07/22/nouveau-site-hugo/
image: /images/2017/07/nouveau-site.png
video:
---


Et voila, bienvenue sur notre nouveau site ! Ça vous plaît ?

![Nouveau site](/images/2017/07/nouveau-site.png)

### Pourquoi changer ?

L'ancien blog sous Wordpress ne me convenait pas vraiment, je ne pouvais pas faire ce que je voulais, je n'avais pas envie de mettre les mains dans le code sur cette plateforme vieillissante... et notre abonnement se terminait ces jours-ci.

Il était temps pour moi de regarder ce qu'il se faisait de plus moderne, et de refaire un site que je pourrais personnaliser facilement.

Tout n'est pas encore fini mais le gros est là. Il manque les photos des anciens articles, de la mise en page de texte, de la correction de fautes, et pas mal de fonctionnalités, mais j'ai une plateforme qui pourra être facilement personnalisable.

Vous pouvez donc retrouver nos articles, les moyens de nous suivre, la carte pour voir notre position, et laisser des commentaires.

De mon côté, je dois encore remettre toutes les photos des anciens articles, les anciens commentaires qui sont sauvegardés mais qui ne s'affichent pas sur les articles, et améliorer l'existant.

Et je vais refaire également une carte plus jolie pour nous positionner. L'actuelle ne marche pas sur les tablettes et les smartphones...

### Sous le capot

Comme il y a pas mal de développeurs qui passent par ici, voici plus d'infos sur ce que j'ai fait ;)

Je voulais mettre en place un workflow plus moderne qu'avec wordpress. J'ai découvert l'univers des sites statiques, avec son hébergeur emblématique Netlify, Node.js et NMP, etc... Je savais que j'avais pris du retard sur ma veille ces dernières années, ça a été l'occasion de me rattraper !

Pour l'IDE, je suis passé **de PHPStrom à [Atom](https://atom.io/)**. J'avais envie de voir autre chose que du PHP, et d'avoir un environnement connecté à Github et tout ce qui va avec (Déploiement auto entre autre). Je ne l'ai pas encore bien exploré mais la prise en main est très facile.

Parmi les générateurs de sites, **[GatsbyJS](https://www.gatsbyjs.org/)** m'a séduit, Node.JS, React, GraphQL, et des perfs en front hallucinantes, il a tout pour plaire mais il est encore jeune et n'a pas de système de thème (ou j'ai pas compris comment ça marchait). L'effort de mise en place d'un premier site est donc assez considérable, surtout par rapport à la concurrence. C'est donc **[Hugo](https://gohugo.io/)** qui a gagné, la compilation est ultra-rapide (120ms pour 100 pages), et il est livré avec un serveur web en auto-refresh suffisamment verbeux pour le développement et le debug en local. La documentation est complète, et il est réellement possible de mettre en production un site simple en moins de 2h sans rien connaître. Bien sur, dès qu'on veut personnaliser un peu, il faut s'y mettre, mais rien de bien compliqué.

Pour le déploiement, c'est donc **[Github](https://github.com/) connecté à [Netlify](https://www.netlify.com/)**. Ca se connecte en quelques clics, et on déploie les modifs avec un simple git push. Netlify est vraiment bien fait et c'est un service à découvrir ! L'hébergement du site est gratuit, avec déploiement automatique, CDN, HTTPS, anti-DDOS, etc... C'est assez incroyable en fait...

Hugo est fourni avec [Disqus](https://disqus.com/) pour gérer les commentaires. Je vais l'utiliser pour le moment mais je pense rapidement migrer vers [StaticMan](https://staticman.net/). Le côté trop touffu et connecté de Disqus ne va pas convenir à notre audience familiale, et la logique de StaticMan est imparable pour aller avec Hugo.

Pour pouvoir gérer ceux qui veulent s'abonner par mail, j'utilise [MailChimp](https://mailchimp.com/). Je l'utilise pour le boulot, et même si je préfererais dans l'absolu gérer les listes moi-même en passant par [Sengrid](https://sendgrid.com/), faut avouer que l'installation est hyper simple. Faudra que je trouve un moyen de diffuser ensuite des campagnes automatiquement.

J'utilise également [IFTTT](https://ifttt.com/) pour automatiser la publication sur Twitter et Facebook, mais je ne suis pas sur du résultat pour le moment, je vais voir si on ne peut pas faire mieux !


Pour la migration de l'existant depuis Wordpress, j'ai utilisé le module de [SchumacherFM](https://github.com/SchumacherFM/wordpress-to-hugo-exporter). On retrouve les développeurs Magento de partout ^^ Enfin bref, son module exporte l'existant en markdown tout prêt pour Hugo. J'ai eu des gros soucis avec les images, mais c'est surtout lié aux différentes migration et changement de NDD que j'ai fait entre Worpress. Ca me semble le point le plus critique de la migration. A noter que le module est relativement simple et qu'il peut être intéressant de le patcher directement pour nettoyer les images à la volée.

Il me reste maintenant à développer une petite appli en JS pour me permettre de publier par mail. Je vais en avoir besoin pour donner des nouvelles avec ma connexion satellite quand je serais en pleine mer. Je vais utiliser l'API Gmail et git pour pouvoir générer et publier les nouveaux articles. A noter également que Netlify a une API que je pourrai utiliser.

Et voila, vous savez tout ! Le résultat est dispo sous Github => https://github.com/ntrossat/voguemerry, et vous pouvez même proposer les pull request pour les fautes d'orthographe ou autre ;)
