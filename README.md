# Hub de Durcissement et Sécurité des Pipelines RAG

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-5b3cf5.svg)](https://tavardt-france.github.io/rag-security-hardener-fr/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![OWASP LLM](https://img.shields.io/badge/OWASP-LLM%20Top%2010-red.svg)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
[![MITRE ATLAS](https://img.shields.io/badge/MITRE-ATLAS%20Matrix-orange.svg)](https://atlas.mitre.org/)

**Hub d'Architecture Défensive et Blueprints de Durcissement pour Pipelines RAG (Retrieval-Augmented Generation)**

Développé et maintenu par la division d'ingénierie de sécurité en intelligence artificielle de **TAVARDT**.

***

## Démonstration en Ligne & Hub d'Architecture Défensive

Vous pouvez consulter les spécifications techniques, les diagnostics architecturaux et les blueprints de durcissement directement dans votre navigateur :

* **[Application Web Officielle sur GitHub Pages](https://tavardt-france.github.io/rag-security-hardener-fr/)**
* **Centre d'Outils TAVARDT**

> [!NOTE]
> **Périmètre d'Exécution Technique :** Ce hub web fournit des spécifications d'architecture défensive et des blueprints de configuration. Les audits actifs des bases vectorielles et de l'intégrité du contexte requièrent des identifiants d'environnement et doivent être exécutés au sein de l'application via l'utilitaire CLI officiel (`rag_security_auditor.py`). Les pages web exécutées dans le bac à sable d'un navigateur ne peuvent se connecter directement aux clusters vectoriels privés.

***

## Blueprints Techniques de Durcissement

1. **rag-security-policy.yml :** Politiques de sécurité d'entreprise définissant les limites de chunks, les balises XML d'isolation de contexte et les règles de validation sémantique.
2. **rag_chunk_sanitizer.py :** Pipeline d'assainissement éliminant les caractères invisibles Unicode, les séquences d'échappement et les marqueurs d'injection de prompt avant la génération d'embeddings.
3. **vector_acl_filter.json :** Schéma de requête vectorielle imposant des filtres obligatoires de contrôle d'accès (RBAC/ACL) par utilisateur et par tenant pour empêcher l'exfiltration inter-organisations.
4. **rag_context_template.xml :** Modèle d'encapsulation de contexte délimité par des balises XML avec directives strictes de non-exécution pour modèles LLM.
5. **rag_security_auditor.py :** Utilitaire CLI local déterministe exécuté dans l'environnement de l'application pour auditer directement les configurations de pipelines RAG et vérifier la conformité OWASP LLM.

***

## Utilisation de l'Outil CLI Déterministe

Pour exécuter l'inspection déterministe directement dans l'environnement de l'application RAG :

```bash
# 1. Télécharger le script d'audit depuis le dépôt officiel
curl -sO https://raw.githubusercontent.com/TAVARDT-France/rag-security-hardener-fr/main/rag_security_auditor.py

# 2. Inspecter le pipeline et les spécifications défensives
python3 rag_security_auditor.py

# 3. Exporter les résultats au format JSON structuré
python3 rag_security_auditor.py -json
```

***

## Liens Utiles

* **Portail Entreprise:** https://ag.tavardt.com/fr/
* **Suite de Diagnostic:** https://tools.tavardt.com/fr/
* **Contact Technique:** https://ag.tavardt.com/fr/contact/

***

© 2026 TAVARDT. Tous droits réservés.
