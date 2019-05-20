# Benchmarking

This repository aims at listing and comparing the concepts, models, tools and people related to computational linguistics. It is not intended to be exhaustive, and would be rather focused on my interests and personal career experiences. Nevertheless completion suggestions are welcome. The project is structured aroud 4 main entry types split into 6 files respectiveley :
- Modellings
- ModellingRelations
- Tools
- Papers
- Contexts
- Persons

This provided databased can be couple with a databse manager to retrieve or visualize information.

## Database specification

The tables are written with comma separated values (.csv) files. They consist of row entries with typed colums (SQL style). Lists are separated by semi-colons and pairs by pipes. The relation schemas is given :

### Modellings
- short_name : word (primary key)
- long_name : text
- papers : word list (Papers foreign key list)
  - introductory or main result papers
- tags : word list (enumaration)
  - e.g. : grammar, model, concept,...
- comments : text
- strengths : text
- shortcomings : text

### ModellingRelations
- first : word (secondary key, Modelling foreign key)
- rel_type : word (enumeration)
  - e.g. : (has as) syntax (:), (has as) sematics (:), (has as) subconcept (:), ...
- second : word (secondary key, Modelling foreign key)
- paper : word (Papers foreign key list, optional)
  - paper where the link is argumented
  
### Tools
(WIP)

### Papers
- ref : word (primary key)
  - of the form Author1LastName\_Author1LastName\_...\_year(index)
- authors : word couple list (Person foreign key list)
- year : number
- title : text
- type : word (enumaration)
  - bibtex paper type (article, injournal, inbook, proceedings, slides,...)
- context : word (Context foreign key, optional)
- modellings : word list (Modelling foreign key list)
- comments : text

### Contexts
- short_name : word (primary key)
- long_name : text
- type : word (enumaration)
  - e.g. : workshop, conference, publisher, season_school, lecture, journal,...
- description : text

### Persons
- last_name : word (secondary key)
- first_name : word (secondary key)
- email_first : word (optional)
- email_sec : word (optional)
  - email = email_first\@email_sec
- institute_town : word (optional)
- interests : word list (Modelling primary key list)
