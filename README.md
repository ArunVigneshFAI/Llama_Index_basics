# Llama_Index_basics
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
