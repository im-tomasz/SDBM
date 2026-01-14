##### ***QUESTION 1***

##### ***Quels sont les tickets qui comportent l'article d'ID 500 ? Afficher le numéro de ticket***

##### ***uniquement***



SELECT  annee, numTicket

FROM t\_vente



WHERE id\_article=500;



##### ***QUESTION 2***

##### ***Quels sont les tickets du 15/01/2017 ? Afficher le numéro de ticket et la date.***



SELECT dateVente, numTicket 

FROM t\_ticket AS t

WHERE dateVente="2017-01-15";.



##### ***QUESTION 3***

##### ***Quels sont les tickets émis du 15/01/2017 au 17/01/2017 ? Afficher le numéro de ticket et la***

##### ***date.***



SELECT dateVente, numTicket

FROM t\_ticket AS t

WHERE dateVente BETWEEN "2017-01-15" AND "2017-01-17";





##### ***QUESTION 4***

##### ***Éditer la liste des articles (Code et nom uniquement) apparaissant sur un ticket à au moins***

##### ***95 exemplaires.***



SELECT nomArticle, a.id\_article, Qte

FROM t\_article AS a

JOIN t\_vente AS v

ON v.id\_article = a.id\_article

WHERE Qte>95;





##### ***QUESTION 5***

##### ***Quels sont les tickets émis au mois de mars 2017 ? Afficher le numéro de ticket et la date.***



SELECT numTicket, dateVente

FROM t\_ticket AS t

WHERE dateVente LIKE "2017-03%";





##### ***QUESTION 6***

##### ***Quels sont les tickets émis au deuxième trimestre 2017 ? Afficher le numéro de ticket et la***

##### ***date.***



SELECT numTicket, dateVente

FROM t\_ticket AS t

WHERE dateVente BETWEEN "2017-04-01" AND "2017-06-30";





##### ***QUESTION 7***

##### ***Quels sont les tickets émis au mois de mars et juillet 2017 ? Afficher le numéro de ticket et la***

##### ***date.***



SELECT numTicket, dateVente

FROM t\_ticket AS t

WHERE dateVente LIKE "2017-03%"

UNION

SELECT numTicket, dateVente

FROM t\_ticket AS t

WHERE dateVente LIKE "2017-07%";





##### ***QUESTION 8***

##### ***Afficher la liste de toutes les bières classées par couleur. (Afficher code et nom de bière,***

##### ***nom de la couleur)***



SELECT nomCouleur, nomArticle, id\_article

FROM t\_couleur AS c

JOIN t\_article AS a

ON c.id\_couleur = a.id\_couleur

ORDER BY nomCouleur;





##### ***QUESTION 9***

##### ***Afficher la liste des bières n'ayant pas de couleur. (Afficher le code et le nom)***



SELECT nomArticle, id\_article, id\_couleur

FROM t\_article AS a

WHERE id\_couleur IS NULL;





##### ***QUESTION 10***

##### ***Donnez la liste des bières de même couleur et de même type que la bière ayant le***

##### ***code 142.***

##### ***(affichez le code et le nom de la bière, le nom de la couleur et le nom du type)***



SELECT id\_article, nomArticle, nomCouleur, nomType 

FROM t\_article AS a



JOIN t\_couleur AS c

ON c.id\_couleur = a.id\_couleur

JOIN t\_typebiere AS t

ON t.id\_type = a.id\_type

WHERE a.id\_couleur IN 



(SELECT a.id\_couleur

FROM t\_article AS a

JOIN t\_couleur AS c

ON c.id\_couleur = a.id\_couleur

JOIN t\_typebiere AS t

ON t.id\_type = a.id\_type

WHERE a.id\_article = 142

)



AND a.id\_type IN 



(SELECT a.id\_type

FROM t\_article AS a

JOIN t\_couleur AS c

ON c.id\_couleur = a.id\_couleur

JOIN t\_typebiere AS t

ON t.id\_type = a.id\_type

WHERE a.id\_article = 142)



AND a.id\_article<>142



ORDER BY a.id\_article;





##### ***QUESTION 11***

##### ***Lister pour chaque ticket la quantité totale d'articles vendus.***

##### ***(Classer par quantité décroissante)***



SELECT t.annee, t.numTicket, SUM(Qte) AS QuantiteTotale

FROM t\_ticket AS t

JOIN t\_vente AS v

ON t.numTicket = v.numTicket

GROUP BY t.annee, t.numTicket

ORDER BY t.annee;





##### ***QUESTION 12***

##### ***Lister chaque ticket pour lequel la quantité totale d'articles vendus est inférieure à 50.***

##### ***(Classer par quantité croissante)***



.





##### ***QUESTION 13***

##### ***Lister chaque ticket pour lequel la quantité totale d'articles vendus est supérieure à 500.***

##### ***(Classer par quantité décroissante)***



.





##### ***QUESTION 14***

##### ***Lister chaque ticket pour lequel la quantité totale d'articles vendus est supérieure à 500. On***

##### ***exclura du total, les ventes de 50 articles et plus. (classer par quantité décroissante)***



.





##### ***QUESTION 15***

##### ***Lister les bières de type ‘Trappiste'. (id, nom de la bière, volume et titrage)***



.





##### ***QUESTION 16***

##### ***Lister les marques du continent ‘Afrique'. (id et nom de marque, nom du continent)***



.





##### ***QUESTION 17***

##### ***Lister les bières du continent ‘Afrique'. (ID, Nom et volume)***



.





##### ***QUESTION 18***

##### ***Lister les tickets (année, numéro de ticket, montant total à payer). En sachant que :***

##### ***• on applique un taux de TVA de 20% au montant total hors taxe de chaque***

##### ***ticket***

##### ***Classer par montant décroissant***



.





##### ***QUESTION 19***

##### ***Donner le C.A. par année. (Année et Total HT)***



.





##### ***QUESTION 20***

##### ***Lister les quantités vendues de chaque article pour l'année 2017. (Id et nom de l'article,***

##### ***quantité vendue)***



.





##### ***QUESTION 21***

##### ***Lister les quantités vendues de chaque article pour les années 2014,2015 ,2016,2017.***



.





##### ***QUESTION 22***

##### ***Lister les tickets sur lesquels apparaissent un des articles apparaissant aussi sur le ticket***

##### ***2017-5123. (Anne et Numéro de ticket)***



.





##### ***QUESTION 23***

##### ***Donner pour chaque Type de bière, la bière la plus vendue en 2017. (Classer par quantité***

##### ***décroissante)***



.





##### ***QUESTION 24***

##### ***Donner la liste des bières qui n'ont pas été vendues en 2014 ni en 2015. (Id, nom et volume)***



.





##### ***QUESTION 25***

##### ***Donner la liste des bières qui n'ont pas été vendues en 2014 mais ont été vendues en 2015.***

##### ***(Id, nom et volume)***



.



