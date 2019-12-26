# Description of the data and data-modelling

## 1. [KEGG](https://www.genome.jp/kegg)

### Environ

> KEGG ENVIRON is a collection of crude drugs, essential oils, and other health-promoting substances, which are mostly natural products of plants.

So far we have KEGG parser which returns data form environ and got basic parser for any kegg object but need to be extendet and more cases should be added
Got list parser for environ and brite list parsers for few categories ---> Q: Can the list parser can be made universal, configurable or should I repeat the code for each brite category... most of the stuff are the same
As data we got: 
* medicinal herbs with major components (not in the csv)
* toxins
* cancerogoens
* endoDiruptiveCompounds
* pesticides

Cancerogens, toxins, all the chemical compounds names should be cleaned somehow because of the name complexity

### Compounds

>As a related resource, the KEGG COMPOUND database contains environmental pollutants and other health-damagine substances.

* Cancerogens
* Pesticides
* Toxins
* Endocrine disruptive compounds

## 2. [MeSH](https://www.ncbi.nlm.nih.gov/mesh)

### Maps as JSON

* DescriptorUI ----> DescriptorName
* DescriptorName ----> TreeNumberList, DescriptorUI
* MeSH Tree map - the tree structure of the MeSH tree with DescriptorUI at each branch/leaf

Some of the entries, take for example "tea" in the medicinal herbs, are so broad as term that brings thousands of other entries which are far from related to herbs and medicinal herbs. So they should be excluded.

Excluded entries:
* Hebrs
    * Tea
    * Senna

Added entries:
* Herbs
    * Tea Tree Oil
    * Senna Plant

In question:
* Herbs
    * Iceland moss: drags large list of fungi which may or may not be related to medicinal herbs

### Logic

* Obtain all the entries including nested with related terms/synonyms at particular branch
* Search the tree for given path (tree number)

### Working with CSV files

* Proper tools for reading and writing CSV files using streams
* CLI tools

### Research on data sanitation

* What are the specifics for cleaning the data
* Remove empty lines?
* remove quotes, headers?

### Research on parsing

* Found some books on parsing


