# Guanchen Agent Plugins

This repo conforms to [Agent Plugins Specification 1.0](https://agent-plugins.org/specification) for plugins, and the [Copilot marketplace](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/plugins-marketplace#creating-a-plugin-marketplace) setup. 

## Setup

Following setup uses the Copilot CLI. Will install under `%USERPROFILE%/.copilot/installed-plugins`.

Can also be done via VS Code UI (slightly different results), will then install under `%USERPROFILE%/.vscode/agent-plugins`. Go to `Extensions` - `Agent Plugins - Installed` to configure.

Both ways make the plugins end up under `Extensions` - `Agent Plugins - Installed`.

```bash
# Get the current marketplaces
copilot plugin marketplace list

# Add the current repo as marketplace
copilot plugin marketplace add erwinkramer/agent-plugins

# Install some plugins, from the Guanchen Agent Plugins marketplace
copilot plugin install guanchen-platform@guanchen-plugins
copilot plugin install guanchen-bank-api@guanchen-plugins
copilot plugin install ponytail@guanchen-plugins
```

Now, use the `Reload Windows` command in VS Code to see the freshly installed plugins.

## Issues

1. For all update/delete commands for plugins installed via `copilot` cli, VS Code has to be closed, because of [os error 5 (permission) issue in the cli](https://github.com/github/copilot-cli/issues/4570). Not an issue when using VS Code UI for installing and managing plugins.
1. Variables for local MCP Servers and local hooks do not work in VS Code chat session, see https://github.com/microsoft/vscode/issues/336882
1. Ponytail does not have a compliant Agent Plugin spec, which only causes an issue with the ponytail-hooks not pointing to `copilot-hooks.json` - but to the claude variant instead. Skills work fine. As a workaround, a personal fork is used here, and a PR has been filed: https://github.com/DietrichGebert/ponytail/pull/911

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
