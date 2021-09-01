# GUIDELINES FOR @GRABOSM

## MINOR ROAD CLASSIFICATIONS

## NEW ADDITIONS

Please follow the official guidelines for minor road classifications https://wiki.openstreetmap.org/wiki/WikiProject_Thailand#Rough_guidelines_for_minor_highway_tag_decision-making_.28useful_in_most_cases.29

### Tips:

- Check existing Mappillary images to investigate whether road is public or private (`highway=service`)
- Is the road within a private area (factory, hotel, temple) or close to an amenity point (temple) => `highway=service`
- A rooftop does not guarantee residential or permanent housing. In fact in most agrictural/farming areas (`highway=track`), isolated buildings are farming huts used for daily work.
- Most `highway=residential` roads are short and found in residential area (landuse), long roads are typically unclassified or agricultural track.
- Check if a long rural road ends at a temple, hotel, estate, facility... (highway=unclassified)
- Does the road look unpaved on satellite imagery (grass/double track) and leads only to agricultural fields/farms? `highway=track`

> DO NOT add a new geometry if you are not sure of its classification.

### highway=service

## CHANGING EXISTING

Do NOT change any existing classification if the road:

- has been updated through a ground survey (visible in GPS traces, mapillary overlay)
- contains a `source`, `source:geometry`, `source:position` tag refering to a ground survey (`GPS`, `gps`, `mapillary`)
- contains an `access` tag or other custom tags
