# OSM Guidelines

A set of decision trees to help mappers choose appropriate OSM tags and geometries.

Based on [official OSM](https://wiki.openstreetmap.org/wiki/Main_Page) and [Thailand](https://wiki.openstreetmap.org/wiki/WikiProject_Thailand) wikis.

## OSM Tags

### Minor Road Classification:

- is the road exclusively for pedestrians ?
  - `yes`: [highway=pedestrian](https://wiki.openstreetmap.org/wiki/Tag:highway=pedestrian)
  - `no`: is the road inside a private property/estate/facility ?
    - `yes`: is the road within a gated housing community?
      - `yes`: [highway=residential](https://wiki.openstreetmap.org/wiki/Tag:highway=residential)
      - `no`: does the road lead to a specific property/building ?
        - `yes`: [highway=service](https://wiki.openstreetmap.org/wiki/Tag:highway=service) + [service=driveway](https://wiki.openstreetmap.org/wiki/Tag:service=driveway)
        - `no`: [highway=service](https://wiki.openstreetmap.org/wiki/Tag:highway=service)
    - `no`: is the main purpose of the road traffic through?
      - `yes`: is it the main link between 2 towns/villages/hamlets/settlements ? 
        - `yes`: is the surrounding network large enough to justify a more significant road ? (e.g. a few unclassified, residentials roads)
          - `yes`: [highway=tertiary](https://wiki.openstreetmap.org/wiki/Tag:highway=tertiary)
          - `no`: [highway=unclassified](https://wiki.openstreetmap.org/wiki/Tag:highway=unclassified)    
        - `no`: [highway=unclassified](https://wiki.openstreetmap.org/wiki/Tag:highway=unclassified)
      - `no`: is the main purpose of the road access to forestry/agricutural fields?
        - `yes`: [highway=track](https://wiki.openstreetmap.org/wiki/Tag:highway=track)
        - `no`: is the main purpose of the road access to permanent residences ? 
          - `yes`: [highway=residential](https://wiki.openstreetmap.org/wiki/Tag:highway=residential)
          - `no`: [highway=unclassified](https://wiki.openstreetmap.org/wiki/Tag:highway=unclassified)

> Note: A "traffic through road" means vehicles passing through an area who's destination is elsewhere.
Next destination could be a village, a temple, an estate, or joining a road of equal or greater importance.

> Note: If a road qualify for multiple tag classifications, it may need to be split into separate segments. Follow [Splitting Road Segments](#splitting-road-segments) below to find out.

> Note: If you are not sure which classification to use, do no change it. If you are adding a new road, tag it [highway=road](https://wiki.openstreetmap.org/wiki/Tag:highway=road) so someone else can review it.

### Path Classification:

- is the path wide enough for a pickup truck? (regardless of grown vegetation and surface smoothness)
  - `yes`: follow [Minor Road Classification workflow](#minor-road-classification) above
  - `no`: has the path been built, designated or signposted for pedestrians only (e.g. sidewalk, golf course footpath, attraction walkway…)
    - `yes`: [highway=footway](https://wiki.openstreetmap.org/wiki/Tag:highway=footway)
    - `no`: is the path commonly used by locals on motorcycles?
      - `yes`: [highway=path](https://wiki.openstreetmap.org/wiki/Tag:highway=path) + [motorcycle=yes](https://wiki.openstreetmap.org/wiki/Key:motorcycle)
      - `no`: [highway=path](https://wiki.openstreetmap.org/wiki/Tag:highway=path)

## Geometries

### Splitting Road Segments:

- does the road segment both follow the main way and branch out of it ?
  - `yes`: split it at the junction and tag both segments separately
  - `no`: is there a major change of surface along the road segment ? (paved to/from unpaved, long sections)
    - `yes`: split it where the change occurs and tag both segments separately
    - `no`: does the road qualify for different highway classification ?
      - `yes`: is the main road purpose traffic through ?
        - `yes`: do no split
        - `no`: split it where the change occurs and tag both segments separately
        
### Merging Road Segments:

- are both roads segments consecutive, follow the main way and share identical tag classification including surface and highway ?
  - `yes`: both segments can be merged
  - `no`: do not merge
