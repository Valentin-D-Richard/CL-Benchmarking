# Benchmarking

This repository aims at listing and comparing the concepts, models, tools and people related to computational linguistics. It is not intended to be exhaustive, and would be rather focused on my interests and personal career experiences. Nevertheless completion suggestions are welcome. The project is structured aroud 4 main entry types split into 6 files respectiveley :
- Topics
- TopicRelations
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
  - e.g. : grammar, (logical) model, concept (or linguistic theory, -> syntax, semantics, pragmatics,...), field, cognition (theory), tool (parser,...), bank...
- comments : text
- strengths : text
- shortcomings : text

### TopicRelations
- first : word (secondary key, Topc foreign key)
- rel_type : word (enumeration)
  - e.g. : syntax (of), sematics (of), pragmatics (of), subconcept (of), subfield (of), modelling (of), related (to), tool (of), bank (of),...
- second : word (secondary key, Topic foreign key)

### Papers
- ref : ASCII word (primary key)
  - of the form Author1LastName\_Author1LastName\_...\_year(index)
- authors : text couple list (Person foreign key list)
- year : number
- title : text
- type : word (enumaration)
  - bibtex paper type (article, injournal, inbook, inproceedings, slides, book,...)
- context : word (Context foreign key, optional)
- modellings : word list (Topic foreign key list)
- comments : text

### Contexts
- short_name : word (primary key)
- long_name : text
- type : word (enumaration)
  - e.g. : workshop, conference, publisher, (online) repository, season_school, lecture, journal, association, institute,...
- description : text

### ContextRelations
- first : word (secondary key, Context foreign key)
- rel_type : word (enumeration)
  - e.g. : supervises, partner (of),...
- second : word (secondary key, Context foreign key)

### Persons
- last_name : text (secondary key)
- first_name : text (secondary key)
- institute_town : text (optional)
- interests : word list (Topic primary key list)
