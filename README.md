# OSM Guidelines

A set of guidelines for improving the OpenStreetMap road network in northern Thailand with a strong focus on off-road.

Based on [global](https://wiki.openstreetmap.org/wiki/Main_Page) and [Thailand](https://wiki.openstreetmap.org/wiki/WikiProject_Thailand) OSM wikis. 

> It has been reviewed by some of the members of the Thai OSM community. Some parts may be moved to the official wiki (e.g. [Minor Road Classification](https://wiki.openstreetmap.org/wiki/WikiProject_Thailand#Rough_guidelines_for_minor_highway_tag_decision-making_.28useful_in_most_cases.29))

> Subject to changes, if you have any feedback, concerns or change requests, please kindly send me a [message](https://www.openstreetmap.org/message/new/cmoffroad).

## Changesets

### Add a source to changesets

Whether it’s GPS or Maxar/Esri/Mapbox, a [source](https://wiki.openstreetmap.org/wiki/Key:source) helps other mappers understand the context of your contributions.

### Make small geographical changesets

Smaller changesets make it easier for others to review your contributions.
A changeset should be ideally within the same province/district.

## Ground surveys

### Upload your GPX recordings

Uploaded [GPS traces](https://www.openstreetmap.org/traces) are visible as a map Overlay in [ID editor](https://www.openstreetmap.org/edit) and help other mappers understand the general accuracy of contributions. 

### Add a source tag

Add/Update [source](https://wiki.openstreetmap.org/wiki/Key:source) tag for all objects you added/modified to `source=GPS` or `source=survey` to reflect latest context.

### Indicate end of the road

When adding or extending roads/paths based on GPS recording, add to the last node of the road:
- [noexit=yes](https://wiki.openstreetmap.org/wiki/Key:noexit) when there was no possibility to travel further (including path)
- [fixme=continue](https://wiki.openstreetmap.org/wiki/Key:fixme) when the road continues but you haven’t been able to map it, and optionally describe the reason if there was any obstacle. e.g. [fixme=continue. tree blocking the way.](https://wiki.openstreetmap.org/wiki/Key:fixme)

## Imagery surveys

### Use ESRI/Mapbox/Maxar instead of Bing

[Bing](https://www.bing.com/maps) imagery in northern Thailand is very outdated (latest [2017](https://dev.virtualearth.net/REST/V1/Imagery/Metadata/Aerial/18.7871861,98.9849548?zl=15&o=xml&key=Am_Iln3EWEST1KZcA-S-glStVM8wMMoHDqr0_xq3HJmzC-k1nGmeL_D7Go-qX-Im&fbclid=IwAR2bgHJOV9LSXQ64J6naWo7J0usECi9h8YVdJ2lEo_6ZcenmuAuVSM91iBI)) and should be avoided for imagery surveys.

There are quite a few conflicting tracks and residential roads that were added with Bing but have recently changed.

ESRI, Mapbox, and Maxar are good alternatives.

> Note: Maxar may have a slight offset in certain areas. Make sure to switch between layers to identify which imagery is more accurate.

### Add a source tag

Add/Update [source](https://wiki.openstreetmap.org/wiki/Key:source) tag for all objects you changed to e.g. `source=Maxar`, `source=Mapbox`, `source=ESRI` to reflect latest context.

> Refrain from modifying an existing object if its latest modifications was done with a ground surveys.

### Avoid adding paths

Make sure they are the thinnest line possible, and there is no housing along. The majority of visible trails on satellite imagery are double tracks, including unmaintained ones. If you are not sure, do not add it, or tag it as [fixme=survey](https://wiki.openstreetmap.org/wiki/Key:fixme)

## Places

### How to tag villages

- draw an area around the main part of the settlement(s) and tag it as [landuse=residential](https://wiki.openstreetmap.org/wiki/Tag:landuse=residential)
- add a point at the center of the village and tag it with
  - [place=hamlet](https://wiki.openstreetmap.org/wiki/Tag:place=hamlet)  for an isolated settlement, typically with less than 200 inhabitants, or around 50 houses
  - [place=village](https://wiki.openstreetmap.org/wiki/Tag:place=village)  for a larger settlement with 200-1000 inhabitants or 50-250 houses
  - [place=town](https://wiki.openstreetmap.org/wiki/Tag:place=town) for larger settlements
  - [name](https://wiki.openstreetmap.org/wiki/Key:name) with the official name of the village in Thai (if known)
  - [name:en](https://wiki.openstreetmap.org/wiki/Key:name) with the official name of the village in English (if known)

### How to tag temples

- draw an area around the temple grounds and tag it as [landuse=religious](https://wiki.openstreetmap.org/wiki/Tag:landuse=religious)
- add a point at the center of the temple grounds and tag it with
  - [amenity=place_of_worship](https://wiki.openstreetmap.org/wiki/Tag:amenity=place_of_worship) 
  - [name](https://wiki.openstreetmap.org/wiki/Key:name) with the official name of the temple in Thai (if known)
  - [name:en](https://wiki.openstreetmap.org/wiki/Key:name) with the official name of the temple in English (if known)
  - [religion](https://wiki.openstreetmap.org/wiki/Key:name) with the relation (e.g. buddhist) (if known)
- optionally, draw an area for each of the main buildings and tag them as [building=yes](https://wiki.openstreetmap.org/wiki/Tag:building=yes)

## Minor Roads

### Always add a surface tag:

When adding a new road, or modifying an existing one, please make sure a [surface](https://wiki.openstreetmap.org/wiki/Key:surface) tag is always present. This is to ensure routers don't redirect normal traffic through off-road conditions.

> Many dirt roads have been wrongly tagged as `highway=track` without surface. When their classification change, the surface information is lost. 

- If the road qualifies for multiple surface classification, it may need to be split into separate segments. Follow [Splitting Road Segments](#splitting-road-segments) below to find out.
- if you do not remember the exact surface or if the road surface may change frequently, use simply [surface=unpaved](https://wiki.openstreetmap.org/wiki/Tag:surface=unpaved) or [surface=paved](https://wiki.openstreetmap.org/wiki/Tag:surface=paved)
- when adding roads based on satellite imagery, compare road color with the surrounding area. If you are not sure, leave it untagged for other mappers to review.

### Choose the right minor road classification:

- is the path wide enough for a pickup truck? (regardless of grown vegetation and surface smoothness)
  - `yes`: [Choose the right path classification](#choose-the-right-path-classification)
  - `no`: is the road exclusively for pedestrians?
    - `yes`: [highway=pedestrian](https://wiki.openstreetmap.org/wiki/Tag:highway=pedestrian)
    - `no`: is the road inside a property/estate/facility/park?
      - `yes`: is the road within a gated housing community?
        - `yes`: [highway=residential](https://wiki.openstreetmap.org/wiki/Tag:highway=residential)
        - `no`: is the road frequently used as through traffic?
          - `yes`: [highway=unclassified](https://wiki.openstreetmap.org/wiki/Tag:highway=unclassified)
          - `no`: does the road lead to a specific building?
            - `yes`: [highway=service](https://wiki.openstreetmap.org/wiki/Tag:highway=service) + [service=driveway](https://wiki.openstreetmap.org/wiki/Tag:service=driveway)
            - `no`: [highway=service](https://wiki.openstreetmap.org/wiki/Tag:highway=service)
      - `no`: is the road frequently used as through traffic?
        - `yes`: is it the main link between 2 towns/villages/hamlets/settlements ? 
          - `yes`: is the surrounding network large enough to justify a more significant road?
            - `yes`: [highway=tertiary](https://wiki.openstreetmap.org/wiki/Tag:highway=tertiary)
            - `no`: [highway=unclassified](https://wiki.openstreetmap.org/wiki/Tag:highway=unclassified)    
          - `no`: [highway=unclassified](https://wiki.openstreetmap.org/wiki/Tag:highway=unclassified)
        - `no`: is the main purpose of the road access to forestry/agricultural fields?
          - `yes`: [highway=track](https://wiki.openstreetmap.org/wiki/Tag:highway=track)
          - `no`: is the main purpose of the road access to permanent residences? 
            - `yes`: [highway=residential](https://wiki.openstreetmap.org/wiki/Tag:highway=residential)
            - `no`: [highway=unclassified](https://wiki.openstreetmap.org/wiki/Tag:highway=unclassified)

#### Important Notes

- A "through traffic road" means vehicles passing through an area whose destination is elsewhere.
The next destination could be a village, a temple, an estate, or joining a road of equal or greater importance.

- If a road qualifies for multiple tag classifications, it may need to be split into separate segments. Follow [Splitting Road Segments](#splitting-road-segments) below to find out.

- If you are not sure which classification to use, do no change it. If you are adding a new road geometry, tag it as [highway=road](https://wiki.openstreetmap.org/wiki/Tag:highway=road) for someone to review. 

### Choose the right path classification:

- is the path too narrow for a pickup truck? (regardless of grown vegetation and surface smoothness)
  - `yes`: has the path been built, maintained exclusively for pedestrians (e.g. sidewalk, golf course footpath, attraction walkway…)
    - `yes`: [highway=footway](https://wiki.openstreetmap.org/wiki/Tag:highway=footway)
    - `no`: is the path commonly used by locals on motorcycles?
      - `yes`: [highway=path](https://wiki.openstreetmap.org/wiki/Tag:highway=path) + [motorcycle=yes](https://wiki.openstreetmap.org/wiki/Key:motorcycle)
      - `no`: [highway=path](https://wiki.openstreetmap.org/wiki/Tag:highway=path)

For [highway=path](https://wiki.openstreetmap.org/wiki/Tag:highway=path), additionally, you may want to add:
- [width](https://wiki.openstreetmap.org/wiki/Key:width) in meters to describe how narrow is the path (e.g. 0.5, 1, 1.5, …)
- [sac_scale](https://wiki.openstreetmap.org/wiki/Key:sac_scale) to classify hiking difficulty
- [mtb:scale](https://wiki.openstreetmap.org/wiki/Key:mtb:scale) to classify mountain biking difficulty

### Split Road Segments:

- does the road segment both follow the main way and branch out of it?
  - `yes`: split it at the junction and tag both segments separately
  - `no`: is there a major change of surface along the road segment? (paved to/from unpaved, long sections)
    - `yes`: split it where the change occurs and tag both segments separately
    - `no`: does the road qualify for different highway classifications?
      - `yes`: is the main road purpose through traffic?
        - `yes`: do no split
        - `no`: split it where the change occurs and tag both segments separately

> Important: Do NOT curve road segments at junctions or exaggerate curves in other scenarios.
        
### Merge Road Segments:

- are both road segments consecutive, follow the main way and share identical tag classification including surface and highway?
  - `yes`: both segments can be merged
  - `no`: do not merge

### Use the appropriate name tag:

- use [name=...](https://wiki.openstreetmap.org/wiki/Key:name) for official road usage.
- use [description=...](https://wiki.openstreetmap.org/wiki/Key:description) for texts that can be viewed by other end-users. E.g. "very steep climb".
- use [note=...](https://wiki.openstreetmap.org/wiki/Key:note) to leave a note to other mappers

If you need to create a signed posted or commonly known activity route (hiking, mountain biking, enduro, …), please create a [relation route](https://wiki.openstreetmap.org/wiki/Relation:route).

### Indicate how traffic goes through waterway crossings:

- Add [ford=yes](https://wiki.openstreetmap.org/wiki/Key:fjord) at the node intersection when traffic must cross the river/stream. 
- Add a [bridge=yes](https://wiki.openstreetmap.org/wiki/Key:bridge) + [layer=1](https://wiki.openstreetmap.org/wiki/Key:layer) road segment when traffic can go over a bridge. Make sure to indicate surface (wood, concrete, metal, ...) and number of [lanes](https://wiki.openstreetmap.org/wiki/Key:lanes) (1 or 2+)
- If you are not sure, add a [fixme=survey bridge/fjord](https://wiki.openstreetmap.org/wiki/Key:fixme) tag at the intersection node.
- If the [waterway](https://wiki.openstreetmap.org/wiki/Key:waterway) (stream or river) is missing, add a small section crossing the road and tag it as [fixme=continue](https://wiki.openstreetmap.org/wiki/Key:fixme)

### Avoid tracktype

[tracktype](https://wiki.openstreetmap.org/wiki/Key:tracktype) should be normally used only on [highway=track](https://wiki.openstreetmap.org/wiki/Tag:highway=track) and unpaved roads, to indicate how well the road is maintained.

It has been wrongly used to indicate:
- [surface=paved](https://wiki.openstreetmap.org/wiki/Tag:surface=paved) (`grade1`)
- main road (`grade1`) instead of [highway=unclassified](https://wiki.openstreetmap.org/wiki/Tag:highway=unclassified)
- difficulty or [smoothness](https://wiki.openstreetmap.org/wiki/Key:smoothness) (`grade4`, `grade5`)

Additionally, road conditions change every season in Thailand and it is impossible to maintain the current status of every unpaved road.

If you want to use it, make sure it matches the examples below, and you update its value over the year.
![tracktype](https://wiki.openstreetmap.org/w/images/thumb/7/7f/Tracktype.jpg/800px-Tracktype.jpg)
