# Description of the data and data-modelling

## 1. [KEGG](https://www.genome.jp/kegg)

### Environ

> KEGG ENVIRON is a collection of crude drugs, essential oils, and other health-promoting substances, which are mostly natural products of plants.

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

Problem with MeSH terms related to descriptor(heading) is that they include variations of the same phrase. Maybe this is a plus?!

### Logic

* Obtain all the entries including nested with related terms/synonyms at particular branch
* Search the tree from givven path (tree number)

### What should happend

1. Filter the kegg data from stop words, descriptive words: type of extract/extraction, variation of the entries with the same root, animal products promoting abusive behavior against animals
