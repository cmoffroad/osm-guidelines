# OSM Tags

A set of decision trees to help mappers choose appropriate OSM tags.

## Minor Road Classification:

- is the road exclusively for pedestrians ?
  - `yes`: [highway=pedestrian](https://wiki.openstreetmap.org/wiki/Tag:highway=pedestrian)
  - `no`: is the road within a private estate ?
    - `yes`: is the road within a gated housing community?
      - `yes`: [highway=residential](https://wiki.openstreetmap.org/wiki/Tag:highway=residential)
      - `no`: does the road lead to specific properties/buildings ?
        - `yes`: [highway=service](https://wiki.openstreetmap.org/wiki/Tag:highway=service) + [service=driveway](https://wiki.openstreetmap.org/wiki/Tag:service=driveway)
        - `no`: is the road narrow and located between properties to access utilities ?
          - `yes`: [highway=service](https://wiki.openstreetmap.org/wiki/Tag:highway=service) + [service=alley](https://wiki.openstreetmap.org/wiki/Tag:service=alley)
          - `no`: [highway=service](https://wiki.openstreetmap.org/wiki/Tag:highway=service)
    - `no`: is the main purpose of the road traffic through?
      - `yes`: is it the main link between 2 towns/villages/hamlets/settlements ? 
        - `yes`: is the surrounding network large enough to justify a more significant road ? (a few unclassified, residentials) 
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

> Note: If a road qualify for multiple tag classifications (e.g. different highway, surface...), it should be split into separate segments. e.g. The first 100 meters of an agricultural track may be paved an have permanent houses along. First part could be tagged as a paved residential, while the rest stay as an unpaved track.

## Path Classification:

- is the path wide enough for a pickup truck? (regardless of grown vegetation and surface smoothness)
  - `yes`: follow [Minor Road Classification workflow](#minor-road-classification) above
  - `no`: has the path been built, designated or signposted for pedestrians only (e.g. sidewalk, golf course footpath, attraction walkway…)
    - `yes`: [highway=footway](https://wiki.openstreetmap.org/wiki/Tag:highway=footway)
    - `no`: is the path commonly used by locals on motorcycles?
      - `yes`: [highway=path](https://wiki.openstreetmap.org/wiki/Tag:highway=path) + [motorcycle=yes](https://wiki.openstreetmap.org/wiki/Key:motorcycle)
      - `no`: [highway=path](https://wiki.openstreetmap.org/wiki/Tag:highway=path)
