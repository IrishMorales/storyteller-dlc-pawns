<div align="center">
<h1>Contributing to Storyteller and DLC Pawns</h1>
<p>Please read this if you would like to contribute to this project or understand how it works for your own forks.</p>
</div>

First off, thanks for taking the time to contribute! :)

All contributions are welcome! Please make sure to read the relevant section below before making your contribution. It will make it a lot easier for us maintainers and smooth out the experience for all involved. The community looks forward to your contributions.

This project would love help with the following:

- [Reporting Bugs](#reporting-bugs)
- [Requesting New Content](#requesting-new-content)
- [Contributing Code](#contributing-code)
- [Creating Art Assets](#creating-art-assets)
- [Localization](#localization)

> And if you like the project, but just don't have time to contribute, that's fine. There are other easy ways to support the project and show your appreciation, which we would also be very happy about:
>
> - Star the project
> - Tell your friends about it
> - Mention us in any posts/content you make - we like seeing what people do with this mod!

## Reporting bugs

To make sure we can fix your bug, we need to know several details first. Before reporting a bug, please do the following:

- Make sure you're using the latest version
- Check if there's an existing issue for this in the Issues tab above (remove the filters before searching so that closed/old issues will show up too).

If the bug exists on the latest version and hasn't been opened yet, kindly open a GitHub issue with the template below:

<details>
    <summary>Issue template</summary>

Mod version: X.X.X

Rimworld version: 1.X

Steps to recreate the bug:

What happened:

What you expected to happen instead:

What DLCs are you playing with?

What other mods are you playing with? (If many, only list the ones you suspect might be related)

Error message (From Dev Mode > Debug log):

Error trace (From Dev Mode > Debug log > Copy to clipboard):

</details>

[Please see this sample issue as an example.](https://github.com/IrishMorales/storyteller-dlc-pawns/issues/1#issue-2615484478)


## Requesting new content

If you have any ideas for the mod, please open a new GitHub issue and describe what you'd like to see!

## Contributing code

This project is structured as follows:

```
ModFolder
|_ 1.4
|___ Assemblies
|___ Defs
|___ Source
|___ Patches
|_ 1.5
|___ Assemblies
|___ Defs
|___ Source
|___ Patches
|_ About
|___ About.xml
|___ Preview.png
|_ Languages
|___ LanguageName
|_____ DefInjected
|_____ Keyed
|_____ Strings
|_ Sounds
|_ Textures
|___ StorytellerAndDLCPawns
|_____ Texture1.png
|_____ Texture2.png
|_ Royalty
|___ 1.4
|_____ Patches
|___ 1.5
|_____ Patches
|_ Ideology
|___ 1.4
|_____ Patches
|___ 1.5
|_____ Patches
```

If you have any fixes to "Patches" for a DLC on a specific version (ex. Royalty 1.4), please put it in Royalty/1.4/Patches ONLY IF `MayRequire` does not work on the XML node you are adding. If `MayRequire` works for the node, please put it in that version's folder (ex. 1.4) instead. This is to keep the DLC folders as small as possible to reduce complexity.

In addition, please work on your code in your own branch. Please run `git checkout -b yourbranch` from the `develop` branch, not the `main` branch.

This code adds the storytellers and DLC reps as PawnKinds (ex. "Grenadier" class of pawns), not as WorldPawns (ex. a specific grenadier who's a 36-year-old man with depression named "Bob"). This is because:

1. Rimworld saves pawns in the world save file (which mods do not directly alter without player intervention), not the game assemblies/data (which mods can directly alter). So this is mainly the only way possible to implement this.
2. Each storyteller/DLC rep has some specific pawn behavior code or events for that storyteller/rep only. This cannot be implemented on an individual basis with world pawns (ex. I can't make the game do it so that "Bob" specifically has magic powers all the time), but it can be with PawnKinds.

So this mod works by making EACH storyteller/DLC rep its own PawnKind, then adding game logic/code to make sure only one of each spawn at a given time when the player plays (ex. if PawnKind Cassandra is already in the map, another PawnKind Cassandra can't visit).

Please also follow/match the core game's coding conventions (like NamesCapitalizedLikeThis_Modifier).

Once you're ready to add code, please open a pull request, add me (IrishMorales) reviewer, and describe what your code does in the description. Thanks! :)

## Creating art assets

If you would like to create art for this mod, please create a GitHub issue titled `[Art] I want to create assets for ____`. We will reply to your issue there.

## Localization

Currently, this mod only supports English. If you would like to translate it to your language, please create a GitHub issue titled `[Localization] I want to translate this to ____`. We will reply to your issue there.

## Attribution

This guide is based on the **contributing.md**. [Make your own here](https://contributing.md/)!
