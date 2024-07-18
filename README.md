# **Financial Document Digitization**

## Table of Contents

1.[Introduction](#Introduction) 

2.[Solution Architecture](#SolutionArchitecture) 

3.[Tools/Models Used](#Tools/ModelsUsed) 

4.[Installation](#Installation) 

5.[Example](#Example) 

6.[Results](#Results) 

<a id="Introduction"></a>
## Introduction
In the context of digitizing documents efficiently, this project aims to evaluate and implement Azure AI Document Intelligence tools. The goal is to assess the capabilities and performance of Azure's Document Recognition tool for processing documents. The project scope includes processing 20 documenmts to validate the tool's efficiency and accuracy.

<a id="SolutionArchitecture"></a>
## Solution Architecture
Azure AI Document Intelligence is a package of services that helps to process and analyze documents more efficiently. It offers a diverse set of models, enabling us to integrate intelligent document processing into our apps and operations. Azure Form Recognizer is a service within Azure AI Document Intelligence that handles form processing. It uses complex machine learning models to automatically evaluate various types of forms and documents, extract key-value pairs, tables, and text, and then organize the results into structured data. We attempted to work on the following models using the generic architecture approach, among the numerous prebuilt and document analysis models available in Azure AI Document Intelligence.

### Architecture Diagram
![image](https://github.com/user-attachments/assets/8e317ca3-97f2-4ed4-be41-96676270caed)

<a id="Tools/ModelsUsed"></a>
## Tools/Models Used
### Azure Form Recognizer
Azure Form Recognizer is designed to be useful for a wide range of businesses and use cases where document processing and information extraction are crucial, providing powerful capabilities for automating and streamlining these operations effectively. It analyzes documents automatically, extracting text, key-value pairs, tables, and other structured data items. It recognizes the layout of documents, including headers, footers, tables, and data sections, in order to accurately extract information. We can train custom machine learning models to recognize document layouts and fields particular to specific companies, increasing the accuracy of specialized papers. It supports a wide range of documents, including invoices, receipts, purchase orders, insurance documents, tax forms, and more.

While investigating the use of a bespoke neural model, we discovered that it could not entirely fulfill our criteria due to the variety of structures found in our documents. Because our documents' formats and layouts differed, the custom neural model struggled to consistently retrieve the appropriate information in all scenarios.

### Layout Model in Azure Form Recognizer
The layout model is used to analyze documents in order to detect and extract structural features like text, tables, and other content regions while leaving out semantic meaning or key-value pairs. It focuses on comprehending a document's physical arrangement and spatial relationships. Detects and segments various parts on a page, such as headers, footers, body text, tables, and other graphical elements. Extracts text and other stuff from specified locations while retaining spatial layout and organization. 

<a id="Installation"></a>
## Installation
### Prerequisites
- Azure subscription with Form Recognizer service
- Python 3.x
- pip (Python package installer)

### Installation Steps

#### Step 1: Install Azure SDK for Python
```bash
pip install azure-ai-formrecognizer
```
#### Step 2: Run Jupyter Notebook
```bash
jupyter notebook
```

After running the command, your default web browser should open with the Jupyter Notebook interface.
Navigate to Formatted_API_Results_Extraction.ipynb file and click on it to open and run the notebook. After you get the API results now navigate to Formatted_Post_Processing. file and click on it to open and run the notebook


<a id="Example"></a>
## Example
![READ](https://github.com/user-attachments/assets/f5910a3f-4858-41c5-92da-fd751a256258)

<a id="Results"></a>
## Results
Following a thorough review of the available pre-trained models and custom-trained models, we propose using pretrained document analysis models. These pretrained models enable us to take advantage of pre-learned features and proven architectures, resulting in faster development and higher accuracy. This method takes advantage of the most recent advances in document analysis to ensure consistent performance while saving time and resources. We also propose that the layout model be adopted going forward, as it appears to produce the best results based on our review of the various models. 
The technique for retrieving results from the pre-trained layout model is as follows. We attempted to analyze the document using the layout model via an API call. Finally, we used post-processing code to extract fields and values from API responses. The findings of the 20 publications were merged, and the accuracy, precision, and recall of the model results were calculated.

Based on the results after post processing the accuracy metrics are as follows:
| Metric  | Value |
| ------------- | ------------- |
| Average Precision  | 88.08% |
| Average Recall  | 81.87% |
| Average F1-Score  | 84.86% |
