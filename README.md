# OSM Guidelines

A set of guidelines for improving the OpenStreetMap road network in northern Thailand with a strong focus on off-road.
Based on [official OSM](https://wiki.openstreetmap.org/wiki/Main_Page) and [Thailand](https://wiki.openstreetmap.org/wiki/WikiProject_Thailand) wikis.

## Changesets

### Add a source to changesets

Whether it’s GPS or Maxar/Esri, a [source](https://wiki.openstreetmap.org/wiki/Key:source) helps other mappers understand the context of your contributions.

> Note: adding a source tag to each object is optional.

### Make smaller geographical changesets

Smaller changesets make it easier for others to review your contributions.
A changeset should be ideally within the same country/province and small area.

## Satellite Imagery

### Use Maxar or ESRI imagery instead of Bing

[Bing](https://www.bing.com/maps) imagery in northern Thailand is very outdated (latest [2017](https://dev.virtualearth.net/REST/V1/Imagery/Metadata/Aerial/18.7871861,98.9849548?zl=15&o=xml&key=Am_Iln3EWEST1KZcA-S-glStVM8wMMoHDqr0_xq3HJmzC-k1nGmeL_D7Go-qX-Im&fbclid=IwAR2bgHJOV9LSXQ64J6naWo7J0usECi9h8YVdJ2lEo_6ZcenmuAuVSM91iBI)) and should not be used for imagery surveys.
There are quite a few conflicting tracks and residential roads that were added with Bing but have recently changed.

## GPS / Local survey

### Upload your GPX recordings

Uploaded [GPS traces](https://www.openstreetmap.org/traces) are visible as a map Overlay in [ID editor](https://www.openstreetmap.org/edit) and helps other mappers understand the general accuracy of contributions. 

### Survey end of road

Indicate on the last node of the road:
- add [noexit=yes](https://wiki.openstreetmap.org/wiki/Key:noexit) when there is no possibility to travel further.
- add [fixme=continue](https://wiki.openstreetmap.org/wiki/Key:fixme) when the road continues but you haven’t been able to map it, and optionally describe the reason if there was any obstacle. e.g. [fixme=continue. tree blocking the way.](https://wiki.openstreetmap.org/wiki/Key:fixme)

## General Classification

### Add surface tag (`important`)

> [Grab](https://github.com/GRABOSM/Grab-Data/issues/49) is currently upgrading the minor road network in Thailand and turning a lot of farming and village tracks into highway=residential.
Many of these dirt tracks had no surface specified, so the information is lost during the conversion. 

> I raised the [issue](https://github.com/GRABOSM/Grab-Data/issues/49#issuecomment-824782069) with Grab, but they haven't followed through with their promise to try to update the information accordingly.

- if you do not remember the exact [surface](https://wiki.openstreetmap.org/wiki/Key:surface), use simply surface=unpaved or surface=paved
- when adding roads based on satellite imagery, compare road color with the surrounding area.
- if you are not sure, leave it untagged for other mappers to review.

### Add missing waterway crossing information

Indicate how traffic goes through waterway crossing:

- Add [ford=yes](https://wiki.openstreetmap.org/wiki/Key:fjord) at the node intersection when traffic must cross the riverbed. 
- Add a [bridge=yes](https://wiki.openstreetmap.org/wiki/Key:bridge) road segment when traffic can go over a bridge. Make sure to indicate surface (wood, concrete, metal, ...) and number of [lanes](https://wiki.openstreetmap.org/wiki/Key:lanes) (1 or 2+)
- If you are not sure, add a [fixme=survey bridge/fjord](https://wiki.openstreetmap.org/wiki/Key:fixme) tag at the intersection node.
- If the [waterway](https://wiki.openstreetmap.org/wiki/Key:waterway) (stream or river) is missing, add a small section crossing the road and tag it as [fixme=continue](https://wiki.openstreetmap.org/wiki/Key:fixme)

### Use the appropriate name tag:

- use [name=...](https://wiki.openstreetmap.org/wiki/Key:name) for official road usage.
- use [description=...](https://wiki.openstreetmap.org/wiki/Key:description) for texts that can be viewed by other end-users. E.g. "very steep climb".
- use [note=...](https://wiki.openstreetmap.org/wiki/Key:note) to leave a note to other mappers

If you need to create a signed posted or commonly known activity route (hiking, mountain biking, enduro, …), please create a [relation route](https://wiki.openstreetmap.org/wiki/Relation:route).

## Trails classification

### Only use highway=path for narrow roads.

Only use [highway=path](https://wiki.openstreetmap.org/wiki/Tag:highway=path) when the road is too narrow for a small 4-wheel car to go through, regardless of its main usage or condition (including grown vegetation).

When adding them via Satellite Imagery, make sure they are the thinnest line possible, and there is no housing along. The majority of visible trails on satellite imagery are double tracks, including unmaintained ones. If you are not sure, tag it as [fixme=survey](https://wiki.openstreetmap.org/wiki/Key:fixme)

### Only use highway=footway for designated & signposted ways

Make sure to only use [highway=footway](https://wiki.openstreetmap.org/wiki/Tag:highway=footway) for paths that are planned/maintained for pedestrians access (e.g. sidewalk, golf court footpath). Use instead [highway=path](https://wiki.openstreetmap.org/wiki/Tag:highway=path) for non designated/signposted trails not large enough for a small 4-wheel car. 

- add [motorcyle=yes](https://wiki.openstreetmap.org/wiki/Key:motorcycle) when the path is commonly used by locals on a motorcycle (by default highway=path excludes all non-motorized vehicles). Do not tag yes, if locals only use it on foot (taang deen, ทางเดิน) but you have the skills and motorbike (extreme enduro) to navigate it.
- add [width](https://wiki.openstreetmap.org/wiki/Key:width) in meters to describe how narrow is the path (e.g. 0.5, 1, 1.5, …)
- add [surface](https://wiki.openstreetmap.org/wiki/Key:width)

Optionally,
- add [sac_scale](https://wiki.openstreetmap.org/wiki/Key:sac_scale) to classify hiking difficulty
- add [mtb:scale](https://wiki.openstreetmap.org/wiki/Key:mtb:scale) to classify mountain biking difficulty

### Decision-Tree workflow

- is the path wide enough for a pickup truck? (regardless of grown vegetation and surface smoothness)
    - `yes`: follow [`Minor Road Classification`](#minor-road-classification) below
    - `no`: has the path been built, designated or signposted for pedestrians only (e.g. sidewalk, golf course footpath, attraction walkway…)
        - yes: `highway=footway`
        - no: is the path commonly used by locals on motorcycles?
            - yes: `highway=path` + `motorcycle=yes`
            - no: `highway=path`

## Minor road classification

### Decision-Tree workflow

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
