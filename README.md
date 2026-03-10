## Project setup
### z.ai for Claude

Configure ~/.claude/settings.json 

{
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "your_zai_api_key",
    "ANTHROPIC_BASE_URL": "https://api.z.ai/api/anthropic",
    "API_TIMEOUT_MS": "3000000",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "glm-4.5-air",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "glm-4.7",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "glm-5"
  },
  "enabledPlugins": {
    "compound-engineering@compound-engineering-plugin": true
  },
  "extraKnownMarketplaces": {
    "compound-engineering-plugin": {
      "source": {
        "source": "github",
        "repo": "EveryInc/compound-engineering-plugin"
      }
    }
  },
  "shellSnapshotEnabled": false,
  "skipDangerousModePermissionPrompt": false
}

**Note:** skipDangerousModePermissionPrompt is set to false. If you run Claude explicitly in container you may want to change this to true. Container is, however, connected to host file system so be careful choosing your risk levels.