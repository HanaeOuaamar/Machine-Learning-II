# 🚦   Machine Learning — Série de Travaux Pratiques

Bienvenue dans ce repository qui regroupe une série de 4 Travaux Pratiques (TP) autour du **Machine Learning** et de l'**Apprentissage par Renforcement** réalisés dans le cadre du cours à l'École Nationale de l'Intelligence Artificielle et du Digital Berkane. Accompagnés d'un environnement de simulation de gestion du trafic routier.

---

## 📄 Description

L'objectif de ce projet est d'appliquer des concepts fondamentaux de l'intelligence artificielle et de l'apprentissage automatique à travers 4 TPs progressifs. Les TPs couvrent différents aspects tels que :
- Comprendre la structure d'un environnement Gym en explorant des propriétés et ses actions possibles
- Contrôle manuel de l'agent
-  Implémentation de Q-learning et SARSA
-  Mise à jour de la politique avec PPO

Le fichier **`env_traffic.py`** fournit un environnement de simulation simplifié permettant d'expérimenter et d'évaluer des stratégies de gestion du trafic.

---

## 🗂️ Contenu du Repository
📂 TPs-Machine-Learning-II

├── 📄 README.md  
├── TP1.ipynb  
├── TP2.ipynb   
├── TP3.ipynb
├── TP4.ipynb    
├── env_traffic.py  → Simulation d'environnement de trafic
├── requirements.txt    → Dépendances Python


---

# 📌 A propos des TPs:
## TP1:  Introduction à l'Apprentissage par Renforcement et découverte d'OpenAI Gym
### 🎯 Objectif:
 L'objectif de ce TP est de se familiariser avec les outils de base du Reinforcement Learning (RL) en utilisant
 la bibliothque OpenAI Gymnasium. en découvrant : 
  - la structure d'un environnement Gym,
  - l'espace des actions et observations,
  - les interactions agent-environnement,
  - l'importance d'une politique efficace,
    
    ### 📁 Fichier : TP_01.ipynb
    #### Interprétation:
    
    - Un agent qui agit au hasard ne peut pas maintenir le système stable sur le long terme.

    - Pour améliorer les performances, il est nécessaire de développer une politique intelligente basée sur l'apprentissage par renforcement.

    - Le contrôle manuel est utile pour appréhender les conséquences des actions.

    - L'environnement CartPole est simple mais très efficace pour illustrer les principes de l’apprentissage par renforcement (états, actions, récompenses, épisodes...).

    ## TP2:  Apprentissage par Q-Learning avec FrozenLake
    ### 🎯 Objectif:
    
    Ce TP a pour but de mettre en pratique les fondements du Q-Learning à travers l'environnement FrozenLake de Gymnasium.

    L'objectif est de permettre à un agent d'apprendre à atteindre la cible sans tomber dans l'eau, en maximisant les récompenses.
    
     ### 📁 Fichier : TP_02.ipynb
     #### Interprétation:
    
    Fonctions utiles:
    Q-Learning : Q(s,a) ← Q(s,a) + α[r + γ maxₐ Q(s',a') - Q(s,a)]
    
    SARSA	:   Q(s,a) ← Q(s,a) + α[r + γ Q(s',a') - Q(s,a)]
    
    Ce TP montre comment un agent peut apprendre à maximiser sa récompense dans un environnement incertain.

    Le Q-learning permet, grâce aux essais et erreurs, d'optimiser progressivement une stratégie sans modèle de l'environnement.

    L'environnement FrozenLake constitue un excellent terrain d'expérimentation pour comprendre les bases de l'apprentissage par renforcement.

    ## TP3:  Optimisation des Feux de Circulation par Reinforcement Learning
    ### 🎯 Objectif:
    
    L’objectif de ce TP est d’optimiser la gestion des feux de circulation à l’aide des algorithmes Q-Learning et SARSA. Il vise à comparer ces deux méthodes d’apprentissage 
    par renforcement afin d’analyser leur impact sur la fluidité du trafic.

    ### 📁 Fichier : TP_03.ipynb
    #### 🛠 Changements effectués dans le TP
   🔧 1. Correction des erreurs d'index:
      L'environnement génère des états avec des valeurs pouvant dépasser 9 (à cause de self.state += new_cars), alors que la q_table est définie pour des états compris 
      entre 0 et 9.
      ✅ Correction apportée :
      Ajout de la ligne suivante dans env_traffic.py :
      self.state = np.clip(self.state, 0, 9)
      ✅ Application supplémentaire du clip dans les fonctions train_q_learning() et train_sarsa() :
      state = tuple(np.clip(env.reset(), 0, 9))
      next_state = tuple(np.clip(next_state_raw, 0, 9)

  #### Interprétation:
  Q-Learning est adapté si l'on souhaite maximiser rapidement la performance, quitte à prendre plus de risques dans l’apprentissage.
  SARSA est idéal pour un apprentissage plus sûr et plus stable.
  Les deux méthodes peuvent convenir à l’optimisation du trafic, selon les objectifs (efficacité vs prudence).    lisez ca et ecrivez moi un objevtif de ce tp.

 ## TP4: Proximal Policy Optimization (PPO)

### 🎯 Objectif:
L’objectif de PPO dans ce TP est d’apprendre à un agent à prendre de meilleures décisions (actions) dans un environnement, en mettant à jour sa politique (probabilités d’actions) et sa valeur des états de manière progressive et stable.

 ### 📁 Fichier : TP_04.ipynb
 
   #### Interprétation:
   
Après l'entraînement avec PPO, on constate que l'agent améliore progressivement sa politique. Grâce au mécanisme de clipping, les mises à jour sont modérées, évitant des modifications trop violentes. Les probabilités des bonnes actions augmentent naturellement, et la valeur des états reflète mieux leur utilité future. L’agent devient donc plus compétent à chaque épisode.

## 🚀 Installation & Exécution

### 1. Cloner le repository


```bash
git clone https://github.com/HanaeOuaamar/TPs-Machine-learning-II.git
cd votre-repository
```

### 2. Installer les dépendances

```bash
pip install -r requirements.txt
```
### 3. Exécuter les notebooks 
```bash
jupyter notebook
```





    


## 👥 Auteurs
Réalisé par : [Hanae Ouaamar]

Encadré par : [Mr Mohamed Khalifa Boutahir]

Université : [ENIAD Berkane ]








