# Comparison of Discord.js Frameworks

## General Comparison

General details about the frameworks, such as versions.  
This section is for stable releases only.  

Discord.js versions are noted in semver where applicable.  
Node.js versions are the minimum versions required.  
Dependencies do not include Discord.js, TypeScript, or optional/peer dependencies.  

| **General** | [**Akairo**][akairo] | [**Commando**][commando] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: |
| Library version | 7.5.5 | 0.10.0 | 3.0.1 |
| Discord.js version | `^11.4.0` | `^11.2.1` | Custom 11.1 |
| Node.js version | 6.0.0 | 7.0.0 | 8.0.0 |
| Typings | ✓ | ✓ | ✓ †1 |
| Dependencies | 0 | 3 | 5 |
| Documentation | [Akairo](https://1computer1.github.io/discord-akairo/) | [Commando](https://discord.js.org/#/docs/commando/master/general/welcome) | [YAMDBF](https://yamdbf.js.org/) |
| VSCode Extension | ✘ | ? | ✘ |

†1: YAMDBF is written in TypeScript.

## Command Parsing

Command parsing is how frameworks parse messages into commands.  
This includes prefixes, aliases, etc.  

| **Command Parsing** | [**Akairo**][akairo] | [**Commando**][commando] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: |
| Command aliases | ✓ | ✓ | ✓ |
| Mention as prefix | ✓ | ✓ | ✓ |
| Multiple prefixes | ✓ | ✘ | ✘ |
| Per-guild prefix customisation | ✓ | ✓ | ✓ |
| Regular expression trigger | ✓ | ✓ | ✘ |
| Stores original input | ✓ | ✓ | ✘ |

## Command Handling

Command handling refers to the behavior of command execution and restrictions.  
It also includes the monitoring of and the inhibition of messages and commands.  

Subcommands are commands that are individual commands with the same base name.  
Argument parsing within one command does not count towards that criteria.  

| **Command Handling** | [**Akairo**][akairo] | [**Commando**][commando] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: |
| Cooldowns | ✓ | ✓ | ✓ |
| Monitoring messages | ✓ | ✓ | ? |
| Blocking messages | ✓ | ✓ | ? |
| Channel restrictions | ✓ | ✓ | ✓ |
| Permissions restrictions | ✓ | ✓ | ✓ |
| Command edits | ✓ | ✓ | ? |
| Subcommands | ✘ | ✘ | ? |
| Run from code | ✓ | ✓ | ✓ |
| Typing mode | ✓ | ? | ? |
| Help information | ✓ | ✓ | ✓ |

## Argument Parsing

Arguments are the data acquired and parsed from user input.  
This section compares how frameworks can match and parse input.  
Custom parsing or types do not count for other specific criterias, even if they are replicable.  

Less obvious criterias:
- Dependent arguments are arguments whose behavior depends on previous arguments.
- User/member/role/channel matching means to be able to find an item based on approximations to their name, their ID, etc.

| **Argument Parsing** | [**Akairo**][akairo] | [**Commando**][commando] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: |
| Ordered arguments | ✓ | ✓ | ✓ |
| Unordered arguments | ✘ ⇒ ✓ | ✘ | ? |
| Optional arguments | ✓ | ✓ | ✓ |
| Quoted arguments | ✓ | ✓ | ? |
| Flag arguments | ✓ | ✘ | ? |
| Rest arguments | ✓ | ✓ | ✓ |
| Dependent arguments | ✓ | ✘ | ? |
| Argument types | ✓ | ✓ | ✓ |
| Union types | ✘ ⇒ ✓ | ✓ | ? |
| Custom types | ✓ | ✓ | ✓ |
| User and member matching | ✓ | ✓ | ✓ |
| Role matching | ✓ | ✓ | ✓ |
| Channel matching | ✓ | ✓ | ✓ |
| Regular expression arguments | ✓ | ? | ? |
| Custom arguments | ✓ | ✓ | ✓ |

## Prompting

Prompting is the ability to collect messages from the user without invoking a command directly.  
Custom prompts do not count for other specific criterias, even if they are replicable.  

| **Prompting** | [**Akairo**][akairo] | [**Commando**][commando] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: |
| From argument parsing | ✓ | ✓ | ? |
| Prompt from code | ✓ | ✓ | ? |
| Prompt time limit | ✓ | ✓ | ? |
| Prompt retry limit | ✓ | ✓ | ? |
| Prompt cancellation | ✓ | ✓ | ? |
| Infinite prompts | ✓ | ✓ | ? |
| Custom text prompt system | ✘ | ✘ | ? |
| Custom prompt messages | ✓ | ※1 | ? |
| Stores prompts and replies | ※2 ⇒ ✓ | ※3 ⇒ ✓ | ? |
| Reaction prompt system | ✘ | ? | ? |

※1: Commando appends built-in text to prompt messages.  
※2: Akairo stores only the last editable response.  
※3: Commando stores only the responses.  

## Module System

The module system of a framework is how the framework structures its modules.  
This includes how new modules (e.g. commands) are created and loaded.  

| **Module System** | [**Akairo**][akairo] | [**Commando**][commando] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: |
| Classes | ✓ | ✓ | ✓ |
| Specific exports | ✘ | ✘ | ✘ |
| ES module support | ✘ | ✘ | ✘ |
| TypeScript module support | ✓ | ✓ | ✓ |
| Recursive loading | ✓ | ✓ | ? |
| Loading and unloading | ✓ | ✓ | ? |
| Reloading modules | ✓ | ✓ | ? |
| Module categories | ✓ | ✓ | ✓ |
| Custom module types | ✓ | ✘ | ? |
| Plugins support | ✘ | ✘ | ✓ |

## Databases

This section compares support for databases (usually for an npm library).  
It also compares settings that can be changed for Discord.  
Custom settings do not count for other specific settings, even if they are replicable.  

Sequelize support does not count as SQLite, MySQL, MSSQL, or PostgreSQL support.

| **Databases** | [**Akairo**][akairo] | [**Commando**][commando] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: |
| FireStore | ? | ? | ? |
| Level | ? | ? | ? |
| MongoDB | ✘ | ✘ | ? |
| MSSQL | ✘ | ✘ | ✓ |
| MySQL | ✘ | ✘ | ✓ |
| NeDB | ✘ | ? | ? |
| Neo4J | ? | ? | ? |
| PostgreSQL | ✘ | ✘ | ✓ |
| RethinkDB | ✘ | ✘ | ? |
| Sequelize | ✓ | ✘ | ✓ |
| SQLite | ✓ | ✓ | ✓ |
| Custom providers | ✓ | ✓ | ✓ |
| Disabled commands | ✘ | ✓ | ✓ |
| Blacklist | ✘ | ✘ | ✓ |
| Prefixes | ✘ | ✓ | ✓ |
| Localization | ✘ | ✘ | ✓ |
| Custom settings | ✓ | ✓ | ✓ | 

## Events

Events that are useful for a framework are compared here.

| **Events** | [**Akairo**][akairo] | [**Commando**][commando] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: |
| Modular event listeners | ✓ | ✘ | ? |
| Reloadable event structures | ✓ | ? | ? |
| On invalid commands | ✓ | ✓ | ? |
| On command blocked | ✓ | ✓ | ? |
| On command start | ✓ | ✓ | ? |
| On command end | ✓ | ✘ | ? |
| On command error | ✓ | ✓ | ? |
| On database changes | ✘ | ✘ | ? |
| On module changes | ✓ | ✓ | ? |
| Custom events | ✓ | ? | ✓ |

## Promise Support

Support for Promises, either as return values from the user or as implementations internally.

| **Promise Support** | [**Akairo**][akairo] | [**Commando**][commando] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: |
| Promises used internally | ✓ | ✓ | ✓ |
| Message monitoring | ✓ | ✘ | ? |
| Argument parsing | ✓ | ✓ | ✓ |
| Command restrictions | ✘ ⇒ ✓ | ✘ | ✓ |
| Command execution | ✓ | ✓ | ✓ |

## Settings

The settings of the framework are options that changes the behavior.  
They are used to opt-in or opt-out of built-in features.  

Built-in features marked as `✓` means they exist and are modifiable, `✘` means they exist and are not modifiable, and `∅` means they do not exist.

| **Settings** | [**Akairo**][akairo] | [**Commando**][commando] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: |
| Modifiable built-in commands | ∅ | ✘ | ✓ |
| Modifiable built-in event handlers | ∅ | ? | ? |
| Modifiable built-in inhibitors | ✘ | ? | ? |
| Modifiable built-in command handler | ✓ | ? | ? |
| Modifiable built-in responses | ✓ ⇒ ∅ | ✘ | ✓ |
| Modifiable built-in locales | ∅ | ∅ | ✓ |
| Bot owner | ✓ | ✓ | ✓ |
| Multiple owners | ✓ | ✓ | ✓ |
| Module directories | ✓ | ✓ | ✓ |

## Legend

| Symbol | Description |
| :-: | --- |
| ✓ | Has the feature |
| ✘ | Does not have the feature |
| ※ | Partially has the feature (details noted at the bottom) |
| † | More information noted at the bottom |
| ⇒ | Different status in a development version (in a public repository) |
| ? | Unknown status of feature (contribute if you know) |
| ∅ | Not applicable |

For example, `✓` means that the feature is available in both the stable release and the development version.  
Likewise, `✘ ⇒ ✓` means that the feature is not available in the stable release, but it is available in the development version.  

Library versions are for the stable release of the framework.  
Discord.js versions follows semver while Node.js versions is the minimum release.  

Notes will refer to the stable version unless explicitly referred to as development version.

## Contributing

If you see inaccurate information, please open an issue or create a pull request to fix it.  
Any issue or pull request that wish to change or add information should have substantial proof.  

If the status between the stable release and development version is unknown, assume they are the same (e.g. `✘` instead of `✘ ⇒ .`).  
Features that are partially available as well as notes should be numbered (e.g. `※1` or `✓ †1`) and noted below.  
Notes should refer to the stable version unless explicitly referred to as development version.  

Opt-in features should be labelled as `✓`, do not make a note that they are opt-in.  
Official plugins are to be labelled with a `✓`, along with a note as to where to find them.  

[akairo]: https://www.npmjs.com/package/discord-akairo
[commando]: https://www.npmjs.com/package/discord.js-commando
[yamdbf]: https://www.npmjs.com/package/yamdbf
