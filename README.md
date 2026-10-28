# Architectury Mod Project Skill

A Codex skill for preparing, documenting, implementing, and validating Minecraft mods created with the [Architectury Template Generator](https://generate.architectury.dev/).

The skill tells an AI coding agent how to inspect the generated repository before writing code, preserve older projects, write a complete project specification, keep shared and loader-specific code in the correct modules, configure the required JDK/SDK, apply the MIT License, and verify every enabled loader.

## What problem this solves

Minecraft and loader APIs change between versions. Code copied from another project may use the wrong mappings, registry APIs, metadata, Java version, or client/server lifecycle. This skill makes the current project's Gradle configuration and resolved dependencies the source of truth and requires evidence-based compilation and runtime validation.

It also makes the project understandable to people who were not part of the original conversation. The generated mod README must clearly explain:

- what the mod is and what it changes;
- which Minecraft version and loaders it supports;
- how its gameplay works, including important values and exceptions;
- how shared and platform-specific code should be organized;
- which resources and metadata are required;
- how to build, install, use, test, and package it;
- what has actually been verified and what remains unverified.

## Included source guidance

All four maintained source documents are included under `references/`:

- `AGENTS.md`
- `OLD-AGENTS.md`
- `Architectury-instr.md`
- `howtowriteREADME.md`

The first two become project-level coding instructions for a new generated mod. The other two define how its README and implementation specification should be written. The skill requires the agent to read all four before modifying a target project.

## Install

Clone or download this repository, then place the `architectury-mod-project` folder in your Codex skills directory:

```text
~/.codex/skills/architectury-mod-project/
```

The folder must contain `SKILL.md` at its root. Restart or reload Codex if the skill is not discovered immediately.

## Use

Invoke it explicitly:

```text
$architectury-mod-project
```

Example request:

```text
Use $architectury-mod-project for /path/to/my-generated-mod. Prepare the project
for a Fabric and NeoForge mod that adds ..., write the complete README first,
then implement and verify it.
```

The skill can also be selected automatically for a clearly matching Architectury mod task.

## Expected workflow

1. Inspect the target repository and determine its real Minecraft, loader, mapping, Gradle, Java, Architectury, mod ID, and module configuration.
2. Read all four bundled guidance files.
3. Copy the two project rule files into a new mod without changing older mod folders.
4. Write a README that explains the mod's purpose, behavior, implementation, assets, SDK, build, installation, validation, and current status.
5. Add and synchronize the MIT license across the root license file, README, loader metadata, and packaged artifacts.
6. Implement shared logic in `common` and loader-specific integration in the matching modules.
7. Configure the correct SDK and verify every enabled loader, relevant runtime behavior, resources, and release JAR.
8. Report verified results and limitations without treating compilation as gameplay proof.

## Scope

This skill does not supply a Minecraft or Architectury project template. Generate the project at [generate.architectury.dev](https://generate.architectury.dev/) first, then use the skill on that repository.

It does not guarantee compatibility across arbitrary Minecraft or loader versions. The skill requires each project to verify its own APIs and dependencies.

## License

This skill is released under the [MIT License](LICENSE).
