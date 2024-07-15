## Financial Document Digitization
In the context of digitizing documents efficiently, this project aims to evaluate and implement Azure AI Document Intelligence tools. The goal is to assess the capabilities and performance of Azure's Document Recognition tool for processing documents. The project scope includes processing 20 documenmts to validate the tool's efficiency and accuracy.

## Approach
Azure AI Document Intelligence offers a diverse set of models, enabling us to integrate intelligent document processing into our apps and operations. We attempted to work on the following models using the generic architecture approach, among the numerous prebuilt and document analysis models available in Azure AI Document Intelligence.

## Architecture Diagram
![image](https://github.com/user-attachments/assets/8e317ca3-97f2-4ed4-be41-96676270caed)

## Suggested Approach 
While investigating the use of a bespoke neural model, we discovered that it could not entirely fulfill our criteria due to the variety of structures found in our documents. Because our documents' formats and layouts differed, the custom neural model struggled to consistently retrieve the appropriate information in all scenarios.

Following a thorough review of the available pre-trained models and custom-trained models, we propose using pretrained document analysis models. These pretrained models enable us to take advantage of pre-learned features and proven architectures, resulting in faster development and higher accuracy. This method takes advantage of the most recent advances in document analysis to ensure consistent performance while saving time and resources. We also propose that the layout model be adopted going forward, as it appears to produce the best results based on our review of the various models. 
The technique for retrieving results from the pre-trained layout model is as follows.

## Flow Diagram
![image](https://github.com/user-attachments/assets/fefc8808-6232-4e03-af2e-7dc53dc6cdfb)

## Results
We attempted to analyze the document using the layout model via an API call. Finally, we used post-processing code to extract fields and values from API responses. The findings of the 20 publications were merged, and the accuracy, precision, and recall of the model results were calculated.

Based on the results after post processing the accuracy metrics are as follows:
Average Precision	88.08%
Average Recall	81.87%
Average F1-Score	84.86%

