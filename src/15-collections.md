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
-1 correspondant au élément, -2 à l'avant dernier , etc

####Les sous listes
Les listes offres décidément beaucoup de possibilités. Une d'entre elle est de pouvoir "découper" la liste pour n'en n'utiliser qu'une *tranche*
```python
>>> x = ['baguette', 'bave', 'grimoire', 1, 0.5]
>>> x[1:4] # récupère les objets de l'indice 1 à l'indice 4 non inclus
['bave', 'grimoire', 1]
>>> x[1:-2] # de l'objet d'indice 1 jusqu'à celui d'indice -2 n'est pas inclus
['bave', 'grimoire']
>>> x[1:] # de l'objet d'indice 1 jusqu'au dernier
['bave', 'grimoire', 1, 0.5]
>>> x[:3] # du premier objet jusqu'à l'objet d'indice 3 non inclus
['baguette', 'bave', 'grimoire']
```









