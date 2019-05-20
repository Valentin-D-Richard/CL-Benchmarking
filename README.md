# Benchmarking

This repository aims at listing and comparing the concepts, models, tools and people related to computational linguistics. It is not intended to be exhaustive, and would be rather focused on my interests and personal career experiences. Nevertheless completion suggestions are welcome. The project is structured aroud 4 main entry types split into 7 files respectiveley :
- Modellings
- ModellingRelations
- Tools
- Papers
- Contexts
- ContextRelations
- Persons

This provided databased can be couple with a databse manager to retrieve or visualize information.

## Database specification

The tables are written with comma separated values (.csv) files. They consist of row entries with typed colums (SQL style). Lists are separated by semi-colons and pairs by pipes. Stars are put to indicate the the field is not left empty but just not investigated yet. The relation schemas is given :

### Topic
- short_name : word (primary key)
- long_name : text
- papers : word list (Papers foreign key list)
  - introductory or main result papers
- tags : word list (enumaration)
  - e.g. : grammar, model, concept, field, cognition (theory)...
- comments : text
- strengths : text
- shortcomings : text

### TopicRelations
- first : word (secondary key, Topc foreign key)
- rel_type : word (enumeration)
  - e.g. : syntax (of), sematics (of), subconcept (of), subfield (of), modelling (of), related (to),...
- second : word (secondary key, Topic foreign key)
- paper : word (Papers foreign key list, optional)
  - paper where the link is argumented
  
### Tools
- short_name : word (primary key)
- long_name : text
- type : word (enumeration)
  - e.g. : bank, parser, website,...
- topics : word list (Topic foreign key list)
- comments : text

### Papers
- ref : word (primary key)
  - of the form Author1LastName\_Author1LastName\_...\_year(index)
- authors : word couple list (Person foreign key list)
- year : number
- title : text
- type : word (enumaration)
  - bibtex paper type (article, injournal, inbook, inproceedings, slides,...)
- context : word (Context foreign key, optional)
- modellings : word list (Topic foreign key list)
- comments : text

### Contexts
- short_name : word (primary key)
- long_name : text
- type : word (enumaration)
  - e.g. : workshop, conference, publisher, archive, season_school, lecture, journal,association,...
- description : text

### ContextRelations
- first : word (secondary key, Context foreign key)
- rel_type : word (enumeration)
  - e.g. : supervises,partner,...
- second : word (secondary key, Context foreign key)

### Persons
- last_name : word (secondary key)
- first_name : word (secondary key)
- institute_town : word (optional)
- interests : word list (Topic primary key list)
