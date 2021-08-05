# Workflows

A set of decision-tree workflow guidelines for choosing appropriate OSM tags.

## Minor Road Classification:

- is the road within a private estate ?
  - `yes`: is the road within a gated housing community?
    - `yes`: `highway=residential`
    - `no`: does the road lead to specific properties/buildings ?
      - `yes`: `highway=service` + `service=driveway`
      - `no`: is the road narrow and located between properties to access utilities ?
        - `yes`: `highway=service` + `service=alley`
        - `no`: ``highway=service`
  - `no`: is the main purpose of the road traffic through?
    - `yes`: is it the main link between 2 towns/villages/hamlets/settlements ? 
      - `yes`: `highway=tertiary`
      - `no`: `highway=unclassified`
    - `no`: is the main purpose of the road agricultural/forestry access?
      - `yes`: `highway=track`
      - `no`: are there permanent residences along the road?
        - `yes`: `highway=residential`
        - `no`: `highway=unclassified`

> Note: A "traffic through road" means vehicles passing through an area who's destination is elsewhere.
Next destination could be a village, a temple, an estate, or joining a road of equal or greater importance.

> Note: If a road qualify for multiple tag classifications (e.g. different highway, surface...), it should be split into separate segments. e.g. The first 100 meters of an agricultural track may be paved an have permanent houses along. First part could be tagged as a paved residential, while the rest stay as an unpaved track.

## Path Classification:

- is the path wide enough for a pickup truck? (regardless of grown vegetation and surface smoothness)
  - `yes`: follow [`Minor Road Classification workflow`](#minor-road-classification) above
  - `no`: has the path been built, designated or signposted for pedestrians only (e.g. sidewalk, golf course footpath, attraction walkway…)
    - `yes`: `highway=footway`
    - `no`: is the path commonly used by locals on motorcycles?
      - `yes`: `highway=path` + `motorcycle=yes`
      - `no`: `highway=path`
