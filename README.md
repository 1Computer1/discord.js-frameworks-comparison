# Comparison of Discord.js Frameworks

## General Comparison

General details about the frameworks, such as versions.  
This section is for stable releases only.  

Discord.js versions are noted in semver where applicable.  
Node.js versions are the minimum versions required.  
Dependencies do not include Discord.js, TypeScript, or optional/peer dependencies.  

| **General** | [**Akairo**][akairo] | [**Commando**][commando] | [**Handles**][handles] | [**Klasa**][klasa] | [**Komada**][komada] | [**YAMDBF**][yamdbf]
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Library version | 7.5.1 | 0.10.0 | 7.3.5 | 0.4.0 | 0.21.1 | 3.0.1 |
| Discord.js version | `^11.2.1` | `^11.2.1` | `^11.1.0` | Master branch | Master branch | Custom 11.1 |
| Node.js version | 6.0.0 | 7.0.0 | 6.0.0 | 8.5.0 | 8.5.0 | 8.0.0 |
| Typings | ✓ | ✓ | ✓ †1 | ✓ | ✘ | ✓ †1 |
| Dependencies | 0 | 3 | 1 | 2 | 4 | 5 |
| Documentation | [Akairo](https://1computer1.github.io/discord-akairo/) | [Commando](https://discord.js.org/#/docs/commando/master/general/welcome) | [Handles](http://handles.topkek.pw/) | [Klasa](https://klasa.js.org/) | [Komada](https://komada.js.org/) | [YAMDBF](https://yamdbf.js.org/) |
| VSCode Extension | ✘ | ? | ✘ | ✓ | ✓ | ✘ |

†1: Handles and YAMDBF are written in TypeScript.

## Command Parsing

Command parsing is how frameworks parse messages into commands.  
This includes prefixes, aliases, etc.  

| **Command Parsing** | [**Akairo**][akairo] | [**Commando**][commando] | [**Handles**][handles] | [**Klasa**][klasa] | [**Komada**][komada] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Command aliases | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Mention as prefix | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Multiple prefixes | ✓ | ✘ | ※1 | ✓ | ✓ | ✘ |
| Per-guild prefix customisation | ✓ | ✓ | ※1 | ✓ | ✓ | ✓ |
| Regular expression trigger | ✓ | ✓ | ✓ | ✓ | ✓ | ✘ |
| Stores original input | ✓ | ✓ | ✓ | ✓ | ✓ | ✘ |

※1: Custom implementations only; see databases section.

## Command Handling

Command handling refers to the behavior of command execution and restrictions.  
It also includes the monitoring of and the inhibition of messages and commands.  

Subcommands are commands that are individual commands with the same base name.  
Argument parsing within one command does not count towards that criteria.  

| **Command Handling** | [**Akairo**][akairo] | [**Commando**][commando] | [**Handles**][handles] | [**Klasa**][klasa] | [**Komada**][komada] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Cooldowns | ✓ | ✓ | ※1 | ✓ | ✓ | ✓ |
| Monitoring messages | ✓ | ✓ | ※1 | ✓ | ✓ | ? |
| Blocking messages | ✓ | ✓ | ※1 | ✓ | ✓ | ? |
| Channel restrictions | ✓ | ✓ | ※1 | ✓ | ✓ | ✓ |
| Permissions restrictions | ✓ | ✓ | ※1 | ✓ | ✓ | ✓ |
| Command edits | ✓ | ✓ | ✘ | ✓ | ✓ | ? |
| Subcommands | ✘ | ✘ | ✘ | ✘ ⇒ ✓ | ✘ | ? |
| Run from code | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Typing mode | ✓ | ? | ※1 | ✓ | ✘ | ? |
| Help information | ✓ | ✓ | ✘ | ✓ | ✓ | ✓ |

※1: Custom implementations only; see databases section.

## Argument Parsing

Arguments are the data acquired and parsed from user input.  
This section compares how frameworks can match and parse input.  
Custom parsing or types do not count for other specific criterias, even if they are replicable.  

Less obvious criterias:
- Dependent arguments are arguments whose behavior depends on previous arguments.
- User/member/role/channel matching means to be able to find an item based on approximations to their name, their ID, etc.

| **Argument Parsing** | [**Akairo**][akairo] | [**Commando**][commando] | [**Handles**][handles] | [**Klasa**][klasa] | [**Komada**][komada] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Ordered arguments | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Unordered arguments | ✘ ⇒ ✓ | ✘ | ✘ | ✘ ⇒ ✓ | ✘ | ? |
| Optional arguments | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Quoted arguments | ✓ | ✓ | ✘ | ✓ | ✘ | ? |
| Flag arguments | ✓ | ✘ | ✘ | ✘ ⇒ ✓ | ✘ | ? |
| Rest arguments | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Dependent arguments | ✓ | ✘ | ✓ | ✘ ⇒ ✓ | ✘ | ? |
| Argument types | ✓ | ✓ | ✘ | ✓ | ✓ | ✓ |
| Union types | ✘ ⇒ ✓ | ✓ | ✘ | ✓ | ✓ | ? |
| Custom types | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| User and member matching | ✓ | ✓ | ※3 | ※1 | ※2 | ✓ |
| Role matching | ✓ | ✓ | ※3 | ※1 | ※2 | ✓ |
| Channel matching | ✓ | ✓ | ※3 | ※1 | ※2 | ✓ |
| Regular expression arguments | ✓ | ? | ✓ | ✓ | ✘ | ? |
| Custom arguments | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

※1: Klasa only supports IDs and mentions.  
※2: Komada only supports IDs and mentions.  
※3: Custom implementations only; see databases section.  

## Prompting

Prompting is the ability to collect messages from the user without invoking a command directly.  
Custom prompts do not count for other specific criterias, even if they are replicable.  

| **Prompting** | [**Akairo**][akairo] | [**Commando**][commando] | [**Handles**][handles] | [**Klasa**][klasa] | [**Komada**][komada] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| From argument parsing | ✓ | ✓ | ✓ | ✓ | ✓ | ? |
| Prompt from code | ✓ | ✓ | ✓ | ✘ ⇒ ✓ | ✘ | ? |
| Prompt time limit | ✓ | ✓ | ✓ | ✓ | ※4 | ? |
| Prompt retry limit | ✓ | ✓ | ✘ | ✘ ⇒ ✓ | ✘ | ? |
| Prompt cancellation | ✓ | ✓ | ✓ | ✓ | ✓ | ? |
| Infinite prompts | ✓ | ✓ | ✓ | ✓ | ✓ | ? |
| Custom text prompt system | ✘ | ✘ | ✓ | ✘ ⇒ ✓ | ✘ | ? |
| Custom prompt messages | ✓ | ※1 | ✓ | ✓ | ✘ | ? |
| Stores prompts and replies | ※2 ⇒ ✓ | ※3 ⇒ ✓ | ✘ | ※5 | ※5 | ? |
| Reaction prompt system | ✘ | ? | ✘ | ✓ | ✘ | ? |

※1: Commando appends built-in text to prompt messages.  
※2: Akairo stores only the last editable response.  
※3: Commando stores only the responses.  
※4: Non-configurable time limit of 30 seconds.  
※5: Klasa stores the raw args/parameters resolved.  

## Module System

The module system of a framework is how the framework structures its modules.  
This includes how new modules (e.g. commands) are created and loaded.  

| **Module System** | [**Akairo**][akairo] | [**Commando**][commando] | [**Handles**][handles] | [**Klasa**][klasa] | [**Komada**][komada] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Classes | ✓ | ✓ | ✓ | ✓ | ✘ | ✓ |
| Specific exports | ✘ | ✘ | ✘ => ✓ | ✘ | ✓ | ✘ |
| ES module support | ✘ | ✘ | ✘ | ✘ ⇒ ✓ †1 | ✘ | ✘ |
| TypeScript module support | ✓ | ✓ | ✓ | ✓ | ✘ | ✓ |
| Recursive loading | ✓ | ✓ | ✓ | ✓ | ✓ | ? |
| Loading and unloading | ✓ | ✓ | ✓ | ✓ | ✘ | ? |
| Reloading modules | ✓ | ✓ | ✓ | ✓ | ✓ | ? |
| Module categories | ✓ | ✓ | ✘ | ✓ | ✓ | ✓ |
| Custom module types | ✓ | ✘ | ✘ | ✓ | ✘ | ? |
| Plugins support | ✘ | ✘ | ✘ | ✓ | ✓ | ✓ |

†1: Klasa has experimental support for ESM in the `esm` branch from the repository.

## Databases

This section compares support for databases (usually for an npm library).  
It also compares settings that can be changed for Discord.  
Custom settings do not count for other specific settings, even if they are replicable.  

Sequelize support does not count as SQLite, MySQL, MSSQL, or PostgreSQL support.

| **Databases** | [**Akairo**][akairo] | [**Commando**][commando] | [**Handles**][handles]†3 | [**Klasa**][klasa] | [**Komada**][komada] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| FireStore | ? | ? | ∅ | ✓ †1 | ✘ | ? |
| Level | ? | ? | ∅ | ✓ †1 | ✘ | ? |
| MongoDB | ✘ | ✘ | ∅ | ✓ †1 | ✓ †2 | ? |
| MSSQL | ✘ | ✘ | ∅ | ✓ †1 | ✘ | ✓ |
| MySQL | ✘ | ✘ | ∅ | ✓ †1 | ✓ †2 | ✓ |
| NeDB | ✘ | ? | ∅ | ✓ †1 | ✓ †2 | ? |
| Neo4J | ? | ? | ∅ | ✓ †1 | ✘ | ? |
| PostgreSQL | ✘ | ✘ | ∅ | ✓ †1 | ✘ | ✓ |
| RethinkDB | ✘ | ✘ | ∅ | ✓ †1 | ✓ †2 | ? |
| Sequelize | ✓ | ✘ | ∅ | ✘ | ✘ | ✓ |
| SQLite | ✓ | ✓ | ∅ | ✓ †1 | ✓ †2 | ✓ |
| Custom providers | ✓ | ✓ | ∅ | ✓ | ✓ | ✓ |
| Disabled commands | ✘ | ✓ | ✘ | ✓ | ✓ | ✓ |
| Blacklist | ✘ | ✘ | ✘ | ✘ ⇒ ✓ | ✘ | ✓ |
| Prefixes | ✘ | ✓ | ✘ | ✓ | ✓ | ✓ |
| Localization | ✘ | ✘ | ✘ | ✓ | ✘ | ✓ |
| Custom settings | ✓ | ✓ | ✘ | ✓ | ✓ | ✓ |

†1: Klasa has official plugins for these databases on the [**Klasa Pieces Repo**](https://github.com/dirigeants/klasa-pieces).  
†2: Komada has official plugins for these databases on the [**Komada Pieces Repo**](https://github.com/dirigeants/komada-pieces).  
†3: Database interaction is not packaged with Handles, but all of these are supported with custom integrations.  

## Events

Events that are useful for a framework are compared here.

| **Events** | [**Akairo**][akairo] | [**Commando**][commando] | [**Handles**][handles] | [**Klasa**][klasa] | [**Komada**][komada] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Modular event listeners | ✓ | ✘ | ✘ | ✓ | ✓ | ? |
| Reloadable event structures | ✓ | ? | ✘ | ✓ | ✓ | ? |
| On invalid commands | ✓ | ✓ | ✘ | ✓ | ✘ | ? |
| On command blocked | ✓ | ✓ | ✘ | ✓ | ✘ | ? |
| On command start | ✓ | ✓ | ✓ | ✘ ⇒ ✓ | ✘ | ? |
| On command end | ✓ | ✘ | ✓ | ✓ | ✘ | ? |
| On command error | ✓ | ✓ | ✓ | ✓ | ✘ | ? |
| On database changes | ✘ | ✘ | ✘ | ✓ | ✓ | ? |
| On module changes | ✓ | ✓ | ✘ | ✓ | ✘ | ? |
| Custom events | ✓ | ? | ✓ | ✓ | ✓ | ✓ |

## Promise Support

Support for Promises, either as return values from the user or as implementations internally.

| **Promise Support** | [**Akairo**][akairo] | [**Commando**][commando] | [**Handles**][handles] | [**Klasa**][klasa] | [**Komada**][komada] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Promises used internally | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Message monitoring | ✓ | ✘ | ∅ | ✓ | ✓ | ? |
| Argument parsing | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Command restrictions | ✘ ⇒ ✓ | ✘ | ∅ | ✓ | ✘ | ✓ |
| Command execution | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

## Settings

The settings of the framework are options that changes the behavior.  
They are used to opt-in or opt-out of built-in features.  

Built-in features marked as `✓` means they exist and are modifiable, `✘` means they exist and are not modifiable, and `∅` means they do not exist.

| **Settings** | [**Akairo**][akairo] | [**Commando**][commando] | [**Handles**][handles] | [**Klasa**][klasa] | [**Komada**][komada] | [**YAMDBF**][yamdbf] |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Modifiable built-in commands | ∅ | ✘ | ∅ | ✓ | ✓ | ✓ |
| Modifiable built-in event handlers | ∅ | ? | ✓ | ✓ | ✓ | ? |
| Modifiable built-in inhibitors | ✘ | ? | ∅ | ✓ | ✓ | ? |
| Modifiable built-in command handler | ✓ | ? | ✓ | ✓ | ✓ | ? |
| Modifiable built-in responses | ✓ ⇒ ∅ | ✘ | ✓ | ✓ | ✘ | ✓ |
| Modifiable built-in locales | ∅ | ∅ | ∅ | ✓ | ∅ | ✓ |
| Selfbot mode | ✓ | ✓ | ∅ | ∅ | ✓ | ✓ |
| Bot owner | ✓ | ✓ | ∅ | ✓ | ✓ | ✓ |
| Multiple owners | ✓ | ✓ | ∅ | ✓ | ✓ | ✓ |
| Module directories | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

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
[handles]: https://www.npmjs.com/package/discord-handles
[klasa]: https://www.npmjs.com/package/klasa
[komada]: https://www.npmjs.com/package/komada
[yamdbf]: https://www.npmjs.com/package/yamdbf
