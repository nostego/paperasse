                                                -*- outline -*-

Ce fichier est
https://svn.lrde.epita.fr/svn/lrde-publis/trunk/share/doc/update-lrde-bib.txt

Normalement, la gestion de ce répertoire se fait simplement en
utilisant make.  Les objectifs principaux de ce Makefile sont donnés
ci-dessous dans l'ordre dans lequel les tâches devraient être
accomplies.

* Sortir une copie fraîche de share
Si vous n'en avez pas encore une, faire

   svn co https://svn.lrde.epita.fr/svn/lrde-publis/trunk/share

sinon

   svn up

* Éditer bib/lrde.bib
** Conférences nationales
Mettre

  category = {national},

** Articles non publiés
Faire

  note = {Submitted} ou {Accepted}

Les articles rejetés ne doivent pas apparaître dans lrde.bib ni dans
le répertoire courant des publications du labo.  En revanche, un
espace existe si vous souhaitez entreposer des publications rejetées :
  /lrde/doc/lrde/papers/rejected/

** URL LRDE
Pensez à inclure l'URL au LRDE de cette façon :

  urllrde = {200102-Wscg},

si l'url est http://www.lrde.[...]/Publications/200102-Wscg

** Emacs est votre ami
Pensez à faire "sort" et "reformat".  Ou exécutez "make neat".

* make neat
Reformate, normalise et trie les entrées de lrde.bib (et csi.bib) à
l'aide de bin/bibneat.

* make view
Pour voir si tout se passe bien.  Votre papier est-il où il le faut
dans lrde.pdf ?

* make check
Pour s'assurer que ce que vous avez écrit marche bien, et que votre
papier est dispo en PDF.

* make diff
Pour voir les différences et permettre le point suivant.  Jeter un
coup d'oeil à lrde.tex.

* Éditer le ChangeLog (share/ChangeLog)
Pour détailler vos changements.

* make ci (ou checkin)
Pour enregistrer vos modifications, les propager dans /mnt/doc, et les
installer sur le site du LRDE.  Si ça se passe mal, faire "svn ci" à
cet endroit là à la main, puis make install.
