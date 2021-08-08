# OSM Guidelines

A set of guidelines to help mappers choose appropriate OSM tags and geometries.

Based on [global](https://wiki.openstreetmap.org/wiki/Main_Page) and [Thailand](https://wiki.openstreetmap.org/wiki/WikiProject_Thailand) OSM wikis. Reviewed by members of the Thai OSM Community.

> Subject to minor changes (wording, and special cases). The majority of cases should be covered.

## OSM Tags

### Minor Road Classification:

- is the road exclusively for pedestrians?
  - `yes`: [highway=pedestrian](https://wiki.openstreetmap.org/wiki/Tag:highway=pedestrian)
  - `no`: is the road within a private property/estate/facility?
    - `yes`: is the road within a gated housing community?
      - `yes`: [highway=residential](https://wiki.openstreetmap.org/wiki/Tag:highway=residential)
      - `no`: is the road within a large property/estate/facility and frequently used as through traffic?
        - `yes`: [highway=unclassified](https://wiki.openstreetmap.org/wiki/Tag:highway=unclassified)
        - `no`: is the main purpose of the road access to forestry/agricultural fields?
          - `yes`: [highway=track](https://wiki.openstreetmap.org/wiki/Tag:highway=track)
          - `no`: does the road lead to a specific building?
            - `yes`: [highway=service](https://wiki.openstreetmap.org/wiki/Tag:highway=service) + [service=driveway](https://wiki.openstreetmap.org/wiki/Tag:service=driveway)
            - `no`: [highway=service](https://wiki.openstreetmap.org/wiki/Tag:highway=service)
    - `no`: is the main purpose of the road through traffic?
      - `yes`: is it the main link between 2 towns/villages/hamlets/settlements ? 
        - `yes`: is the surrounding network large enough to justify a more significant road? (e.g. a few unclassified, residential roads)
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

- If you change the classification of an existing [highway=track](https://wiki.openstreetmap.org/wiki/Tag:highway=track) that had no [surface](https://wiki.openstreetmap.org/wiki/Key:surface) specified, make sure to add [surface=unpaved](https://wiki.openstreetmap.org/wiki/Tag:surface=unpaved) if the road seems not paved. *Many dirt roads have been wrongly added as a track to be automatically rendered off-road in outdoor applications*

- If you are not sure which classification to use, do no change it. If you are adding a new road geometry, tag it as [highway=road](https://wiki.openstreetmap.org/wiki/Tag:highway=road) for someone to review. 

### Path Classification:

- is the path wide enough for a pickup truck? (regardless of grown vegetation and surface smoothness)
  - `yes`: follow [Minor Road Classification workflow](#minor-road-classification) above
  - `no`: has the path been built, maintained exclusively for pedestrians (e.g. sidewalk, golf course footpath, attraction walkway…)
    - `yes`: [highway=footway](https://wiki.openstreetmap.org/wiki/Tag:highway=footway)
    - `no`: is the path commonly used by locals on motorcycles?
      - `yes`: [highway=path](https://wiki.openstreetmap.org/wiki/Tag:highway=path) + [motorcycle=yes](https://wiki.openstreetmap.org/wiki/Key:motorcycle)
      - `no`: [highway=path](https://wiki.openstreetmap.org/wiki/Tag:highway=path)

## Geometries

### Splitting Road Segments:

- does the road segment both follow the main way and branch out of it?
  - `yes`: split it at the junction and tag both segments separately
  - `no`: is there a major change of surface along the road segment? (paved to/from unpaved, long sections)
    - `yes`: split it where the change occurs and tag both segments separately
    - `no`: does the road qualify for different highway classifications?
      - `yes`: is the main road purpose through traffic?
        - `yes`: do no split
        - `no`: split it where the change occurs and tag both segments separately
        
### Merging Road Segments:

- are both road segments consecutive, follow the main way and share identical tag classification including surface and highway?
  - `yes`: both segments can be merged
  - `no`: do not merge
