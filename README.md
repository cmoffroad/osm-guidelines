# OSM Off-Road Guidelines (Thailand)

A set of guidelines for improving the OpenStreetMap off-road network in northern Thailand with a strong focus on enduro.

The goal is to bring together existing and new OSM contributors to make better maps available for the offroad community through popular mobile and Garmin applications.

> Status: `Draft`, if you have any feedback, concerns or change requests, please kindly send me a [message](https://www.openstreetmap.org/message/new/cmoffroad).

## Basics

### `highway=track` + `surface=unpaved` + `source=GPS`

4-wheel vehicles may be able or are known to use this way. 

- *1.5 meter wide or larger*
- *presence of double tracks in the ground*
- *may look like a path during rainy season due to to grown vegetation*
- *known as "dirt road" or "ถนนดิน" or "thanon din"*

### `highway=path` + `motorcycle=yes` + `surface=unpaved` + `source=GPS`

Motorcycles may be able or are known to use this way.

- *1 meter wide or smaller*
- *give access to nearby fields and villages*
- *found in flat or hilly terrain*
- *known as "dirt path" or "ทางดิน" or "tang din"*

### `highway=footway` + `surface=unpaved` + `source=GPS`

Trails used exclusively for walking, only suitable for extreme sports

- *found in very steep, mountainous terrain*
- *presence of large rocks or roots*
- *narrow paths with sharp turns requiring pivot turns*
- *known as "footpath" or "ทางเดิน" or "tang deun"*

### Important Notes

- Only add `source=GPS` for roads/trails that have been confirmed to exist through a ground survey. Many roads/paths have been added only using satellite imagery and may be inaccurate.

- If a road/path qualifies for different tags, split it into multiple line segments and tag these separately. e.g. double tracks turns into path. Or the road added via ground survey is extended via satellite imagery.

- If part of your GPS trace include riding inside a creek, stream or river, do not create a `highway` segment for this section.

- Because unpaved road surface conditions in Thailand change very often with weather and seasons, following tags are not taken into consideration: `tracktype`, `smoothness`. 

### Applications

List of applications supporting these guidelines:

#### Garmin NightRider Mod

- source OSM Garmin map files from https://www.nightrider.info/ 
- convert appearance with mod file https://mega.nz/file/91tGTKhI#xsVv2_pcxh45qXNyc9aYEEebT_3AbyjCSEBB_c8C30k

#### OsmAnd Enduro Plugin

- instructions at https://github.com/cmoffroad/osmand-plugin-enduro

## Advanced

### Upload your GPS recordings

Uploaded [GPS traces](https://www.openstreetmap.org/traces) are visible as a map Overlay in the [OSM ID editor](https://www.openstreetmap.org/edit) and help improve accuracy of road geometries that may be misaligned due to poor GPS signal.

### Indicate the end of the road

- Add to the last node of the road [noexit=yes](https://wiki.openstreetmap.org/wiki/Key:noexit) when there was no possibility to travel further. This prevents other mappers to have do more ground survey to find out.
- Use [fixme=continue](https://wiki.openstreetmap.org/wiki/Key:fixme) when the road continues but you haven’t been able to map it, and optionally describe the reason if there was any obstacle. e.g. [fixme=continue. tree blocking the way.](https://wiki.openstreetmap.org/wiki/Key:fixme)

### Indicate how traffic goes through waterway crossings:

- If the [waterway](https://wiki.openstreetmap.org/wiki/Key:waterway) (stream or river) is missing, add a small section crossing the road.
- Add [ford=yes](https://wiki.openstreetmap.org/wiki/Key:ford) at the node intersection when traffic must cross the river/stream. 
- Add a [bridge=yes](https://wiki.openstreetmap.org/wiki/Key:bridge) + [layer=1](https://wiki.openstreetmap.org/wiki/Key:layer) road segment when traffic can go over a bridge.

### Use the appropriate text tag

- use [description=...](https://wiki.openstreetmap.org/wiki/Key:description) for texts that can be viewed by other end-users. e.g. "very steep climb".
- use [fixme=...](https://wiki.openstreetmap.org/wiki/Key:fixme) for texts that require action from other end-users. e.g. "continue", "resurvey", "precision"...
- use [note=...](https://wiki.openstreetmap.org/wiki/Key:note) to leave a note to other OSM mappers.  e.g. "path widen to double track since July 2021"
- do not use [name=...](https://wiki.openstreetmap.org/wiki/Key:name) which is reserved for official road usage.

### Pick the right minor road classification

Not all unpaved roads may be classified as `highway=track`. e.g. main roads between villages may be `unclassified`, while roads within private estate may be tagged as `service`. 

For more info, see the official [Minor Road Classification](https://wiki.openstreetmap.org/wiki/WikiProject_Thailand#Rough_guidelines_for_minor_highway_tag_decision-making_.28useful_in_most_cases.29).