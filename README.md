# [Machine Translation (MT)](#machine-translation-(MT))

## 1. [Type de modele ](#Type-de-modele)
### [1.1. Règle Basée (Rule-Based)](#Règle-Basée (Rule-Based))
### [1.2. Basée sur les Corpus (Statistical Machine Translation, SMT)](#basee-sur-les-Corpus-Statistical-Machine-Translation-SMT)

### [1.3 Neural Machine Translation (NMT)](#Neural-Machine-Translation-(NMT))

## 2. [Neural Machine Translation](#Neural-Machine-Translation)
### [2.1. Seq2Seq avec LSTM/GRU](#Seq2Seq-avec-LSTM/GRU)
### [2.2.Seq2Seq avec Attention Mechanism](#Seq2Seq-avec-Attention-Mechanism)
### [2.3. Transformers](#Transformers)



# Machine Translation

La traduction automatique (Machine Translation, MT) est une sous-discipline du traitement automatique des langues (NLP) qui concerne la traduction automatique de textes d'une langue à une autre à l'aide de logiciels et d'algorithmes.



# Type de modele

## Règle Basée (Rule-Based)

- Utilise des règles linguistiques définies manuellement pour traduire le texte.
- Nécessite une connaissance approfondie des langues source et cible.
- Avantage : Précision linguistique.
- Inconvénient : Peu flexible et difficile à maintenir à grande échelle.

## Basée sur les Corpus (Statistical Machine Translation, SMT)

- Utilise des modèles statistiques entraînés sur de grands corpus bilingues.
- Analyse les probabilités de correspondance entre les segments de texte dans les deux langues.
- Avantage : Peut apprendre à partir de grandes quantités de données.
- Inconvénient : Peut produire des erreurs de traduction et nécessite des corpus bilingues volumineux.


## Neural Machine Translation (NMT)

- Utilise des réseaux de neurones profonds pour modéliser la traduction.

- Modèle de bout en bout qui apprend directement la correspondance entre les phrases source et cible.

- Avantage : Meilleure qualité de traduction, capable de capturer le contexte de manière plus précise.
- Inconvénient : Exige beaucoup de données et de puissance de calcul.

# Neural Machine Translation (NMT) en Détail

Les modèles NMT sont les plus récents et les plus performants pour la traduction automatique.

## Seq2Seq avec LSTM/GRU
Le modèle Seq2Seq (Sequence to Sequence) avec LSTM (Long Short-Term Memory) ou GRU (Gated Recurrent Unit) est une architecture de réseaux de neurones récurrents utilisée pour des tâches comme la traduction automatique. 

Il comporte deux parties principales : l'encodeur et le décodeur.

**Encodeur** : Un RNN (LSTM ou GRU) traite la séquence d'entrée et génère un vecteur de contexte résumant l'information de toute la séquence.

**Décodeur** : Un autre RNN utilise ce vecteur de contexte pour générer la séquence de sortie, prédisant un mot à la fois.

Les LSTM et GRU sont efficaces pour apprendre les dépendances à long terme dans les séquences grâce à leur capacité à surmonter le problème de gradient évanescent. 

Ils sont couramment utilisés pour la traduction automatique, le résumé automatique et la génération de texte. 

Bien que les transformateurs soient plus récents et souvent plus performants, les modèles Seq2Seq avec LSTM/GRU restent importants pour comprendre les bases des tâches de séquence à séquence.

# Seq2Seq avec Attention Mechanism

Le modèle Seq2Seq avec mécanisme d'attention améliore les architectures Seq2Seq classiques pour des tâches comme la traduction automatique.

**Encodeur** : Un RNN (LSTM ou GRU) traite la séquence d'entrée et génère une série d'états cachés pour chaque mot.

**Décodeur avec Attention** : Le décodeur utilise un mécanisme d'attention pour pondérer les états cachés de l'encodeur à chaque étape de la génération de la séquence de sortie. Cela permet au décodeur de se concentrer sur les parties pertinentes de l'entrée pour chaque mot généré.

Le modèle Seq2Seq avec mécanisme d'attention améliore la performance en capturant mieux les dépendances à long terme et les relations complexes, offre une interprétabilité en montrant quelles parties de l'entrée sont importantes pour chaque mot de la sortie, et est utilisé pour la traduction automatique, le résumé automatique et la génération de texte.

# Transformers

**Description** : Introduit par Vaswani et al. en 2017, les Transformers utilisent des mécanismes d'attention auto-régressive pour traiter les séquences en parallèle. Ils n'utilisent pas de mécanismes récurrents.

**Avantages** : Excellente parallélisation, capacité à capturer les relations à longue distance plus efficacement, et performances supérieures sur de nombreux benchmarks de traduction automatique.








