# Overview

Do you dream of glassy silicoids?  Or perhaps you'd like some rock-people with sexual dimorphism?  Silfae's "Animated Silicoid Portraits" mod delivers several different options for portraits and extra gameplay features.  Do you wish the gameplay elements were up-to-date so that you can play the Taclariotan Influence or Mandate of Druerd as designed?  Then this mod is for you!

There are lots of other mods which contain these portraits, so why should you choose this one?  None of the others update the species traits, custom empires, or shipset, but this one does!  Please enjoy my translation of Silfae's custom empire into modern Stellaris.

# Changes

All gameplay features from the original mod are upgraded to be fully compatible with Stellaris 3.0.*, the latest version when this was written.  Updates include:

* Update the included Contingency-swap shipset `silicoid_01`
    * Ensure the ship entities are blank for ship sections and instead use the ship hull as the attachment point for the Contingency graphics
    * Add missing entities and weapon locators
    * Remove duplication
    * Fallback for titans, juggernauts, and colossi is Contingency (`ai_01`), which itself will fall back to mammalian
* Update silicoid civics to use modifiers available in Stellaris 3.0 (also now available for Lithoids)
* Allow silicoids as a secondary species and to spawn randomly (which requires at least one random namelist)
* Add a silicoid namelist (sourced from a variety of random name generators)
* Silicoids are now part of the LITHOID archetype (requires Lithoids)
    * They remain a separate Silicoid (`SLCOD`) species class
    * Can use many common built-in traits (although some are specifically omitted by making `trait_silicoid` incompatible with them)
    * Can use (most) Lithoid traits and unique silicoid traits
    * Lithoids (species class) cannot take any silicoid traits
    * Will work with built-in ascension paths and other gameplay features that require `BIOLOGICAL` or `LITHOID` archetypes
* Override `pop_categories` in order to balance silicoid Pop upkeep (0.25 food, 0.75 minerals in most situations, 0.25 food and 0.75 energy for Electroids)
* Update most silicoid traits to work with Stellaris 3.0
    * Update "Sparkly" and "Grotesque" to reduce or increase amenities usage (old effects no longer available)
    * Silicoid and Electroid traits (and Idealized/Demanding Structure) adjusted to work on energy/minerals/food instead of consumer goods
    * The silicoid trait is now a middle ground between biological species and full lithoids - this is a design change from the original so silicoids aren't merely alpha-version lithoids
    * Some trait effects tweaked with an eye towards vanilla balance
* Adjust silicoid setup event to ensure at least 1 farming district on their homeworlds
* Update prescripted empires
    * Taclariotan Influence is now Fanatic Materialist/Authoritarian to meet the requirements for Technocracy - lost Xenophobe to compensate
    * Tacloriotans now also have Sparkly - they had an unused trait pick
    * Taclariotans now use the new `SLCOD1` namelist instead of `ART1`
* Add a second Alt. Silicoid species class (`SLCODALT` which cannot randomly spawn) that contains the same portraits, but uses the default lithoid features without any of the above changes

## Compatibility

This mod has more compatibility concerns than most of my other Silfae's Revisited series.  Because to overwrites `pop_categories` (Pop strata) to adjust silicoid Pop resource upkeep, that makes this mod incompatible with any mods that also adjust Pop strata.  It's also likely to break any time Stellaris makes changes to the underlying Pop strata, such as the anticipated changes for the upcoming 3.1 'Lem' minor release.  These files are completely overwritten: 

* `common/pop_categories/00_social_classes.txt` - regular empire pop strata
* `common/pop_categories/01_gestalt_drones.txt` - gestalt empire pop strata
* `common/pop_categories/02_other_categories.txt` - precursors, criminals/deviants, and miscellaneous pop strata

This mod is also incompatible with mods that add the same species classes, traits, shipset (by name - other reuses of the Contingency will be compatible), or art assets (portraits and meshes).

The Launcher will tell you that some mods are outdated - that is because the dependencies are both out of date with the game's version number.  This mod overwrites and replaces all incompatible code so that the portrait mod will function as originally designed.  You can safely ignore the out-of-date warning for the dependency mods.

Not compatible with achievements.  The shipset does not have NSC classes.

### Dependencies

In order for this mod to function, you **must** install these two mods and load them before this one:

* [Animated Silicoid Portraits](https://steamcommunity.com/sharedfiles/filedetails/?id=1160316076) by Silfae
* [Silfae's city sets updated](https://steamcommunity.com/sharedfiles/filedetails/?id=2247427791) by Nozeminer

### When to Install

This mod should be added before the game has started.  If you remove it from a game in progress, your game may have graphical problems if any species was using the custom portraits or city graphics.

## Known Issues

This mod overwrites the corresponding species class added by "Silfae's city sets updated" so that it will not be available for use.  Instead, the original species class from Silfae (with localisation) is used.  Expect to see one line in error.log like this:

```
[00:50:44][game_singleobjectdatabase.h:147]: Object with key: Silfae-Silicoid already exists
```

## Changelog

* 1.0.0 Initial version
* 1.0.1 Resolve major bug where the `SLCODALT` species class did not get the proper Pop upkeep, prescripted empires require lithoids, allow portrait randomization

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/silicoid_portraits_revisited).

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.

# Special Thanks

I was inspired to extend the original mod when I saw [Endugu](https://steamcommunity.com/profiles/76561198037630876/myworkshopfiles/)'s [expansion](https://steamcommunity.com/sharedfiles/filedetails/?id=1584824947) of [Silfae](https://steamcommunity.com/profiles/76561198021525667/myworkshopfiles/)'s [Animated Xirmian Portraits](https://steamcommunity.com/workshop/filedetails/?id=881118424).  Modular mods that require downloading the original mod(s) help give credit where credit is due.

An extra special thanks to Silfae for creating and sharing so many detailed, animated portraits for the community.