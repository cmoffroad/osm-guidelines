# Workflows

A set of decision-tree workflow guidelines OSM tags.

## Minor Road Classification:

- is the road within a private estate ?
  - `yes`: is the road within a gated housing community?
    - `yes`: `highway=residential`
    - `no`: `highway=service`
  - `no`: is the main purpose of the road traffic through?
    - `yes`: does it link two towns/villages/hamlets/settlements ? 
      - `yes`: `highway=tertiary`
      - `no`: `highway=unclassified`
    - `no`:  does the road have no other function other than for residential purposes?
      - `yes`: `highway=residential`
      - `no`: is the main purpose of the road agriculture/forestry ?
        - `yes`: `highway=track`
        - `no`: `highway=unclassified`

## Path Classification:

- is the path wide enough for a pickup truck? (regardless of grown vegetation and surface smoothness)
    - `yes`: follow `Minor Road Classification workflow` above
    - `no`: has the path been built, designated or signposted for pedestrians only (e.g. sidewalk, golf course footpath, attraction walkway…)
        - yes: `highway=footway`
        - no: is the path commonly used by locals on motorcycles?
            - yes: `highway=path` + `motorcycle=yes`
            - no: `highway=path`
