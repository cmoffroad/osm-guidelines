## HOW TO CONTRIBUTE FURTHER ?

### Add missing `surface=paved` or `surface=unpaved` to existing roads
Make sure to split the road segment that shares different surface conditions.

> Note: it's ok to use a more precise surface type however beware some terms are too vague and misused e.g. `dirt`, `ground`

### Add missing `source=GPS` tag to road segments that have been confirmed via a ground survey
Make sure to split the road segment if part of it has not been surveyed.

> Do NOT tag an entire road segment if you havent surveyed the whole length. There might be a private property gate, an impassable section...

### Tag paths large enough for a 4WD as `highway=track`
Many double tracks have been incorrectly tagged as path due to grown vegetation, poor surface conditions and lazy mappers.
Best way to know? Ask nearby villagers/farmers if a pickup track can go.

### Indicate the end of the road

- Add to the last node of the road [noexit=yes](https://wiki.openstreetmap.org/wiki/Key:noexit) when there was no possibility to travel further. This prevents other mappers to have do more ground survey to find out. 
- Use [fixme=continue](https://wiki.openstreetmap.org/wiki/Key:fixme) when the road continues but you haven’t been able to map it, and optionally describe the reason if there was any obstacle. e.g. [fixme=continue. tree blocking the way.](https://wiki.openstreetmap.org/wiki/Key:fixme)

### Indicate how vehicles go through waterway crossings:

- If the [waterway](https://wiki.openstreetmap.org/wiki/Key:waterway) (stream or river) is missing, add a small section crossing the road.
- Add [ford=yes](https://wiki.openstreetmap.org/wiki/Key:ford) at the node intersection when vehicles must cross the river/stream. 
- Add a [bridge=yes](https://wiki.openstreetmap.org/wiki/Key:bridge) + [layer=1](https://wiki.openstreetmap.org/wiki/Key:layer) road segment when traffic can go over a bridge.

### Upload your GPS recordings

Uploaded [GPS traces](https://www.openstreetmap.org/traces) are visible as a map Overlay in the [OSM ID editor](https://www.openstreetmap.org/edit) and help improve accuracy of road geometries that may be misaligned due to poor GPS signal.