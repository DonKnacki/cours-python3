# 5. Collections

Dans les chapitres précédents, nous avons vu comment créer une variable c'est à dire définir une étiquette sur un objet.

Vous vous rendrez compte très rapidement qu'il est utile de pouvoir avoir plusieurs objets qui correspondent à une seule étiquette.  
C'est là qu'entre en scène les *collections*  

## Les listes
Durant votre parcours pour devenir magicien, vous serez sans doute amené à vous fournir en matériel 

 - une baguette magique 
 - de la bave de crapaud
 - un vieux grimoire
 - etc ...

Pour rien oublier, il vaut mieux tous noter sur une même liste ! 
En python, c'est la même chose : les listes sont très utiles pour avoir plusieurs informations au même endroit

###Création de listes
Voyons comment créer une liste
```python
>>> x = list()
>>> x
[]
```

*Mais pourquoi Python répond [ ] ?*  
Car il existe une seconde façon de créer une liste avec l'utilisation des crochets.  
La syntaxe est plus courte et en plus cela permet de créer une liste avec des valeurs en une seule ligne! 
```python
>>> x = ['baguette', 'bave', 'grimoire', 1, 0.5]
>>> x
['baguette', 'bave', 'grimoire', 1, 0.5]
```
###Jouons avec les listes
Bien entendu, les listes ne sont pas figées : on peut ajouter et supprimer des objets qui la compose.
```python
>>> x = ['baguette', 'bave', 'grimoire', 1, 0.5]
>>> x.append(-1) # ajoute un objet à la liste
>>> x
['baguette', 'bave', 'grimoire', 1, 0.5, -1]
>>> x.remove('bave') # supprime l'objet 'bave' de la liste 
>>> x
['baguette', 'grimoire', 1, 0.5, -1]
>>> y = ['a', 'b']
>>> x.extend(y) # ajoute tous les objets de la liste y dans la liste x
['baguette', 'grimoire', 1, 0.5, -1, 'a', 'b']
```
Contrairement au variable ordinaire, si on colle deux étiquettes sur la même liste, les changements sur une étiquette sont répercutées sur l'autre
```python
>>> x = ['baguette', 'bave', 'grimoire']
>>> y = x
>>> x
['baguette', 'bave', 'grimoire']
>>> y
['baguette', 'bave', 'grimoire']
>>> x.append(1)
>>> x
['baguette', 'bave', 'grimoire', 1]
>>> y
['baguette', 'bave', 'grimoire', 1]
```

####A vos ordres ! 
Vous l'aurez remarqués, les listes sont ordonnées : lorsqu'on ajoute un objet, celui-ci se retrouve en dernière place.  
Les objets ont donc une place précise dans la liste et on peut y accéder via son *indice*  
Attention néanmoins, **le premier objet se trouve à l'indice 0**
```python
>>> x = ['baguette', 'bave', 'grimoire', 1, 0.5]
>>> x[2]
'grimoire'
>>> x[5]
Traceback (most recent call last):
	File "<stdin>", line 1, in <module>
IndexError: list index out of range
```
Python nous avertit que nous avons essayé d'accéder à un indice qui n'existe pas.  
En effet, comme il y a 5 objets dans la liste x, le dernier objet se trouve à l'indice 4.

```python
>>> x[-1]
0.5
```
Vous ne rêvez pas ! On peut également accéder à un élément avec un indice négatif.  
-1 correspondant au dernier élément, -2 à l'avant dernier , etc

####Les sous listes
Les listes offres décidément beaucoup de possibilités. Une d'entre elle est de pouvoir "découper" la liste pour n'en n'utiliser qu'une *tranche*
```python
>>> x = ['baguette', 'bave', 'grimoire', 1, 0.5]
>>> x[1:4] # récupère la liste des objets de l'indice 1 à l'indice 4 non inclus
['bave', 'grimoire', 1]
>>> x[1:-2] # liste des objets de l'indice 1 jusqu'à celui d'indice -2 non inclus
['bave', 'grimoire']
>>> x[1:] # liste des objets de l'indice 1 jusqu'au dernier
['bave', 'grimoire', 1, 0.5]
>>> x[:3] # liste des objets du premier objet jusqu'à l'objet d'indice 3 non inclus
['baguette', 'bave', 'grimoire']
```
## Les tuples
Les tuples sont un deuxième type de collections.  Contrairement au liste, ce sont des objets *immutables*. Cela signifie que une fois créé, un tuple ne peut être modifié.
```python
>>> x = ('baguette', 'bave', 'grimoire', 1, 0.5)
>>> x
('baguette', 'bave', 'grimoire', 1, 0.5)
```
Les tuples partages de nombreuses caractéristiques avec les listes:

 -  Les éléments d'un tuple ont un ordre défini
 - On peut accéder directement à un objet via son indice
	 - Les indices de tuples débutent à zéro
	 - Les indices négatifs comptent à partir du dernier élément du tuple 
 - On peut découper un tuple pour obtenir une tranche
 
 ```python
>>> x = ('baguette', 'bave', 'grimoire', 1, 0.5)
>>> x[1:4] # récupère le tuple avec les objets de l'indice 1 à l'indice 4 non inclus
('bave', 'grimoire', 1)
>>> x[1:-2] #  tuple avec les objets de l'indice 1 jusqu'à celui d'indice -2 non inclus
('bave', 'grimoire')
>>> x[1:] # tuple avec les objets de l'indice 1 jusqu'au dernier
('bave', 'grimoire', 1, 0.5)
>>> x[:3] # tuple avec les objets du premier jusqu'à l'objet d'indice 3 non inclus
('baguette', 'bave', 'grimoire')
```

En revanche, il n'existe aucune façon d'ajouter, modifier ou supprimer un élément.  
 
*Quelle est l'utilité des tuples ?*  

Les tuples sont préconisés lors il n'y a aucun traitement à effectuer sur les objets présent dans le tuple.  
Si on a besoin uniquement de lire les valeurs de objet présent dans une collection, il faudra mieux utiliser les tuples car le traitement de ces derniers est plus rapide que celui des listes.
