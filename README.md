# OSM Off-Road Guidelines (Thailand)

A set of guidelines for improving the OpenStreetMap off-road network in northern Thailand with a focus on enduro, MTB and hiking.

The goal is to bring together existing and new OSM contributors to make better maps available for the offroad community through popular mobile and Garmin applications.

> If you have any feedback, concerns or change requests, please post a message in this OSM forum [thread](https://forum.openstreetmap.org/viewtopic.php?pid=841479).

## Basics

### `highway=track` + `surface=unpaved` + `source=GPS`

4-wheel vehicles (often only offroad type) may be able or are known to use this way. 

- *1.5 meter wide or larger*
- *presence of double tracks in the ground*
- *may look like a path during rainy season due to to grown vegetation*
- *known as "dirt road" or "ถนนดิน" or "thanon din"*

> If the track is temporarily not passable due to fallen trees, add a `barrier=log` node at the location of the obstacle.

### `highway=path` + `motorcycle=yes` + `surface=unpaved` + `source=GPS`

2-wheel vehicles (light-weight and often only offroad type) may be able or are known to use this way.

- *1 meter wide or smaller*
- *give access to nearby fields and villages*
- *found in flat or hilly terrain*
- *known as "dirt path" or "ทางดิน" or "tang din"*

### `highway=footway` + `surface=unpaved` + `source=GPS`

Walking/hiking trails where high-risk extreme enduro/MTB might be possible depending on surface conditions and skills.

- *found often in very steep, mountainous terrain*
- *presence of large rocks or roots*
- *narrow paths with sharp turns requiring pivot turns*
- *known as "footpath" or "ทางเดิน" or "tang deun"*

### Important Notes

- Only add `source=GPS` for roads/trails that have been confirmed to exist through a ground survey. Many roads/paths have been added only using satellite imagery and may be inaccurate.

- If a road/path qualifies for different tags, split it into multiple line segments and tag these separately. e.g. double tracks turns into path. Or the road added via ground survey is extended via satellite imagery.

- If part of your GPS trace include riding inside a creek, stream or river, do not create a `highway` segment for this section.

- Because unpaved road surface conditions in Thailand change very often with weather and seasons, following tags are not taken into consideration: `tracktype`, `smoothness`, `trail_visibility`. 

### Applications

List of applications supporting these basic guidelines:

#### Garmin NightRider

- source OSM Garmin map files from https://www.nightrider.info/ 
- convert appearance with mod file https://mega.nz/file/91tGTKhI#xsVv2_pcxh45qXNyc9aYEEebT_3AbyjCSEBB_c8C30k

#### Garmin AlternativasLibres

- instructions at https://alternativaslibres.org/en/downloads.php?fbclid=IwAR00hHsPRowfFKH9qH0rA3M3sQqNQ9qvq9Cb_WE1wFZHnquR1aA-JYB2XG4

#### OsmAnd Offroad Survey Plugin

- instructions at https://github.com/cmoffroad/osmand-offroad-survey-plugin

### Extras

- [Common myths about OpenStreetMap](https://github.com/cmoffroad/osm-guidelines/blob/main/MYTHS.md)
- [Common mapping mistakes](https://github.com/cmoffroad/osm-guidelines/blob/main/MISTAKES.md)
- [Useful local lingo](https://github.com/cmoffroad/osm-guidelines/blob/main/LINGO.md)
- [How to contribute further?](https://github.com/cmoffroad/osm-guidelines/blob/main/CONTRIBUTE.md)