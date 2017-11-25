# Comparison of Discord.js Frameworks

## General Comparison

General details about the frameworks, such as versions.  
This section is for stable releases only.  

Discord.js versions are noted in semver where applicable.  
Node.js versions are the minimum versions required.  
Dependencies do not include Discord.js, TypeScript, or optional/peer dependencies.  

| **General** | [**Akairo**](https://www.npmjs.com/package/discord-akairo) | [**Commando**](https://www.npmjs.com/package/discord.js-commando) | [**Handles**](https://www.npmjs.com/package/discord-handles) | [**Klasa**](https://www.npmjs.com/package/klasa) | [**Komada**](https://www.npmjs.com/package/komada) | [**YAMDBF**](https://www.npmjs.com/package/yamdbf)
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Library version | 7.5.1 | 0.9.0 | 7.3.5 | 0.3.0 | 0.21.1 | 3.0.1 |
| Discord.js version | `^11.2.1` | `^11.2.1` | `^11.1.0` | Master branch | Master branch | Custom 11.1 |
| Node.js version | 6.0.0 | 7.0.0 | 6.0.0 | 8.1.0 | 8.5.0 | 8.0.0 |
| Typings | ✓ | ✓ | ✓ †1 | ✓ | ✘ | ✓ †1 |
| Dependencies | 0 | 3 | 1 | 6 | 4 | 5 |

†1: Handles and YAMDBF are written in TypeScript.  

## Command Parsing

Command parsing is how frameworks parse messages into commands.  
This includes prefixes, aliases, etc.  

| **Command Parsing** | [**Akairo**](https://www.npmjs.com/package/discord-akairo) | [**Commando**](https://www.npmjs.com/package/discord.js-commando) | [**Handles**](https://www.npmjs.com/package/discord-handles) | [**Klasa**](https://www.npmjs.com/package/klasa) | [**Komada**](https://www.npmjs.com/package/komada) | [**YAMDBF**](https://www.npmjs.com/package/yamdbf) |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Command aliases | ✓ | ✓ | ? | ? | ? | ? |
| Mention as prefix | ✓ | ✓ | ? | ? | ? | ? |
| Multiple prefixes | ✓ | ✘ | ? | ? | ? | ? |
| Per-guild prefix customisation | ✓ | ✓ | ? | ? | ? | ? |
| Regular expression trigger | ✓ | ✓ | ? | ? | ? | ? |
| Stores prefix and alias used | ✓ | ✓ | ? | ? | ? | ? |

## Command Handling

Command handling refers to the behavior of command execution and restrictions.  
It also includes the monitoring of and the inhibition of messages and commands.  

Subcommands are commands that are individual commands with the same base name.  
Argument parsing within one command does not count towards that criteria.  

| **Command Handling** | [**Akairo**](https://www.npmjs.com/package/discord-akairo) | [**Commando**](https://www.npmjs.com/package/discord.js-commando) | [**Handles**](https://www.npmjs.com/package/discord-handles) | [**Klasa**](https://www.npmjs.com/package/klasa) | [**Komada**](https://www.npmjs.com/package/komada) | [**YAMDBF**](https://www.npmjs.com/package/yamdbf) |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Cooldowns | ✓ | ✓ | ? | ? | ? | ? |
| Monitoring messages | ✓ | ✓ | ? | ? | ? | ? |
| Blocking messages | ✓ | ✓ | ? | ? | ? | ? |
| Channel restrictions | ✓ | ✓ | ? | ? | ? | ? |
| Permissions restrictions | ✓ | ✓ | ? | ? | ? | ? |
| Command edits | ✓ | ✓ | ? | ? | ? | ? |
| Subcommands | ✘ | ✘ | ? | ? | ? | ? |
| Run from code | ✓ | ✓ | ? | ? | ? | ? |
| Help information | ✓ | ✓ | ? | ? | ? | ? |

## Argument Parsing

Arguments are the data acquired and parsed from user input.  
This section compares how frameworks can match and parse input.  
Custom parsing or types do not count for other specific criterias, even if they are replicable.  

Less obvious criterias:
- Dependent arguments are arguments whose behavior depends on previous arguments.
- User/member/role/channel matching means to be able to find an item based on approximations to their name, their ID, etc.

| **Argument Parsing** | [**Akairo**](https://www.npmjs.com/package/discord-akairo) | [**Commando**](https://www.npmjs.com/package/discord.js-commando) | [**Handles**](https://www.npmjs.com/package/discord-handles) | [**Klasa**](https://www.npmjs.com/package/klasa) | [**Komada**](https://www.npmjs.com/package/komada) | [**YAMDBF**](https://www.npmjs.com/package/yamdbf) |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Ordered arguments | ✓ | ✓ | ? | ? | ? | ? |
| Unordered arguments | ✘ ⇒ ✓ | ✘ | ? | ? | ? | ? |
| Optional arguments | ✓ | ✓ | ? | ? | ? | ? |
| Quoted arguments | ✓ | ✓ | ? | ? | ? | ? |
| Flag arguments | ✓ | ✘ | ? | ? | ? | ? |
| Rest arguments | ✓ | ✓ | ? | ? | ? | ? |
| Dependent arguments | ✓ | ✘ | ? | ? | ? | ? |
| Argument types | ✓ | ✓ | ? | ? | ? | ? |
| Union types | ✘ ⇒ ✓ | ✘ | ? | ? | ? | ? |
| Custom types | ✓ | ✓ | ? | ? | ? | ? |
| User and member matching | ✓ | ✓ | ? | ? | ? | ? |
| Role matching | ✓ | ✓ | ? | ? | ? | ? |
| Channel matching | ✓ | ✓ | ? | ? | ? | ? |
| Custom argument parsing | ✓ | ✓ | ? | ? | ? | ? |

## Prompting

Prompting is the ability to collect messages from the user without invoking a command directly.  
Custom prompts do not count for other specific criterias, even if they are replicable.  

| **Prompting** | [**Akairo**](https://www.npmjs.com/package/discord-akairo) | [**Commando**](https://www.npmjs.com/package/discord.js-commando) | [**Handles**](https://www.npmjs.com/package/discord-handles) | [**Klasa**](https://www.npmjs.com/package/klasa) | [**Komada**](https://www.npmjs.com/package/komada) | [**YAMDBF**](https://www.npmjs.com/package/yamdbf) |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| From argument parsing | ✓ | ✓ | ? | ? | ? | ? |
| Prompt from code | ✓ | ✓ | ? | ? | ? | ? |
| Prompt time limit | ✓ | ✓ | ? | ? | ? | ? |
| Prompt retry limit | ✓ | ✓ | ? | ? | ? | ? |
| Prompt cancellation | ✓ | ✓ | ? | ? | ? | ? |
| Infinite prompts | ✓ | ✓ | ? | ? | ? | ? |
| Custom prompt system | ✘ | ✘ | ? | ? | ? | ? |
| Custom prompt messages | ✓ | ※1 | ? | ? | ? | ? |
| Stores prompts and replies | ※2 ⇒ ✓ | ※3 ⇒ ✓ | ? | ? | ? | ? |

※1: Commando appends built-in text to prompt messages.  
※2: Akairo stores only the last editable response.  
※3: Commando stores only the responses.  

## Module System

The module system of a framework is how the framework structures its modules.  
This includes how new modules (e.g. commands) are created and loaded.  

| **Module System** | [**Akairo**](https://www.npmjs.com/package/discord-akairo) | [**Commando**](https://www.npmjs.com/package/discord.js-commando) | [**Handles**](https://www.npmjs.com/package/discord-handles) | [**Klasa**](https://www.npmjs.com/package/klasa) | [**Komada**](https://www.npmjs.com/package/komada) | [**YAMDBF**](https://www.npmjs.com/package/yamdbf) |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Classes | ✓ | ✓ | ? | ? | ? | ? |
| Class instances | ✓ | ✘ | ? | ? | ? | ? |
| Specific exports | ✘ | ✘ | ? | ? | ? | ? |
| ES module support | ✘ | ✘ | ? | ? | ? | ? |
| TypeScript module support | ✓ | ✓ | ? | ? | ? | ? |
| Recursive loading | ✓ | ✓ | ? | ? | ? | ? |
| Loading and unloading | ✓ | ✓ | ? | ? | ? | ? |
| Reloading modules | ✓ | ✓ | ? | ? | ? | ? |
| Module categories | ✓ | ✓ | ? | ? | ? | ? |
| Custom module types | ✓ | ✘ | ? | ? | ? | ? |
| Plugins support | ✘ | ✘ | ? | ? | ? | ? |

## Databases

This section compares support for databases (usually for an npm library).  
It also compares settings that can be changed for Discord.  
Custom settings do not count for other specific settings, even if they are replicable.  

Sequelize support does not count as SQLite, MySQL, MSSQL, or PostgreSQL support.  

| **Databases** | [**Akairo**](https://www.npmjs.com/package/discord-akairo) | [**Commando**](https://www.npmjs.com/package/discord.js-commando) | [**Handles**](https://www.npmjs.com/package/discord-handles) | [**Klasa**](https://www.npmjs.com/package/klasa) | [**Komada**](https://www.npmjs.com/package/komada) | [**YAMDBF**](https://www.npmjs.com/package/yamdbf) |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| SQLite | ✓ | ✓ | ? | ? | ? | ? |
| MySQL | ✘ | ✘ | ? | ? | ? | ? |
| MSSQL | ✘ | ✘ | ? | ? | ? | ? |
| PostgreSQL | ✘ | ✘ | ? | ? | ? | ? |
| Sequelize | ✓ | ✘ | ? | ? | ? | ? |
| MongoDB | ✘ | ✘ | ? | ? | ? | ? |
| RethinkDB | ✘ | ✘ | ? | ? | ? | ? |
| Custom providers | ✓ | ✓ | ? | ? | ? | ? |
| Disabled commands | ✘ | ✓ | ? | ? | ? | ? |
| Blacklist | ✘ | ✘ | ? | ? | ? | ? |
| Prefixes | ✘ | ✓ | ? | ? | ? | ? |
| Localization | ✘ | ✘ | ? | ? | ? | ? |
| Custom settings | ✓ | ✓ | ? | ? | ? | ? |

## Events

Events that are useful for a framework are compared here.  

| **Events** | [**Akairo**](https://www.npmjs.com/package/discord-akairo) | [**Commando**](https://www.npmjs.com/package/discord.js-commando) | [**Handles**](https://www.npmjs.com/package/discord-handles) | [**Klasa**](https://www.npmjs.com/package/klasa) | [**Komada**](https://www.npmjs.com/package/komada) | [**YAMDBF**](https://www.npmjs.com/package/yamdbf) |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Modular event listeners | ✓ | ✘ | ? | ? | ? | ? |
| On invalid commands | ✓ | ✓ | ? | ? | ? | ? |
| On command blocked | ✓ | ✓ | ? | ? | ? | ? |
| On command start | ✓ | ✓ | ? | ? | ? | ? |
| On command end | ✓ | ✘ | ? | ? | ? | ? |
| On command error | ✓ | ✓ | ? | ? | ? | ? |
| On database changes | ✘ | ✘ | ? | ? | ? | ? |
| On module changes | ✓ | ✓ | ? | ? | ? | ? |

## Promise Support

Support for Promises, either as return values from the user or as implementations internally.  

| **Promise Support** | [**Akairo**](https://www.npmjs.com/package/discord-akairo) | [**Commando**](https://www.npmjs.com/package/discord.js-commando) | [**Handles**](https://www.npmjs.com/package/discord-handles) | [**Klasa**](https://www.npmjs.com/package/klasa) | [**Komada**](https://www.npmjs.com/package/komada) | [**YAMDBF**](https://www.npmjs.com/package/yamdbf) |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Promises used internally | ✓ | ✓ | ? | ? | ? | ? |
| Message monitoring | ✓ | ✘ | ? | ? | ? | ? |
| Argument parsing | ✓ | ✓ | ? | ? | ? | ? |
| Command restrictions | ✘ ⇒ ✓ | ✘ | ? | ? | ? | ? |
| Command execution | ✓ | ✓ | ? | ? | ? | ? |

## Settings

The settings of the framework are options that changes the behavior.  
They are used to opt-in or opt-out of built-in features.  

| **Settings** | [**Akairo**](https://www.npmjs.com/package/discord-akairo) | [**Commando**](https://www.npmjs.com/package/discord.js-commando) | [**Handles**](https://www.npmjs.com/package/discord-handles) | [**Klasa**](https://www.npmjs.com/package/klasa) | [**Komada**](https://www.npmjs.com/package/komada) | [**YAMDBF**](https://www.npmjs.com/package/yamdbf) |
| --- | :-: | :-: | :-: | :-: | :-: | :-: |
| Built-in commands | ✘ | ✓ | ? | ? | ? | ? |
| Modify built-in commands | ∅ | ✓ | ? | ? | ? | ? |
| Built-in responses | ✓ ⇒ ✘ | ✓ | ? | ? | ? | ? |
| Modify built-in responses | ✓ ⇒ ∅ | ✘ | ? | ? | ? | ? |
| Selfbot mode | ✓ | ✓ | ? | ? | ? | ? |
| Bot owner | ✓ | ✓ | ? | ? | ? | ? |
| Multiple owners | ✓ | ✓ | ? | ? | ? | ? |
| Module directories | ✓ | ✓ | ? | ? | ? | ? |

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

## Biases

There are currently a lots of biases to Akairo at this moment.  
Developers of other frameworks, please help reduce bias!  
(Remove this section once everyone is mostly happy)  
