# [Machine Translation (MT)](#machine-translation-(mt))

## 1. [Types de modèles](#types-de-modèles)
### [1.1. Basé sur des règles (Rule-Based)](#basé-sur-des-règles-(rule-based))
### [1.2. Basé sur les corpus (Statistical Machine Translation, SMT)](#basé-sur-les-corpus-(statistical-machine-translation-smt))
### [1.3 Neural Machine Translation (NMT)](#neural-machine-translation-(nmt))

## 2. [Neural Machine Translation](#neural-machine-translation)
### [2.1. Seq2Seq avec LSTM/GRU](#seq2seq-avec-lstm/gru)
### [2.2. Seq2Seq avec mécanisme d'attention](#seq2seq-avec-mécanisme-d'attention)
### [2.3. Transformers](#transformers)

## 3. [Modèles récents de Machine Translation](#modèles-récents-de-machine-translation)
   [3.1. M2M-100](#m2m-100)

   [3.2. NLLB-200](#nllb-200)

## 4. [Métriques d'évaluation en Machine Translation](#métriques-d'évaluation-en-machine-translation)

## 5. [Quelques notions importantes à savoir](#quelques-notions-importantes-à-savoir)






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


### Modèles récents de Machine Translation

#### 3.1. M2M-100
M2M-100 est un modèle de traduction automatique multilingue développé par Facebook AI, capable de traduire directement entre 100 langues sans passer par une langue pivot comme l'anglais. Il utilise un réseau de neurones transformateur pour fournir des traductions de haute qualité. Pour en savoir plus sur le M2M-100, visitez ce [lien](https://huggingface.co/transformers/v4.5.1/model_doc/wav2vec2.html).

#### 3.2. NLLB-200
NLLB-200 (No Language Left Behind) est un autre modèle multilingue conçu pour améliorer la traduction automatique dans des langues moins représentées. Ce modèle, également basé sur l'architecture des transformateurs, vise à rendre la traduction plus accessible et précise pour une large gamme de langues. Pour en savoir plus sur le NLLB-200, visitez ce [lien](https://huggingface.co/docs/transformers/model_doc/nllb).

### Métriques d'évaluation en Machine Translation

Les métriques d'évaluation en traduction automatique mesurent la qualité des traductions produites par les modèles. Parmi les plus courantes, on trouve :
- **BLEU (Bilingual Evaluation Understudy)** : Évalue la précision en comparant les n-grammes de la traduction générée à ceux de la référence.
- **METEOR (Metric for Evaluation of Translation with Explicit ORdering)** : Prend en compte la précision, le rappel, et l'ordre des mots.
- **TER (Translation Edit Rate)** : Mesure le nombre de modifications nécessaires pour convertir la traduction générée en la référence.
- **ROUGE (Recall-Oriented Understudy for Gisting Evaluation)** : Utilisé principalement pour l'évaluation des résumés, mais applicable à la traduction.

Chaque métrique a ses propres critères et méthodes pour évaluer la précision, la fluidité et l'adéquation des traductions.

### Quelques notions importantes à savoir

Pour bien comprendre et travailler avec la traduction automatique, il est essentiel de connaître certains concepts clés :
- **Alignement des phrases** : Processus de mise en correspondance des segments de texte entre les langues source et cible.
- **Corpus parallèle** : Ensemble de textes alignés phrase par phrase dans deux langues différentes, utilisé pour entraîner et évaluer les modèles de traduction.
- **Mécanisme d'attention** : Technique utilisée dans les modèles de réseaux de neurones pour se concentrer sur les parties pertinentes de la séquence d'entrée lors de la génération de la sortie.
- **Surapprentissage (Overfitting)** : Problème où un modèle apprend trop précisément les détails d'un jeu de données d'entraînement, ce qui réduit sa capacité à généraliser à de nouvelles données.
- **Model pruning** : Technique visant à réduire la taille d'un modèle en supprimant les poids et connexions jugés non essentiels, ce qui permet d'améliorer l'efficacité et de réduire les besoins en calcul.
- **Model distillation** : Processus dans lequel un modèle plus petit (student) est entraîné pour reproduire les sorties d'un modèle plus grand et plus performant (teacher), permettant ainsi de créer des modèles plus légers et plus rapides tout en conservant une grande partie de la performance du modèle original.

Ces notions sont essentielles pour comprendre les défis et les solutions associés à la traduction automatique.




