# Validateur et Sécurisation de Pipelines RAG - TAVARDT France

> Audit d'Isolation de Contexte, Prévention des Injections Indirectes et Protection Défensive de l'IA

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Active-brightgreen)](https://tavardt-france.github.io/rag-security-hardener-fr/)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Security: OWASP LLM](https://img.shields.io/badge/Security-OWASP%20LLM01%20%7C%20LLM02-red.svg)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

## Vue d'Ensemble de l'Architecture et Sécurité RAG

L'architecture de Génération Augmentée par Récupération (RAG) introduit des vecteurs de vulnérabilité critiques dans les applications d'intelligence artificielle d'entreprise. En ingérant des documents externes et des bases de connaissances, l'application s'expose à l'Injection Indirecte de Prompt (OWASP LLM01) et aux Fuites de Données Multi-Tenant (OWASP LLM02).

Ce dépôt fournit une application web interactive s'exécutant 100% dans le navigateur ainsi qu'un outil CLI Python sans dépendance externe pour auditer les architectures RAG et générer des modèles de sécurisation défensive.

## Application Web Interactive

Accédez à l'outil en ligne et auditez votre pipeline en temps réel :

- [https://tavardt-france.github.io/rag-security-hardener-fr/](https://tavardt-france.github.io/rag-security-hardener-fr/)

## Utilisation du Scanner CLI (Python)

L'utilitaire `rag_security_hardener.py` fonctionne avec la bibliothèque standard Python et permet d'automatiser l'audit dans vos pipelines CI/CD ou environnements de développement.

```bash
# Executar avaliacao interativa com parametros padrao
python rag_security_hardener.py

# Exportar middleware defensivo para uso imediato em seu pipeline
python rag_security_hardener.py --export-blueprint secure_rag_middleware.py

# Executar auditoria em modo JSON para integracao em CI/CD
python rag_security_hardener.py --ingestion 3 --vector-db 3 --context-boundary 3 --indirect-filter 3 --json
```

## Contrôles Architecturaux et Mitigations Défensives

1. **Isolation de Contexte** : Encapsulation stricte du contexte avec des balises XML délimitatrices (`<untrusted_context>`) et des consignes système imperméables.
2. **Prévention des Injections Indirectes** : Nettoyage heuristique des instructions masquées et anomalies sémantiques dans les documents ingérés.
3. **Isolation Multi-Tenant (RBAC)** : Ségrégation stricte des vecteurs par espaces de noms et vérification des droits lors des requêtes.
4. **Passerelle de Sortie et Citations** : Vérification d'attribution et masquage actif des données confidentielles.

## Portails Officiels

- **Portail Officiel TAVARDT** : [https://ag.tavardt.com/fr/](https://ag.tavardt.com/fr/)
- **Portail d'Outils** : [https://tools.tavardt.com/fr/](https://tools.tavardt.com/fr/)
- **Contact** : [https://ag.tavardt.com/fr/contact/](https://ag.tavardt.com/fr/contact/)

---
&copy; 2026 TAVARDT France. Tous droits réservés.
