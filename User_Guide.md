README
======

DEVELOPPEMENT D'UN PIPELINE DE GENE SET ENRICHMENT ANALYSIS (GSEA)
==================================================================
	SOUS R, INTERFACE SHINY

PRESENTATION DE L'INTERFACE :
-----------------------------

Elle se décompose en 5 zones :
	- Chargement et affichage des données
	- Vulcano plot
	- GO enrichment
		* GO classification (+barplot)
		* Possibilité de choisir le niveau de GO et les ontologies
		* GO enrichment (+barplot et dotplot), avec choix du nombre de catégories à afficher
		* GO graphe
			. Il est possible que le Graphe ne s'affiche pas à cause d'un trop faible nombre de nodes.
	- KEGG enrichment
		* Affichage de l'enrichment
		* Zone de saisie de texte où entrer les IDs de pathway, qui renvoie à la représentation graphique
		du pathway dans une page web.
	- Protein domains
		* Test hypergéométrique
		* Possibilité d'ajouter des métadonnées
	
Des boutons start permettent de lancer les analyses.

PRECAUTIONS D'UTILISATION :
---------------------------

WARNING 1 : La version graturie de shiny ne permet pas de séparer les tâches. bien que tout soit séparé
en onglets, les calculs de chaque analyse ne se font pas en parallèle mais sont mis en file d'attente 
les uns après les autres.

WARNING 2 : L'appli est une bêta et ne fonctionne qu'avec un seul format de doonées, celui du fichier
"human_retine.txt" : format txt, mêmes noms de colonnes, mêmes types d'IDs, ...

WARNING 3 : La rapidité de l'appli dépend de la qualité de la connexion, notamment de l'accès aux bases 
de données. Il est arrivé que l'appli tourne "dans le vide" car elle n'arrivait pas à se connecter aux 
bases de données.

WARNING 4 : Il y a un fort risque de crash à cause de versions incompatibles entre packages. Par exemple,
nous avons dû abandonner l'utilisation de pathview après la mise à jour automatique d'un ou pusieurs de 
nos packages

SCRIPT "STANDALONE" :
---------------------

Ce script additionel constitue le pipeline non-interfacé sous Shiny. Il est beaucoup plus riche en 
commentaires et explications. Ce script est complet et entièrement fonctionnel; il a été finalisé avant de 
commencer l'interface shiny, et nous l'avons gardé, pour conserver une trace de l'avancée du travail.

* Edit du 29/05 : entièrement fonctionel sauf pour pathview, en raison de conflits de versions de packages.
La correction n'a été apportée qu'à l'application Shiny *

Obtention du jeu de données :
-----------------------------

	Sara R. Savage, Colin A. Bretz, and John S. Penn ; RNA-Seq Reveals a Role for NFAT-Signaling in Human 
	Retinal Microvascular Endothelial Cells Treated with TNFα ; PLoS One. 2015
	
	doi:  10.1371/journal.pone.0116941
	
	https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4305319/

***********************************************************************************************************
Kevin Durimel, Victor Mataigne - M2.1 BIM - Université de Rouen.
	Script standalone : Kevin Durimel
	Interfaçage shiny : Victor Mataigne.

