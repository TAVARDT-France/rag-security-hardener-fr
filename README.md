# Hub de Durcissement et Sécurité des Pipelines RAG

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-5b3cf5.svg)](https://tavardt-france.github.io/rag-security-hardener-fr/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

***

Moteur d'évaluation de sécurité et de renforcement contextuel pour architectures RAG (Retrieval-Augmented Generation) conçu par **TAVARDT**. Ancré dans les standards OWASP LLM01, OWASP LLM04, OWASP LLM07 et MITRE ATLAS, ce kit audite le cloisonnement vectoriel multilocataire, assainit les injections indirectes et exporte des middlewares défensifs.

***

## Fonctionnalités Clés et Architecture Défensive

* **Audit Déterministe des Pipelines** : Valide l'isolation contextuelle, les filtres de métadonnées et les quotas de segmentation face aux exigences formelles de sécurité.
* **Production Automatisée de Middleware** : Exporte des classes Python modulaires configurées pour assainir les contextes extraits et imposer un encapsulement XML strict.
* **Contrôle du Cloisonnement Multilocataire** : Confirme que les requêtes vectorielles imposent des filtres d'accès cryptographiques pour interdire les fuites de données entre comptes.

***

## Vecteurs de Risque et Impact Opérationnel

Traiter des flux RAG sans isolation stricte du contexte autorise des charges malveillantes insérées dans des sources externes à détourner l'exécution du modèle. Le toolkit analyse cinq domaines critiques de sécurité :

* **Intégrité de l'Ingestion Documentaire** : Audite les flux d'ingestion face aux injections stéganographiques dans les PDF, caractères de contrôle unicode et formats malveillants (Déduction : jusqu'à -25 points).
* **Cloisonnement Multilocataire en Base Vectorielle** : Repère les collections partagées dépourvues d'isolation stricte par espaces de noms ou métadonnées d'accès (Déduction : jusqu'à -30 points).
* **Encapsulation des Frontières Contextuelles** : Interdit la concaténation directe de textes en exigeant des balises XML fermées avec consignes d'exclusion d'ordres (Déduction : jusqu'à -25 points).
* **Filtrage des Injections Indirectes de Prompt** : Déploie des filtres d'expressions régulières compilés pour neutraliser les commandes d'évasion dissimulées (Déduction : jusqu'à -20 points).
* **Garde-fous de Validation des Réponses et Masquage** : Impose la vérification des citations et le masquage des données sensibles avant délivrance au client (Déduction : jusqu'à -15 points).

Les pipelines inspectés reçoivent une note cumulée de 10 à 100 points. Le rapport classe l'architecture en statut **HARDENED** (85 à 100 points), **MODERATE** (50 à 84 points) ou **CRITICAL** (inférieur à 50 points), bloquant ainsi les déploiements non conformes.

***

## Installation et Utilisation CLI

Évaluez la sécurité de vos flux ou exportez des briques de middleware à l'aide de commandes Python standard :

```bash
# Cloner le dépôt officiel
git clone https://github.com/TAVARDT-France/rag-security-hardener-fr.git

# Accéder au dossier de travail
cd rag-security-hardener-fr

# Évaluer le pipeline RAG sur tous les niveaux défensifs
python rag_security_hardener.py -i 3 -v 3 -c 3 -f 3 -g 3

# Exporter le middleware de protection en Python
python rag_security_hardener.py -i 3 -v 3 -c 3 -f 3 -g 3 -e defensive_rag_middleware.py

# Exporter le rapport structuré au format JSON
python rag_security_hardener.py -i 3 -v 3 -c 3 -f 3 -g 3 -j
```

***

## FAQ Technique

### Quels vecteurs de vulnérabilité le kit de sécurité RAG évalue-t-il dans les flux de récupération ?

L'outil inspecte les pipelines face à l'ingestion de documents non authentifiés, aux fuites multilocataires en base vectorielle, à la rupture des frontières contextuelles, aux injections indirectes et aux sorties non filtrées. L'architecture évaluée obtient une note de robustesse de 10 à 100 points la classant en statut HARDENED, MODERATE ou CRITICAL.

### En quoi l'encapsulation contextuelle en balises XML neutralise-t-elle les injections indirectes ?

Isoler les fragments documentaires au sein de balises XML strictes trace une frontière étanche entre connaissances externes et consignes système impératives. Ce cloisonnement empêche les commandes hostiles dissimulées dans des sources tierces d'être interprétées comme des instructions exécutables par le modèle.

### Pourquoi le filtrage par métadonnées de locataire est-il indispensable dans les bases vectorielles ?

En l'absence de compartimentage rigoureux par espaces de noms ou métadonnées vérifiées, les recherches sémantiques risquent d'extraire des fragments appartenant à d'autres comptes. Appliquer un contrôle d'accès strict lors des requêtes vectorielles prévient toute fuite latérale de données sensibles entre organisations distinctes.

### Quelles garanties défensives le canevas de middleware exporté apporte-t-il à l'application ?

L'exportation du fichier avec l'option -e fournit une classe de garde en Python capable de neutraliser les motifs d'attaque et de normaliser les balises avant l'assemblage final du prompt. Cette barrière logicielle intercepte les tentatives de contournement de consignes et l'exfiltration de secrets au moment de l'exécution.

### Le kit de durcissement peut-il s'intégrer dans les chaînes d'intégration continue CI/CD ?

Les scripts CLI traitent les niveaux de configuration ou les fichiers locaux en produisant des rapports exploitables grâce au paramètre -j. Les flux d'automatisation peuvent analyser le score JSON obtenu afin d'interrompre immédiatement les déploiements ne respectant pas les critères de sécurité.

***

## Liens Utiles

* **Portail Institutionnel:** https://ag.tavardt.com/fr/
* **Suite de Diagnostic:** https://tools.tavardt.com/fr/
* **Contact Technique:** https://ag.tavardt.com/fr/contact/

***

### Licence
Distribué sous licence MIT. Consultez [LICENSE](LICENSE) pour plus d'informations.

***

© 2026 TAVARDT. Tous droits réservés.
