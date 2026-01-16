# Agentics Foundation - Summarizer Bot Custom Prompts

This repository contains custom prompt templates for the Agentics Foundation Discord summarizer bot.

## 📁 Repository Structure

```
summarizer-bot-rules/
├── PATH                         # Routing configuration
├── README.md                    # This file
└── prompts/
    ├── default.md              # Global fallback prompt
    ├── discussion/
    │   └── default.md         # Discussion category prompts
    ├── meeting/
    │   └── default.md         # Meeting category prompts
    └── moderation/
        └── default.md         # Moderation category prompts
```

## 🎯 How It Works

The bot uses the `PATH` file to determine which prompt to use based on:
- **Category**: discussion, meeting, or moderation
- **Channel**: The Discord channel name
- **Summary Type**: brief, detailed, or comprehensive

### Routing Logic

1. First tries: `prompts/{category}/{channel}.md` (channel-specific)
2. Then tries: `prompts/{category}/default.md` (category default)
3. Falls back to: `prompts/default.md` (global fallback)

## 📝 Available Variables

All prompt files can use these template variables:

- `{category}` - discussion, meeting, or moderation
- `{channel}` - Discord channel name
- `{summary_type}` - brief, detailed, or comprehensive
- `{message_count}` - Number of messages being summarized
- `{messages}` - The actual message content

## 🎨 Customization

### Adding Channel-Specific Prompts

To create a custom prompt for a specific channel:

```bash
# For #general channel discussions
prompts/discussion/general.md

# For #team-meetings channel
prompts/meeting/team-meetings.md
```

### Modifying Existing Prompts

1. Edit the appropriate `.md` file
2. Commit and push to GitHub
3. In Discord, run: `/prompt-config refresh`
4. Test with: `/prompt-config test discussion`

## 🔄 Bot Commands

Configure the bot to use these prompts:

```
/prompt-config set github.com/agenticsorg/summarizer-bot-rules
/prompt-config status
/prompt-config test discussion
/prompt-config refresh
```

## 📋 Prompt Guidelines

### Best Practices

1. **Be Specific**: Tailor prompts to your community's style
2. **Use Structure**: Clear sections help the AI generate consistent summaries
3. **Include Examples**: Show the format you want
4. **Test Changes**: Use `/prompt-config test` before committing

### File Requirements

- **Format**: Markdown (.md files)
- **Encoding**: UTF-8
- **Max Size**: 50 KB per file
- **Min Size**: 50 characters

## 🚀 Getting Started

1. Fork this repository (or use it directly)
2. Customize the prompt templates
3. Configure the bot: `/prompt-config set github.com/agenticsorg/summarizer-bot-rules`
4. Test it: `/summarize` in any channel
5. Iterate based on results

## 📚 Resources

- [Full Documentation](https://github.com/mrjcleaver/summarybot-ng/tree/main/docs)
- [Template Guide](https://github.com/mrjcleaver/summarybot-ng/blob/main/docs/external-prompts-template-repo.md)
- [User Guide](https://github.com/mrjcleaver/summarybot-ng/blob/main/docs/external-prompts-user-guide.md)

## 🤝 Contributing

Feel free to suggest improvements via issues or pull requests!

## 📜 License

MIT License - Feel free to use and modify these prompts for your own Discord server.

---

**Maintained by**: Agentics Foundation
**Bot Repository**: https://github.com/mrjcleaver/summarybot-ng
