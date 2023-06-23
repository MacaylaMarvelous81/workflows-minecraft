# workflows-minecraft
A set of reusable workflows for any Minecraft development (at this time, Java Edition mods)

## Workflows
- [Java Edition](#java-edition)
    - [fabricmc-publish](#fabricmc-publish)
	- [java-build](#java-build)

## Java Edition
These are workflows suitable for Java Edition development.

### [fabricmc-publish](/.github/workflows/fabricmc-publish.yml)
Publishes a FabricMC mod to GitHub Releases and Modrinth. Intended for use when pushing a tag. It calls
[java-build](#java-build) to build the mod.  
TBA: CurseForge publish, more customization via inputs

#### Inputs
| Input       | Type   | Description                                        | Required   |
|-------------|--------|----------------------------------------------------|------------|
| mod-name    | string | The name of the mod as it will appear in releases. | Yes        |
| modrinth-id | string | The mod id in Modrinth.                            | No         |

#### Secrets
| Secret         | Description                                                              | Required |
|----------------|--------------------------------------------------------------------------|----------|
| MODRINTH_TOKEN | Authorization token used to authenticate with Modrinth and publish mods. | No       |

### [java-build](/.github/workflows/java-build.yml)
Builds a mod.

#### Inputs
| Input | Type   | Description                                                  | Required |
|-------|--------|--------------------------------------------------------------|----------|
| ref   | string | The ref to build. Will use the latest commit if unspecified. | No       |

#### Secrets
This workflow does not use any secrets.
