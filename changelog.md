# EDAM\_1.4.owl

- A major revision of the "Topic" sub-ontology expanding this into medical concepts (~60 new topics), following an effort led by Cath Brooksbank with major input from partners from EMTRAIN (European Medicines research TRAINing network) and partners from related ESFRI (European Strategy Forum on Research Infrastructures) projects.
- Fixing many minor bugs (mostly overlapping or bad synonyms) within topics, and other clean-ups.
- Removed the lowest tier of the "Topic" branch (mostly by moving terms up a level).
- Removed all `oboOther:namespace` and some subsets; removed most `oboInOwl:inSubset` for deprecated concepts and added subset 'obsolete'.
- New forms of UniProt identifiers added (regex).
- Examples of IANA and chemical media types added.
- A couple of file-/data-handling concepts added (operations and an identifier).
- An OBO-format version of EDAM has been omitted. We will only resume providing OBO format in case of substantial demand or full automation of the conversion.
- Documentation files have been substantially updated, _e.g._ specifying channels for the most welcome community contributions.

  **And most importantly:**
- EDAM is now being developed at GitHub!!!



# EDAM\_1.3.owl

Highlights of changes:
- Greatly simplified "Topic" branch.
- Many new terms added for annotating tools in the [BioToolsRegistry](bioregistry.cbs.dtu.dk).



# EDAM\_1.2.owl

This is the first version of EDAM now that is maintained in OWL format. The OBO-format version is generated from it by processing the OWL file.

Highlights of changes:
- New references to MeSH.
- Edits to synonyms.
- About a dozen new formats.

- Clean-ups for cleaner viewing in Protege and OLS:
- Removed problematic "has input" and "has output" axioms.
- Cleaner annotations on the ontology itself.




# EDAM\_1.1.obo

Many additions (mostly in "Operation" and some in "Topic" branches) for "next generation" sequencing analysis.
EDAM now provides complete coverage of biological domains and bioinformatics methods from [SeqWiki](http://seqanswers.com/wiki/SEQanswers).
SeqWiki "biological domains" map to EDAM "Topic", SeqWiki "bioinformatics methods" map to EDAM "Operation".


# EDAM\_1.0.obo
The first release proper.

General changes
  - New style for concept IDs: 4 digit number, subontology namespace / subset("operation", "topic" etc) _e.g._ 
   "EDAM\_operation:0004" (new style) instead of "EDAM:0000004" (old style).

  - New relations ("has function", "is function of") are defined for use by annotators (they are not used in EDAM itself).

  - Synonyms are defined that define related or relevant concepts in many other ontologies and systems. Synonyms are added throughout but especially on top-level concepts ("Operation", "Data", "Format" and "Topic") and relations ("has input", "is input of", "has output", "is output of", "has topic", "is topic of", "has format", "is format of", "has function", "is function of").

  - New concept attributes and modifiers have been added, most importantly:
  
   "{note}" for comments on synonyms and other attributes, _e.g._
`synonym: "assembly" NARROW [SO:0001248] {note="Perhaps surprisingly, the definition of 'SO:assembly' is narrower than the 'SO:sequence\_assembly'."}`.

   "{since}" for annotation of version information, _e.g._ data of creation or obsoletion of a concept id:
`id: EDAM\_data:3165 {since=1.0}` or
`is\_obsolete: true {since=1.0}`.

"Format" branch
  - 10 new formats.




# EDAM\_beta13.obo
General changes
  - "Identifier" branch moved from top-level to beneath "Data". The "identifier" namespace / definitions have been kept!
  - Extensive revision of "Data", "Operation" and "Topic" branches to reduce clutter and ease navigation.
  - Bottom-up clean up removing terms that are too fine-grained. Top-down clean up to add or remove terms to aid navigation.
  - has\_topic (defined on "Data" and "Operation") replaces in\_topic.
  - Duplicated relationships (child terms erroneously restating the inherited relationships of their parents) have been removed.

"Data" branch
  - All "Data" concepts now organised into 4 sub-concepts:
   - "Core data" - Data that typically are the primary input or output of a tool or which correspond to entries from the primary (_e.g._ sequence or structural) biological databases.
   - "Identifier" - A short numerical or textual label that identifies (typically uniquely) something such as data, a resource or a biological entity.
   - "Parameter" - Typically a simple numerical or string value that controls the operation of a tool.
   - "Report" - A human-readable collection of information that is distinct from primary (_e.g._ sequence or structural) biological data, including free text, annotation about biological entities and phenomena, computer-generated reports of analysis of primary data and metadata.
   - "Report" concepts for sequences correspond better (without duplicating) established sequence feature keys.

"Operation" branch
   - Fewer concepts, simpler is\_a hierarchy
   - "has\_input" and "has\_input" relations defined (on nearly all terms)

"Format" branch
   - "is\_format\_of" relations defined (for nearly all terms)

"Topic" branch
   - Improved term names and is_a hierarchy, reflecting whether topics concern a type of data, operation or are more general. 
   - New "Biological data resources" sub-branch includes common data resource concepts.
   - Major revision! Too much to mention, so take a look :)





# EDAM\_beta12.obo
General changes
   - OBO subset definitions added
   - Sub-ontologies / namespaces / subsets now are "topic", "data", "format", "identifier", "operation"
   - Relation types now are "in\_topic", "has\_input", "has\_output", "is\_format\_of", "is\_identifier\_of"
   - Many edits (to concepts and "is\_a" relations) to improve navigability in all sub-ontologies

New "Identifier" sub-ontology
   - Containing concepts which were under Data<-Identifier
   - For fine-grained annotation of identifiers of data

"Resource" sub-ontology obsoleted 
   - Most concepts merged into "Topic" sub-ontology (see below)
   - All remaining concepts in "resource" namespace obsoleted

Major revisions to "Topic" sub-ontology
   - Concepts redefined as "...general bioinformatics subject or category, such as a field of study, data, processing, analysis or technology."
   - For coarse-grained annotation of diverse resources
   - Subsumes concepts from old "resource" sub-ontology (see above)

EDAM-specific relations
   - Many new relations added (most term statements which should define relations now do)
   - Relations defined on parent only (not duplicated in children)

"Format" sub-ontology
   - About 50 new formats added





# EDAM\_beta11.obo
- Entire "Entity" branch (all terms) made obsolete

- Root term of "resource" namespace ("Data resource") renamed to "Resource"

- Root term of "format" namespace ("Data format") renamed to "Format"

- Corrections (2) removing duplicate IDs





# EDAM\_beta10.obo
Major revision of "Operation" branch 
  - immensely simplified top level
  - better hierarchy

Major revision of "Data" branch 
  - simpler top-level 
  - better hierarchy
  - new branches for "Protein data", "Nucleic acid data"
  - new terms to aid navigation
  - clean up "annotation" and "metadata" concepts

Major revision of "Data format" branch
  - better hierarchy
  - children of "HTML format" are now (mostly) obsolete
  - many new formats added

Simplification of "Topic" branch
  - concepts are now more strictly "fields of study"

General changes
  - term relations are now defined in one direction only
  - more consistent usage of words in term names
  - more intuitive term names (child names follow parent in style where possible)
  - many term additions and deletions