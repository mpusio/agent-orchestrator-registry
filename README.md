# Agent Orchestrator Registry

Curated registry of marketplace sources and featured plugins for [Agent Orchestrator](https://github.com/mpusio/agent-orchestrator).

## Adding a Marketplace

1. Fork this repo
2. Add your marketplace entry to `registry.json` under `marketplaces`:

```json
{
  "id": "your-marketplace-id",
  "repo": "owner/repo",
  "description": "Short description of your marketplace",
  "tags": ["tag1", "tag2"],
  "featured": false
}
```

3. Open a Pull Request with:
   - Marketplace name and repo URL
   - Brief description of what plugins it contains
   - At least one working plugin in the marketplace

## Adding a Featured Plugin

Featured plugins highlight noteworthy plugins from existing marketplaces. Add to `featuredPlugins`:

```json
{
  "name": "plugin-name",
  "marketplace": "marketplace-id",
  "description": "What this plugin does",
  "tags": ["relevant", "tags"],
  "category": "category-name"
}
```

## Schema

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `version` | number | yes | Schema version (currently 1) |
| `lastUpdated` | ISO 8601 | yes | Last modification timestamp |
| `marketplaces[].id` | string | yes | Unique marketplace identifier |
| `marketplaces[].repo` | string | yes | GitHub owner/repo |
| `marketplaces[].description` | string | yes | Short description |
| `marketplaces[].tags` | string[] | yes | Searchable tags |
| `marketplaces[].featured` | boolean | no | Show in featured section |
| `featuredPlugins[].name` | string | yes | Plugin name |
| `featuredPlugins[].marketplace` | string | yes | Parent marketplace ID |
| `featuredPlugins[].description` | string | yes | Short description |
| `featuredPlugins[].tags` | string[] | yes | Searchable tags |
| `featuredPlugins[].category` | string | no | Plugin category |
