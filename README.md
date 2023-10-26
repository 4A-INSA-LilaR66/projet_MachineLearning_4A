# machine_learning_projet

### fichier R : 
02-10 : ACP + projection des individus (Léa)

02-20 : Julie
-Mise au propre des transformations + adaptation des codes
-Interprétations de l'ACP 
-Analyse Unidimensionnelle finie :)

Lila :
-Prevision par modèle gaussien, binomial 
-Regression LASSO 

-LDA episode 2 : julie (en cours) --------------------------------------

reste à vérifier avec la prof : (partie sur tune.knn)

-est ce que la cross validation par défaut de knn est bien le bootstrap sample ==> d'après Méli c'est de la cross validation 

-est ce que c'est bien le fait que l'échantillon bootstrap ne contienne que 63.2% des données et donc induisent un biais qui nous fait autant varier k ?

-comment trouver la vraie valeur optimale du nombre de voisin k ?? 

------------------------------------------------------------------

-SVM episode 4 : Lila (en cours)


### fichier Python : 
02-10 : modification des données après leur chargement (log, sqrt) (Julie)
Je suis en train de revoir les transformations possibles, j'en ai fait une liste que j'estime être la meilleure, vous pouvez regarder dans le fichier test_modif_donnees, j'attends votre avis (et celui de la prof de ML) pour changer :)
Je trouve ça bien mieux perso (Léa) :)

02-12 : exploration multidimensionelle (Julie)

02-13 : je me suis arretée avant le clustering (car il marche pas) je continuerai demain les explications je pense mais je te l'ai mis au cas où tu le veuilles avant :) (Léa)

02-13 : fin jusqu'au clustering

02-20 fichier Léa sur Ozone avec commentaires Méli. J'ai un soucis pour la courbe avec les IC et les lambda_min/1se car la règle de méli ne semble pas fonctionner (et celle de la doc sur la fonction associée non plus, à voir à un moment. fin de modif. Question : dans le tp vendredi on a été mocage et O3 pour faire des régressions logistiques. Maintenant, que utilisons nous ? (j'ai testé avec rain et tpmod et ça donne pas grand chose (du r^2 négatif)... Avez vous des idées ?

03-05 : Julie j'ai essayé de réarranger le code sur lasso et la regression logistique mais il y a qq endroits où j'ai toujours des résultats bizarres. 

- SVM : Eva
- Boosting, arbre, RF et réseaux de neurones en cours Léa 

07052022 Mise à jour du fichier, mise au propre des tests et tests MONTE CARLO, normalement tout compile, reste à le vérifier sur un autre ordi, à faire la partie données manquantes si besoin et ce sera fini ! Relecture avec Lila du latex la seconde semaine de vacances + tableau récapitulatif :))) 
-------------------------------------------
proposition blabla pour le rapport sur la svm (suite aux consignes et conseils de Méli)

\textbf{Méthode SVM (Support vector machine)}

1) pour la classification binaire (Y a pour modalité 1 et -1)

\begin{itemize}
\item Objectif d'utilisation de la méthode : 
Séparer les données par un hyperplan en maximisant la marge et utiliser la règle de classification suivante : 

$$\ f_{\alpha^\ast,b^\ast}(x)=sign(\sum_{x_i \ vecteurs \ support} y_i \alpha_i^\ast \langle x_i,x\rangle+b^\ast)$$

avec $\alpha_i \forall i$ et b trouvés en résolvant le problème d'optimisation suivant : 

argmin$(\frac{1}{2} \|w\|+C\sum \xi_i)$ avec $\forall i, y_i\langle w,x_i\rangle+b \geq 1- \xi_i et \xi_i \geq 0$

\item Hypothèses supposées :

Les données sont linéairement séparables, mais on autorise certaines mis classifications (slack variables). 

\item Variables à paramétrer :  

-le cost \textbf{C} (détermine le nombre de $\xi_i >$ 0, soit le nombre de support vectors. Plus il est grand, plus les marges sont petites et plus le risque d'overfitting augmente)\\

-d'autres paramètres propres aux noyaux utilisés 

$\rightarrow \gamma$ (‘rbf’, ‘poly’ ou ‘sigmoid’), pris par défaut à $\frac{1}{taille données}$

$\rightarrow$ coef0 (‘poly’ ou ‘sigmoid’), pris par défaut 1

$\rightarrow$ degree ('poly') correspond au degré du polynôme du noyau polynomial. 

Ces variables sont optimisées par cross validation pour choisir les valeurs des différents paramètres dans une grille de valeurs. 

\end{itemize}

$\rightarrow$ on a utilisé cette méthode pour pouvoir séparer nos données selon trois classes (low\_rain, high\_rain, no\_rain) et pour cela on a utilisé la méthode SVM one to all qui repose sur le même principe que présenté précédemment mais où il y a un système de votes pour attribuer la classe majoritaire à chaque point. 
2) pour la régression

\begin{itemize}
\item Objectif d'utilisation de la méthode : 
Séparer les données par un hyperplan en maximisant la marge et utiliser la règle de classification suivante : 

$$\ f_{\alpha^\ast,b^\ast}(x)=sign(\sum_{x_i \ vecteurs \ support} y_i \alpha_i^\ast \langle x_i,x\rangle+b^\ast$$

avec $\alpha_i \forall i$ et b trouvés en résolvant le problème d'optimisation suivant : 

argmin$(\frac{1}{2} \|w\|+C\sum \xi_i)$ avec $\forall i, y_i\langle w,x_i\rangle+b \geq 1- \xi_i \ et \ \xi_i \geq 0$

\item Hypothèses supposées :

Les données sont linéairement séparables, mais on autorise certaines mis classifications (slack variables). 

\item Variables à paramétrer :  

-le cost \textbf{C} (détermine le nombre de $\xi_i >$ 0, soit le nombre de support vectors. Plus il est grand, plus les marges sont petites et plus le risque d'overfitting augmente)\\

-epsilon $\epsilon$ : donne la taille de la marge

-d'autres paramètres propres aux noyaux utilisés 

$\rightarrow \gamma$ (‘rbf’, ‘poly’ ou ‘sigmoid’), pris par défaut à $\frac{1}{taille données}$

$\rightarrow$ coef0 (‘poly’ ou ‘sigmoid’) pris par défaut à 1

$\rightarrow$ degree ('poly') correspond au degré du polynôme du noyau polynomial. 

\item Méthode(s) pour tuner les variables : 

Par cross validation (pour évaluer l'erreur de généralisation) sur une grille de valeurs 




\end{itemize}

$\rightarrow$ on a utilisé cette méthode pour la régression de la variable qualitative rain

------------------------------------------------------------------
Lien vers le Overleaf : https://fr.overleaf.com/7594352394vdsgzctxqpgb
