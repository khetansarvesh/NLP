These have similar architecture to what we used in MT, just change the dataset!! There are differnt types of summarizations.

# 1. <ins> Abstractive vs Extractive Summarization </ins>

### Extractive Summarization (no more used cause abstractive has become easy and norm nowadays)
- Given a document of 100 lines, you summarize it into 10 lines by just picking 10 lines out of the 100 ‘as it is’.
- This can be modeled as a binary classification problem i.e. for every sentence in 100 lines you need to classify it as ‘Yes’ or ‘No’ where Yes means to be included in the summary while No means not to be included into the summary

### Abstractive Summarization
- Here we dont copy paste, we understand the meaning of the 100 lines and then write 10 lines in your own words
- This is a NLG Task
- CNN Daily News Dataset can be used

# 2. <ins> Generic vs Query Based vs User Focused </ins>

### Generic 
- Summaries the entire document eg say you have a document of world war 1 and you want a summary of above document

### Query Based
- Say you have a document on world war 1 and you don't want the summary of entire document, instead you want a summary on only the causes of world war 1

### User Based
- Say you have a document on world war 1 and you want to generate a summary of entire document for a 5 yr old vs a historian

# 3. <ins> Based on Output Format </ins>
- Summaries in textual form (Paragraphs)
- Summaries in form of bullet points
- Summaries in form of table


# 4. <ins> Monolingual vs Cross-lingual Summarization </ins>

### Monolingual Summarization
- Say the document was in english and you need to summarize it in english

### Cross-lingual Summarization
- Say the document was in english and you need to summarize it in French


# 5. <ins> Single-Document Summarization vs Multi-Document Summarization </ins>
