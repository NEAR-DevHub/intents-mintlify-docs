<picture>
  <source media="(prefers-color-scheme: dark)" srcset="images/logo/dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="images/logo/light.svg">
  <img alt="NEAR Intents" src="images/logo/dark.svg" height="60">
</picture>

# NEAR Intents Documentation

[![Documentation](https://img.shields.io/badge/docs-near--intents.org-blue)](https://docs.near-intents.org)
[![Telegram](https://img.shields.io/badge/chat-Telegram-blue?logo=telegram)](https://t.me/near_intents)
[![X (Twitter)](https://img.shields.io/badge/follow-@near__intents-black?logo=x)](https://x.com/near_intents)
[![GitHub](https://img.shields.io/badge/GitHub-defuse--protocol-black?logo=github)](https://github.com/defuse-protocol)

Official documentation for [NEAR Intents](https://docs.near-intents.org) — a multichain transaction protocol where users specify desired outcomes and market makers compete for best execution.

## Structure

```
├── getting-started/        # Introduction and first swap guide
├── integration/
│   ├── distribution-channels/  # 1Click API docs for app builders
│   ├── market-makers/          # Market maker integration guides
│   └── verifier-contract/      # Direct contract integration
├── api-reference/          # API endpoint specifications
├── resources/              # FAQs, fees, chain support
└── security-compliance/    # Security, compliance, terms
```

## Development

Install the [Mintlify CLI](https://www.npmjs.com/package/mintlify):

```bash
npm i -g mintlify
```

Run local preview:

```bash
mintlify dev
```

View at `http://localhost:3000`

## Contributing

1. Create a branch for your changes
2. Run `mintlify dev` to preview locally
3. Submit a pull request

### Writing Guidelines

- Use second-person voice ("you")
- Include code examples with language tags
- Test all code examples before publishing
- Use relative paths for internal links
- Add frontmatter (title, description) to all pages

## Deployment

Changes pushed to `main` are automatically deployed via [Mintlify](https://dashboard.mintlify.com).

## Resources

- [Live Documentation](https://docs.near-intents.org)
- [NEAR Intents App](https://near-intents.org)
- [Partner Dashboard](https://partners.near-intents.org)
- [Telegram Support](https://t.me/near_intents)
