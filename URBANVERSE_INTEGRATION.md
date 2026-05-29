# README Addendum — UrbanVerse Integration

> Ce repo est un **fork** de [vercel-labs/opensrc](https://github.com/vercel-labs/opensrc) v0.7.2, integre dans l'ecosysteme gerivdb UrbanVerse (Phase 5, Session F).

## Integration UrbanVerse

```
gerivdb/opensrc (L3 — outillage)
├── utilise par IRIS (L2b) — canal perception externe
├── utilise par ARGUS (L2b) — audit cross-repo sans MCP
├── utilise par KRONOS (L2b) — pattern extraction + diff versions
└── integre dans ECOS-CLI — commande `ecos source <dep>`
```

## Utilisation

```bash
# Fetch le source d'une dependance
opensrc fetch zod
opensrc fetch pypi:requests
opensrc fetch gerivdb/ECOS-CLI

# Obtenir le path local
opensrc path zod

# Lire le source avec rg (instantane, zero appel reseau)
rg "parse" $(opensrc path zod)

# Auditer l'ecosysteme complet
python recall_coherence_check.py --mode opensrc
```

## Gouvernance

- ADR : `GOVERNANCE-HUB/ADR/ADR-009-opensrc-integration.md`
- Registries publics uniquement
- Cache purge via `ecos-clean-opensrc.ps1`

## Remotes

- `origin` : gerivdb/opensrc (ce repo)
- `upstream` : vercel-labs/opensrc (source originale)
