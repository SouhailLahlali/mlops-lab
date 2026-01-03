# Étape 1 : Créer le dépôt GitHub et connecter le remote

Instructions :

1. Aller sur GitHub → New Repository → nom : `mlops-lab-01`
2. Copier l’URL HTTPS du dépôt.
3. Connecter le dépôt local au remote :

```bash
git remote add origin https://github.com/<USER>/mlops-lab-01.git
git branch -M main
git push -u origin main
```

![Création et connexion GitHub](https://github.com/user-attachments/assets/eabee292-774c-4dc2-8361-5a029b42b43a)

---

# Étape 2 : Définir les secrets GitHub

Instructions :

1. Aller dans : GitHub → Repository → Settings → Secrets and Variables → Actions → New repository secret
2. Créer les secrets suivants :

| Nom               | Valeur                           | Type     |
| ----------------- | -------------------------------- | -------- |
| PY_VERSION        | 3.10                             | variable |
| F1_GATE_THRESHOLD | 0.70                             | variable |
| DEMO_SECRET       | "CI/CD demo secret for students" | secret   |
| APP_ENV           | staging                          | variable |

![Secrets GitHub 1](https://github.com/user-attachments/assets/ef46dc1c-8bbd-4ce7-88a0-90329db5698e)
![Secrets GitHub 2](https://github.com/user-attachments/assets/49a14205-70d7-438c-bccb-fd69274e3e50)

---

# Étape 3 : Créer le workflow CI/CD

![Workflow CI/CD](https://github.com/user-attachments/assets/9a51bd8a-1820-4da3-b284-9879ee627e91)

---

# Étape 4 : Commit et push

Instructions :

1. Aller dans : GitHub → Actions
2. Vérifier :

   * **job ci** : doit installer Python, exécuter les scripts, uploader les artefacts
   * **job cd** : uniquement sur `main`, doit simuler un déploiement SSH

![Actions CI/CD 1](https://github.com/user-attachments/assets/02f59af2-ae49-4b5b-ac62-cede067a9709)
![Actions CI/CD 2](https://github.com/user-attachments/assets/fef0ae77-5450-4e5a-85c9-ad950b147f3c)
