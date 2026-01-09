Blocage automatique du pipeline (Security Gate)
Grâce au paramètre :  --exit-code 1
Trivy force Jenkins à :
Retourner un code d’erreur
Arrêter immédiatement le pipeline
Marquer le build comme FAILURE
Cela garantit qu’aucune image vulnérable ne peut être déployée en production.
Security Gate fonctionne correctement✅
<img width="1516" height="733" alt="image" src="https://github.com/user-attachments/assets/1dbb0d51-682d-43da-be52-0ff06550f179" />
