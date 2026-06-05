# Seance 23 - Chatbot IA vocal + texte - moments importants

- Video : `2026-06-05 16-40-51.mp4`
- Duree detectee : 02:01:14
- Transcription brute : `seance-23-chatbot-ia-vocal-texte-transcription.txt`
- Segments JSON : `seance-23-chatbot-ia-vocal-texte-segments.json`

## Logique de la seance

- **Sections 01-10 - Cadrer la V1** : Je transforme le RAG restaurant en assistant utile pour un client.
- **Sections 11-20 - Brancher le RAG** : Je garde les cles cote serveur et je fais parler Supabase avec OpenAI.
- **Sections 21-30 - Tester le texte** : Je controle les reponses, les sources et le ton cote client.
- **Sections 31-40 - Passer au design client** : Je quitte le prototype technique pour une experience restaurant.
- **Sections 41-50 - Construire le widget** : Je pose le site, le bouton, le panneau et les usages mobiles.
- **Sections 51-60 - Ajouter la voix** : Je choisis un pipeline vocal simple, stable et reutilisable.
- **Sections 61-70 - Corriger le retrieval** : Je repare les horaires, le menu du soir et les options vegetariennes.
- **Sections 71-80 - Publier la V1** : Je cree un lien testable, je verifie et je demande un retour client.

## Prompts repris ou reconstruits proprement

### Section 03

```text
Maintenant qu'on a cree le RAG restaurant, cree un chatbot textuel connecte a ce RAG.

Fais d'abord les recherches necessaires sur les bonnes pratiques recentes OpenAI/Supabase.

Architecture attendue :
- serveur Node cote backend
- page HTML/CSS/JS cote client
- aucune cle OpenAI exposee dans le navigateur
- endpoint /api/chat
- endpoint /api/health
- tests curl et Playwright

Le chatbot doit repondre aux questions clients sur :
- carte et menus
- horaires
- reservations
- allergies et regimes
- groupes et privatisations

Garde une V1 simple et testable.
```

### Section 18

```text
Tu es l'assistant textuel du restaurant Maison Denem.

Objectif :
- Repondre en francais naturel, utile, concis et professionnel.
- Utiliser uniquement les extraits fournis dans CONTEXTE_RAG.
- Ne jamais afficher les references internes [S1], [S2] ou les noms de fichiers.
- Repondre comme une personne qui travaille a l'accueil du restaurant.

Regles strictes :
- Si l'information est presente, reponds directement.
- Si le contexte ne permet pas de repondre avec certitude, dis-le clairement.
- Ne confirme jamais une reservation reelle, une disponibilite definitive ou une allergie garantie sans validation humaine.
- Ne mentionne pas tables SQL, embeddings, chunks ou mecanismes internes.
- Evite : "d'apres les informations disponibles", "selon les informations", "il semble", "dans notre base".
```

### Section 23

```text
Le design de test n'est pas assez propre.

Je veux une interface tres simple, proche d'une experience ChatGPT/OpenAI :
- page claire
- champ de saisie lisible
- reponses propres
- aucun panneau technique visible pour le client
- responsive desktop/mobile
- design sobre et premium

Garde le debug uniquement pour les tests, pas pour l'utilisateur final.
```

### Section 33

```text
N'oublie pas que c'est pour un client.

L'utilisateur final se fiche de voir :
- les sources
- les scores
- les metriques
- les chunks

Rapproche-toi d'un design client propre :
- site restaurant Maison Denem
- hero premium
- navigation simple
- widget assistant en bas a droite
- reponse client uniquement
- ton naturel et chaleureux.
```

### Section 42

```text
J'aimerais rajouter une partie vocale pour les demandes clients.

Le client doit pouvoir parler au widget et recevoir une reponse vocale.

Fais des recherches sur les docs OpenAI actuelles, puis propose l'architecture la plus simple et la plus sure en reutilisant notre RAG existant.

Je veux garder :
- la logique RAG cote serveur
- les cles privees cote serveur
- une experience simple pour le client
- des tests texte et vocal avant publication.
```

### Section 54

```text
La voix fonctionne, mais le RAG ne donne pas les horaires exacts.

Corrige le retrieval et/ou la logique de reponse pour que les questions suivantes retournent les horaires precis quand ils existent :
- lundi midi
- lundi soir
- dimanche midi
- dimanche soir
- horaires d'ouverture

Teste en texte et en vocal.
Ne donne pas de formule de doute si le contexte contient l'information exacte.
```

### Section 63

```text
Le menu du soir ne remonte pas correctement.

Le retrieval est trop influence par l'historique et par le mot "soir".

Corrige pour que les demandes suivantes lisent les chunks menu structures :
- menu
- carte
- ce qu'on mange
- menu du soir
- options vegetariennes

Objectif :
- retourner la carte complete quand elle existe
- entrees, plats, desserts, menu degustation
- ne pas basculer vers les horaires juste parce que le client dit "soir"
- tester texte et vocal apres correction.
```

### Section 72

```text
Publie une V1 publique propre.

Contraintes :
- ne pousse pas la video
- ne pousse pas .env
- ne pousse pas les fichiers temporaires
- garde seulement index.html, styles.css, app.js, favicon et README
- active GitHub Pages sur main /
- verifie que l'URL repond en HTTP 200
- ouvre la page publique et teste le widget
```

### Section 74

```text
Ecris-moi un mail tres amical pour Guillaume.

Dis-lui :
- que la V1 de l'assistant IA restaurant est en ligne
- qu'il peut tester le lien
- que je veux son retour sur l'experience client
- qu'il peut tester la carte, les horaires, les options vegetariennes et la partie vocale
- que je ferai les ajustements ensuite

Ton :
- simple
- amical
- court
- pas corporate
```
