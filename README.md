# MagicSetsXML

Introduction
============
This XML file contains all sets (or nearly) from alpha to the latest sets released (For set i mean everything that has been released with a 3 letter code and a symbol). 

Its main purpose is to be focused only on sets, and nothing else, then you can't find  information about single cards, mechanics, etc. only sets details. The only card detail available is the card composition.

This file is manually updated, so there could be a delay on when a set is released and when is reported here. 
Along with the set information the card_logos folder contains all the symbols.

Edition Item
============

Even if depending on the set type some of the details are different (preconstructed, normal set, commander, etc) all edition have a common set of information listed below:  contains the following information:
- Set exit date (month-year)
- Set name (the name is reported in English, Italian and Spanish)
- Image filename (available in the card 
- 3 Letters set code

You can access the xml file here:

If you need to consume the xml as an API you can use this url: https://inuyasha82.github.io/MagicSetsXML/magicsymbols.xml 
(this is not a real API, so there are no builtin filtering features), if you want something more similar to an API, you can check my other project: https://github.com/inuyasha82/mtgrestservice and deploy it on your server (the project is based on the same xml).

This README is not completed yet.

Set Name 
--------
The set name tag is wrapped inside the <names> tag, since it is reported in different languages: 
```xml
<names>
	<name>English Name</name>
	<name lang="it">Italian Name</name>
	<name lang="es">Spanish Name</name>
</names>
```
Currently only English, Spanish and Italian names are reported. No lang attribute means English language. 
	
Card Composition
----------------
The card compisition is wrapped around the <cards> tag. Depending on the specific sets you can find one or more of the following:
	
* lands
* common
* uncommon
* rare
* mythic rare
* oversize
* other

Other is used when the cards doesn't fall into any of the categories above, or are from some specific sets (i.e. from the vault).

The xml code for this section is:
```xml
<cards>
	<common>101</common>
	<uncommon>60</uncommon>
	<rare>53</rare>
	<mythic>15</mythic>
	<lands>20</lands>
</cards>
```
Normal Set
----------
For the normal set the card composition is composed by:

* Number of lands
* Number of commond cards
* Number of uncommon cards
* Number of rare cards
* Number of mythics cards
* Number of any special card

The xml entry for this type
```xml
<edition>
	<launch>2018-04</launch>
	<code>DOM</code>
	<image>DOM_Symbol.png</image>
	<names>
		<name>Dominaria</name>
	</names>
	<cards>
		<common>101</common>
		<uncommon>80</uncommon>
		<rare>53</rare>
		<mythic>15</mythic>
		<lands>20</lands>
	</cards>
</edition>
```
Preconstructed Sets
===================
A preconstructed set has a little bit different structure, keeping all the common fields (names, code, image, launch, etc.) the card composition field is replaced by the <preconstructed> tag. Here an example of a preconstructed set: 
	
```xml
<edition>
	<launch>2011-04</launch>
	<code> DDG </code>
	<image>DDG_symbol.png</image>
	<names>
		<name>Duel Decks: Knights vs. Dragons</name>
		<name lang="it">Duel Decks: Knights vs. Dragons</name>
	        <name lang="es">Duel Decks: Knights vs. Dragons</name>
	</names>
	<preconstructed decks="2" type="duel">
		<size>60</size>
	</preconstructed>
</edition>
```

The preconstructed tag is composed of two attributes and one child:

* **decks** attribute is the number of decks that compose this set.
* **type** it identify the type of preconstructed set, it can be one of: duel, commander, planechase, multiplayer. It can be left empty.
* The child tag is used to identify the size of each deck in the set.

Special tags
=================
In some cases special tags are used to identify some properties of some particular set. To help to identify what is the type of set.

* From the vault sets : for this type of set there is a special tag that is added to identify it as from the vault:

```xml
<vault />
```

The tag doesn't have any value or attribute. If present it identify the set as one of the "From the vault" series

* Fun sets: actually there are only three fun sets, anyway to help to identify them the tag: 

```xml
<fun />
```
is used.

* Some sets are only available online, in this case the following tag is added:

```xml
<online />
```

Contributing
============
Everyone is free to contribute reporting new sets, proposing new information to be added, or reporting issues with sets. 
