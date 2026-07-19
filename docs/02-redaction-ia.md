# 02 — La rédaction IA : agents, workflow, gouvernance

## Principe

Une rédaction entièrement composée d'agents IA, avec **un rédacteur en chef humain** (le fondateur au départ) qui fixe la ligne, valide et publie. L'IA produit ; l'humain décide.

## Les agents

### Amont (recherche et fiabilité)

| Agent | Rôle | Entrées | Sorties |
|---|---|---|---|
| **Veilleur / journaliste** | Scanner l'actualité (IA, wearables, santé, longévité, neurosciences, design) : publications scientifiques, annonces produits, brevets, conférences, signaux faibles | Flux RSS, alertes, APIs, newsletters sources | Liste quotidienne de sujets scorés (nouveauté, affinité audience, potentiel viral) |
| **Fact-checker** | Vérifier chaque affirmation : remonter à la source primaire, qualifier le niveau de preuve (étude peer-reviewed vs communiqué de presse), signaler les zones d'incertitude | Brouillons + sujets retenus | Fiche de vérification par article, liens sources, mentions de réserve à intégrer |

### Production

| Agent | Rôle |
|---|---|
| **Rédacteur d'articles** | Écrire l'article de fond à partir du sujet validé et de la fiche de vérification, dans le ton du média (voir [03-ligne-editoriale.md](03-ligne-editoriale.md)) |
| **Agent SEO** | Recherche de mots-clés, structure Hn, maillage interne, métadonnées, articles evergreen ciblant les requêtes du territoire (« bague connectée vs montre », « suivi du sommeil », etc.) |

### Distribution (un agent par canal, chacun avec le format natif du canal)

| Agent | Format |
|---|---|
| **Agent LinkedIn** | Posts d'opinion et d'analyse, angle professionnel/futur du travail et de la santé |
| **Agent X** | Threads synthétiques, réactions à chaud à l'actualité |
| **Agent TikTok** | Scripts de vidéos courtes (hook < 3 s, 30–60 s), briefs de tournage ou de montage |
| **Agent newsletter** | Édition hebdomadaire : sélection, éditorial, curation |
| **Agent emails** | Séquences d'accueil, réactivation, annonces (dont lancements ONYRA) |

Chaque agent de distribution **repart de l'article validé**, jamais du brouillon : la vérification est faite une fois, en amont, pour tous les canaux.

## Le workflow quotidien

```
Veilleur ──> shortlist de sujets
                 │
                 ▼
   [HUMAIN] choix des sujets du jour        ← décision n°1
                 │
                 ▼
Fact-checker ──> fiche de vérification
                 │
                 ▼
Rédacteur ──> article + Agent SEO
                 │
                 ▼
   [HUMAIN] validation / réécriture / refus  ← décision n°2 (rien ne sort sans elle)
                 │
                 ▼
Agents LinkedIn · X · TikTok · Newsletter · Emails
                 │
                 ▼
   [HUMAIN] relecture rapide des déclinaisons, programmation  ← décision n°3
```

Charge humaine visée : **1 à 2 h par jour** en rythme de croisière. Si la validation prend plus de temps que l'écriture manuelle, la machine est mal réglée — on corrige les prompts/consignes des agents, pas le volume.

## Règles de gouvernance

1. **Aucune publication sans validation humaine.** Pas d'auto-publication, même pour les formats courts.
2. **Toute affirmation factuelle a une source primaire** consignée par le fact-checker. En cas de doute non levé : on ne publie pas, ou on publie avec la réserve explicite.
3. **Erreur publiée = correction visible** (édition avec mention, pas de suppression silencieuse).
4. **Journal de production** : chaque contenu garde la trace sujet → sources → versions → validation. Utile pour la qualité, la responsabilité et l'amélioration des agents.
5. **Les agents n'inventent jamais de citations, de chiffres ou d'études.** Consigne explicite dans chaque prompt système, contrôlée par le fact-checker.

## Montée en charge

- **Phase 1 (mois 1–3)** : 2 canaux (LinkedIn + newsletter), agents veilleur/fact-checker/rédacteur. Le fondateur valide tout.
- **Phase 2 (mois 4–6)** : ajout X et SEO. Cadence quotidienne LinkedIn, hebdo newsletter.
- **Phase 3 (mois 7–12)** : TikTok (le canal le plus coûteux en production), emails, éventuellement podcast. Possibilité d'un éditeur humain freelance en second regard.

Détail des jalons dans [04-roadmap-kpis.md](04-roadmap-kpis.md).
