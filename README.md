# MagicSetsXML

Introduction
============
This XML file contains all sets (or nearly) from alpha to the latest sets released. 

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
(this is not a real API, so there are no builtin filtering features), if you want something more similar to an API, you can check my other project: https://github.com/inuyasha82/mtgrestservice

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

Contributing
============
Everyone is free to contribute reporting new sets, proposing new information to be added, or reporting issues with sets. 
