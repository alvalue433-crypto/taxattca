# Prompts système des agents

Chaque fichier est le prompt système d'un agent de la rédaction. Tous héritent de la [charte des agents](../docs/05-charte-agents.md) : la coller en tête du prompt, ou l'injecter en préambule système si l'outil le permet.

## Amont

| Fichier | Agent | Déclenchement |
|---|---|---|
| [`01-veilleur.md`](01-veilleur.md) | Veilleur / journaliste | Quotidien, 6 h |
| [`02-fact-checker.md`](02-fact-checker.md) | Fact-checker | Après sélection humaine des sujets |

## Production

| Fichier | Agent | Déclenchement |
|---|---|---|
| [`03-redacteur.md`](03-redacteur.md) | Rédacteur d'articles | Après fiche de vérification |
| [`04-seo.md`](04-seo.md) | SEO | En parallèle du rédacteur |

## Distribution — uniquement à partir d'un article **validé**

| Fichier | Agent |
|---|---|
| [`05-linkedin.md`](05-linkedin.md) | LinkedIn |
| [`06-x.md`](06-x.md) | X |
| [`07-tiktok.md`](07-tiktok.md) | TikTok |
| [`08-newsletter.md`](08-newsletter.md) | Newsletter |
| [`09-emails.md`](09-emails.md) | Emails |

## Règle de chaînage

```
veilleur → [humain] → fact-checker → rédacteur (+ SEO) → [humain] → distribution → [humain] → publication
```

Les agents de distribution partent **toujours** de l'article validé, jamais d'un brouillon : la vérification est faite une fois, en amont, pour tous les canaux. Un agent de distribution n'ajoute aucun fait absent de l'article source.

## Convention de nommage des variables

Les prompts utilisent des variables entre accolades, à remplacer à l'exécution :

- `{NOM_MEDIA}` — nom du média (à figer après la phase 0)
- `{DATE}` — date du jour
- `{SUJET}` — sujet retenu
- `{ARTICLE_VALIDE}` — texte de l'article validé
- `{FICHE_VERIF}` — fiche de vérification
- `{BRIEF}` — consignes du rédacteur en chef pour ce contenu
