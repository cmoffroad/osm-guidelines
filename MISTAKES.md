## Common OpenStreetMap (OSM) mapping mistakes

### Extending an existing road that may share different tags:
Always create a new road segment and add the necessary tags. Consecutive segments of the same road sharing identical tags can be always merged later on.

### Not splitting an existing road that may share different tags:
Split a road into multiple segments if different sections need different tags. 
e.g. first section is paved within a residential area, the rest is an unmaintained agricultural track.

### Setting or changing a road to the wrong classification
Make sure to refer to the official guidelines and decision tree.
If you are unsure about the correct classification, do not add/change it.
> https://wiki.openstreetmap.org/wiki/WikiProject_Thailand#Rough_guidelines_for_minor_highway_tag_decision-making_.28useful_in_most_cases.29

### Creating a new track/path purely on a GPS trace.
In mountainous areas, GPS traces may be wrong by a few dozen meters due to poor signals. If the track/path is visible on satellite imagery, follow its shape as much as you can.

### Using outdated and misaligned imagery
The default Bing imagery is most of the time outdated and misaligned. A better alternative is Maxar Premium Imagery available in the layers menu.

### Using the wrong text tag

- use [name=...](https://wiki.openstreetmap.org/wiki/Key:name) only for official road usage.
- use [description=...](https://wiki.openstreetmap.org/wiki/Key:description) for texts that can be viewed by other end-users. e.g. "very steep climb".
- use [fixme=...](https://wiki.openstreetmap.org/wiki/Key:fixme) for texts that require action from other end-users. e.g. "continue", "resurvey", "precision"...
- use [note=...](https://wiki.openstreetmap.org/wiki/Key:note) to leave a note to other OSM mappers.  e.g. "path widen to double track since July 2021"

### Not using a proper description for your changes:
Use a good changeset description so that other mappers can understand your changes
https://wiki.openstreetmap.org/wiki/Good_changeset_comments

### Making changes in completely different geographical areas:
Split your changes into smaller geographical changesets.
https://wiki.openstreetmap.org/wiki/Changeset#Geographical_size_of_changesets

### Changing major roads classification
If you are a new mapper, leave this task to experienced mappers.