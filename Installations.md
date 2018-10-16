
# Anaconda

Anaconda est une plateforme libre de distribution pour Python et R. Il permet de gérer de librairies python via `conda`. Il est supporté par Linux/MacOS/Windows.

## Installation

Il suffit de le télécharger à cette adresse https://www.anaconda.com/download/ et de suivre les étapes d'installations.

## Environnement virtuel

Anaconda permet de créer différents environnements de python, avec différentes versions, différentes librairies etc.

Il faut d'abord vérifier que conda est bien installé via la commande `conda -V`. Ensuite il faut s'assurer que l'on a bien la dernière version via `conda update conda`. On peut maintenant créer un environnement virtuel. Pour cela on utilise la commande : 

>`conda create -n NomDelEnvironnement python=x.x anaconda`

Par exemple on peut utiliser la commande :

>`conda create -n gt-deep-learning python=3.6 anaconda`

Une fois l'environnement installé, il nous faut donc l'activer. La commande pour cela est :

>`source activate NomDelEnvironnement`  sous Linux / MacOs

>`activate NomDelEnvironnement`  sous Windows

Pour le désactiver, on utilise les commandes :
>`source deactivate`  sous Linux / MacOs

>`deactivate`  sous Windows


Dans notre cas, on peut donc utiliser la commande `source activate gt-deep-learning`

Il nous reste donc qu'à installer les librairies python qui nous intéresse pour faire du deep learning.

# TensorFlow

"TensorFlow est un outil open source d'apprentissage automatique développé par Google. Le code source a été ouvert le 9 novembre 2015 par Google et publié sous licence Apache.

Il est basé sur l'infrastructure DistBelief, initiée par Google en 2011, et est doté d'une interface Python.

TensorFlow est l'un des outils les plus utilisés en IA dans le domaine de l'apprentissage machine." Wikipédia.

## Installation

Nous allons utiliser Anaconda pour l'installer. Il suffit de se placer dans l'environnement virtuel que l'on souhaite (pour nous `gt-deep-learning`) et utiliser la commande `conda install tensorflow`. Anaconda va ainsi rechercher les librairies nécessaires à l'utilisation de la librairie TensorFlow et les installer.

Pour vérifier que TensorFlow est bien installé on peut exécuter le "Hello World" suivant (soit dans un fichier `.py`, soit directement dans un interpréteur python)


```python
import tensorflow as tf

hello = tf.constant('Hello, TensorFlow!')


sess = tf.Session()


print(sess.run(hello))
```

    b'Hello, TensorFlow!'


# Keras

Keras est une autre librairie open source permettant de faire du deep learning. Elle se base sur TensorFlow et Theano (encore une autre librairie pour faire du deep learning). Elle a l'avantage d'être de plus haut-niveau, donc il est plus facile de créer de prototype de réseaux de neurones avec. Néanmoins, c'est aussi un inconvénient car on perd en flexibilité.

## Installation

Nous allons aussi utiliser Anaconda pour l'installer. Encore une fois, il suffit de se placer dans l'environnement virtuel que l'on souhaite (pour nous gt-deep-learning) et utiliser la commande `conda install keras`et Anaconda va installer le nécessaire.

Par exemple on créé rapidement un réseau de neurones à plusieurs couches denses de la manière suivante


```python
from keras.models import Sequential
from keras.layers import Dense

model = Sequential()

model.add(Dense(units=64, activation='relu', input_dim=100))
model.add(Dense(units=10, activation='softmax'))

model.summary()
```

    _________________________________________________________________
    Layer (type)                 Output Shape              Param #   
    =================================================================
    dense_1 (Dense)              (None, 64)                6464      
    _________________________________________________________________
    dense_2 (Dense)              (None, 10)                650       
    =================================================================
    Total params: 7,114.0
    Trainable params: 7,114
    Non-trainable params: 0.0
    _________________________________________________________________


    Using TensorFlow backend.


# Liens utiles

Pour la documentation TensorFlow le site https://www.tensorflow.org/ est très complet. Il possède mêmes des tutoriels pour commencer le deep learning.

Pour la documentation Keras le site https://keras.io/ est aussi pratique.
