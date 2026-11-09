# Fiche de cadrage — Sujet 13 : Collecte des déchets
## Module : Systèmes Multi-Agents appliqués à l'IoT — Master MSID S3

### 1. Membres du groupe
- [Votre Nom 1] — Modélisation & Théorie
- [Votre Nom 2] — Conception UML & MQTT
- [Votre Nom 3] — Simulateur Python

### 2. Problématique
Aujourd'hui, les camions de collecte suivent des tournées fixes : ils vident
des bacs à moitié vides tandis que d'autres débordent. Avec les capteurs de
remplissage installés sur les bacs, comment permettre à des camions-agents de
se répartir dynamiquement les bacs à vider, sans planificateur central, tout
en respectant leur capacité et la durée de travail des équipes ?

### 3. Questions de recherche retenues
- (Obligatoire) Q1 — Écart d'utilité entre équilibre de Nash et optimum
  social : que vaut le prix de l'anarchie ?
- (Obligatoire) Q2 — Convergence du consensus et robustesse à la panne d'un
  camion en cours de tournée.
- (Au choix) Q3 — Nombre de débordements évités et kilomètres économisés par
  rapport à des tournées fixes. *(Note : vous pouvez remplacer par Q4 - Équité si vous préférez)*

### 4. Approche proposée (5 lignes maximum)
Agents à utilité (BinAgent, TruckAgent, DepotAgent, CityAgent) communicant via
un broker MQTT. Chaque camion maximise U_c(B_c) = Σ w_b f_b − c δ(B_c).
Une base de connaissances fournit les priorités (zones sensibles, jours de
marché) pour pondérer w_b. Les camions se répartissent les bacs par consensus
distribué (CBBA). La théorie des jeux (Nash, Shapley) mesure le prix de
l'anarchie et partage les coûts. Quatre scénarios sont comparés : égoïstes,
Nash, consensus, optimum centralisé.

### 5. Cinq références de départ
[1] S. Russell, P. Norvig, Artificial Intelligence: A Modern Approach, Pearson.
[2] Y. Shoham, K. Leyton-Brown, Multiagent Systems, Cambridge University Press, 2009.
[3] R. Olfati-Saber et al., « Consensus and Cooperation in Networked Multi-Agent
    Systems », Proceedings of the IEEE, 2007.
[6] H.-L. Choi, L. Brunet, J. P. How, « Consensus-Based Decentralized Auctions
    for Robust Task Allocation », IEEE Transactions on Robotics, 2009.
[8] OASIS, MQTT Version 3.1.1 (2014) et MQTT Version 5.0 (2019).

### 6. Répartition prévue du travail
| Tâche | Membre 1 | Membre 2 | Membre 3 |
|---|---|---|---|
| Formalisation (utilités, jeu, PoA) | ✓ | | |
| Diagrammes UML (classes, séquence) | | ✓ | |
| Spécification MQTT (topics, QoS, LWT) | | ✓ | |
| Base de connaissances | ✓ | | |
| Simulateur Python + broker Mosquitto | | | ✓ |
| Rédaction article (Intro, SoA, Formalisation) | ✓ | | |
| Rédaction article (Architecture, Discussion) | | ✓ | |
| Rédaction article (Expériences, Conclusion) | | | ✓ |
| Soutenance (5 min chacun) | ✓ | ✓ | ✓ |

### 7. Risques identifiés et parades
- Complexité de CBBA → prévoir un fallback Contract Net plus simple.
- Broker MQTT local → installer Mosquitto dès la semaine 3.
- Charge de rédaction → commencer la section Experiments dès la semaine 7.