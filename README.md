# Minecraft 1.21.11 Fabric Mod Snippets

A VS Code snippets extension for Fabric 1.21.11 modding. All snippets are declarative JSON and grouped by language in the snippets/ folder.

## What you get

- Registries, items, blocks, entities, screens, networking, worldgen, tools (Java) in [snippets/java](snippets/java)
- Data generation helpers: entrypoint, model, loot, recipe providers in [snippets/java/fabric.json](snippets/java/fabric.json)
- Command scaffolding (arguments, permissions, feedback) in [snippets/java/command.register.json](snippets/java/command.register.json)
- Fabric metadata and tags: fabric.mod.json blocks and tags templates in [snippets/json](snippets/json)
- Gradle and properties blocks for Fabric projects in [snippets/json/gradle.json](snippets/json/gradle.json)

## Install

1. Clone the repo or download the VSIX you build locally.
2. In VS Code, run Extensions: Install from VSIX... and pick the packaged file, or open the folder and press F5 to launch the extension host.
3. Ensure the workspace language mode matches the snippet file you want (Java or JSON).

## Using snippets

- Trigger snippets by prefix (dotted, lowercase), e.g. reg.item, block.ore, datagen.entry, command.register, fabricmod.base, tag.block.
- Tab through placeholders; optional parts are left as comments in snippet bodies.
- Snippets target Fabric API for Minecraft 1.21.11 and Java 21.

## Contributing

- Add new JSON snippet files under snippets/java or snippets/json.
- Register every snippet file in the contributes.snippets array in [package.json](package.json).
- Keep prefixes dotted/lowercase and descriptions short; maintain indentation and placeholder numbering.
- Bump the version in [package.json](package.json) and add notes to [CHANGELOG.md](CHANGELOG.md).

## License

MIT. See [LICENSE](LICENSE).
