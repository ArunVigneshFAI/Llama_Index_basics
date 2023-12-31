# Llama_Index_basics

![image](https://github.com/ArunVigneshFAI/Llama_Index_basics/assets/141916176/829ce30e-6bd0-4b59-abd5-d190a654965f)

![image](https://github.com/ArunVigneshFAI/Llama_Index_basics/assets/141916176/e4c4af2a-6507-4bcf-85a2-a903f4b5a322)

The general usage pattern of LlamaIndex is as follows:

1. Load in documents (either manually, or through a data loader)

2. Parse the Documents into Nodes

3. Construct Index (from Nodes or Documents)

4. [Optional, Advanced] Building indices on top of other indices

5. Query the index

## 1. Load in Documents
In the initial phase, data loading takes place. The data is presented in the form of Document objects. A range of data loaders is at the users' disposal, accessible through the 'load_data' function.

A Document serves as a streamlined container encasing the data source. At this point, the user has the option to continue with either of the subsequent actions:
1) Feed the Document object directly into the index (see section 3).

2) First convert the Document into Node objects (see section 2).

## 2. Parse the Documents into Nodes
Moving forward, the subsequent phase involves the conversion of these Document objects into Node objects. Nodes serve as discrete sections of source Documents, encompassing various forms such as text fragments or images. In addition to content, they encompass metadata and connections to other nodes and index frameworks.

Nodes are accorded primary importance within the LlamaIndex context. Users are granted the flexibility to define Nodes and their associated characteristics directly. Alternatively, they have the option to utilize NodeParser classes to "parse" source Documents into Nodes.

## 3. Index Construction
An index can now be constructed utilizing the available Document objects. The most straightforward concept involves integrating the Document objects upon index initialization.

The function 'from_documents' also features an optional parameter named 'show_progress'. By setting it to 'True', users can opt to view a progress bar while the index is being built.

Moreover, the option exists to create an index using a group of Node objects directly. Depending on the chosen index approach, LlamaIndex might employ LLM (Large Language Model) calls to facilitate the index construction process.

## 4. [Optional, Advanced] Building indices on top of other indices
The capability exists to construct indices atop existing indices. This compositional approach empowers users to effectively index diverse data sources. LlamaIndex introduces the concept of index composability, enabling the creation of indices built upon pre-existing indices. This feature proves advantageous in comprehensively indexing an entire document hierarchy, facilitating the provision of tailored knowledge to GPT.

Composability provides the means to establish more detailed indices for individual documents, as well as more comprehensive indices covering a range of documents.

## 5. Query the index
Following the index construction process, users gain the ability to perform queries using a QueryEngine. It's important to recognize that a "query" essentially constitutes an input to a Large Language Model (LLM). Consequently, the index serves a purpose beyond just answering questions; it can be employed for various other tasks as well.
