# Guanchen Agent Plugins

This repo conforms to [Agent Plugins Specification 1.0](https://agent-plugins.org/specification) for plugins, and the [Copilot marketplace](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/plugins-marketplace#creating-a-plugin-marketplace) setup. 

## Setup

Following setup uses the Copilot CLI. Will install under `%USERPROFILE%/.copilot/installed-plugins`.

Can also be done via VS Code UI (slightly different results), will then install under `%USERPROFILE%/.vscode/agent-plugins`. Go to `Extensions` - `Agent Plugins - Installed` to configure.

Both ways make the plugins end up under `Extensions` - `Agent Plugins - Installed`.

```bash
# Get the current marketplaces
copilot plugin marketplace list

# Add some marketplaces for popular skills
copilot plugin marketplace add mattpocock/skills
copilot plugin marketplace add dietrichgebert/ponytail

# Add the current repo as marketplace
copilot plugin marketplace add erwinkramer/agent-plugins

# Install some popular skills, via the added marketplaces
copilot plugin install mattpocock-skills@mattpocock
copilot plugin install ponytail@ponytail

# Install some skills, from the Guanchen Agent Plugins marketplace
copilot plugin install guanchen-platform@guanchen-plugins
copilot plugin install guanchen-bank-api@guanchen-plugins
```

Now, use the `Reload Windows` command in VS Code to see the freshly installed plugins.

For all following commands, VS Code has to be closed, because of [os error 5 (permission) issue in the cli](https://github.com/github/copilot-cli/issues/4570). Not an issue when using VS Code UI for installing and managing plugins.

## Maintenance

Auto update for plugins is enabled by default, but if you want to trigger manually:

```bash
# Update all installed plugins
copilot plugin update --all
```

## Teardown

```bash
# Remove a plugin
copilot plugin remove guanchen-bank-api@guanchen-plugins

# Remove a marketplace and all its plugins 
copilot plugin marketplace remove guanchen-plugins --force
```
