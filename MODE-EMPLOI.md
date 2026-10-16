# Mettre le site en ligne (≈ 15 minutes, gratuit)

## 1. Personnaliser la soirée
Ouvre `index.html` dans un éditeur de texte (Bloc-notes suffit) et cherche `const SOIREE`.
Change la date, l'heure, le lieu et ton prénom.

## 2. Activer l'e-mail de confirmation (EmailJS)
1. Crée un compte gratuit sur https://www.emailjs.com (200 e-mails/mois offerts).
2. **Email Services → Add New Service → Gmail**, connecte ta boîte. Note le **Service ID**.
3. **Email Templates → Create New Template**, puis remplis :
   - **To Email** : `{{email}}`
   - **Bcc** : ton adresse e-mail (comme ça tu reçois une copie de chaque inscription)
   - **Subject** : `C'est confirmé {{prenom}} : soirée du {{soiree_date}} !`
   - **Content** :

```
Salut {{prenom}} !

Ton inscription à la soirée est bien enregistrée.

Quand : {{soiree_date}}, {{soiree_heure}}
Où : {{soiree_lieu}}

Ce que tu nous as dit :
- Boisson : {{boisson}}
- Assiette : {{regime}} (allergies : {{allergies}})
- Chanson pour la playlist : {{chanson}}
- Niveau de danse : {{danse}}
- Départ prévu : {{depart}}
- Tu ramènes : {{ramene}}
- Talent caché : {{talent}}
- Ton mot : {{mot}}

Infos de contact : {{nom}}, né·e le {{naissance}}, {{tel}}

À très vite !
{{hote}}
```

   Enregistre et note le **Template ID**.
4. **Account → API keys** : copie la **Public Key**.
5. Dans `index.html`, cherche `const EMAILJS` et colle les 3 valeurs entre les guillemets.

## 3. Mettre en ligne
1. Va sur https://app.netlify.com/drop
2. Glisse-dépose le dossier qui contient `index.html`.
3. Netlify te donne un lien : envoie-le à tes invités.
