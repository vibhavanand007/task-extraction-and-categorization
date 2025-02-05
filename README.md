# Task Extraction and Categorization from Unstructured Text

## Objective:
The objective of this project is to create an NLP pipeline that can identify and categorize tasks from unstructured text. The program extracts actionable tasks, identifies who is responsible for performing them, and when the tasks should be completed if such information is provided.

This solution uses heuristic-based NLP techniques to detect tasks and categorize them into meaningful groups. The pipeline includes text preprocessing, task extraction, entity recognition, and categorization of tasks based on predefined keywords and deadlines.

## Steps Followed:
1. **Preprocessing**: 
   - Cleaned the text by removing stop words, punctuation, and irrelevant metadata.
   - Tokenized the text into sentences and performed POS tagging to identify actionable verbs.

2. **Task Identification**:
   - Developed heuristics to detect sentences that likely represent tasks.
   - Tasks were identified using imperative verbs and deadline mentions.

3. **Task Categorization**:
   - Categorized tasks into useful predefined categories such as:
     - Shopping
     - Work/Study
     - Household Chores
     - Meetings/Appointments
   - Used a simple keyword-based approach for categorization and additional techniques like BERT embeddings for task clustering.
   
4. **Output**:
   - A structured list of tasks was generated, including information about who is responsible and when the task should be completed.

## Structure of the Code:
The code is divided into the following key functions:
- **Preprocessing Function**: Cleans and prepares the text for analysis.
- **Task Extraction Function**: Identifies sentences that represent tasks based on heuristics.
- **Categorization Function**: Categorizes tasks into predefined categories using keywords and deadlines.
- **Testing and Validation**: Validates the results with a small, manually curated sample.

### Technologies Used:
- Python
- NLTK for text processing and POS tagging
- SpaCy for Named Entity Recognition (NER)
- Pandas for organizing output
- BERT/Word2Vec (optional for advanced categorization)
- Regular expressions for text pattern matching

## Insights/Challenges

### Challenges Faced:
- **Handling Ambiguous Sentences**:  
  One of the challenges encountered was handling ambiguous sentences where tasks were implied but not explicitly stated. For example, sentences like "He needs to attend the call later" or "The room needs cleaning" could not be easily identified as tasks without additional context or clarification.

- **Extracting "Who" and "When" Information**:  
  Extracting the entity (who) performing the task and the deadline (when) posed challenges in complex sentences, particularly when these details were implied or not directly stated. For example, "She should review the report by Friday" vs "Review the report" without specifying a subject.

- **Categorizing Tasks Without Clear Deadlines**:  
  Some tasks did not have deadlines or were ambiguous about the timeframe, making it difficult to categorize them accurately. For instance, the task "Buy groceries" doesn’t specify when or if it is time-sensitive, and thus, was harder to categorize into a specific action.

### Future Improvements:
- **Implement Advanced Techniques for "Who" Extraction**:  
  One possible future improvement is the use of Named Entity Recognition (NER) and dependency parsing to extract the "who" more accurately in sentences where the subject is implied or complex.

- **Dynamic Category Expansion with Topic Modeling**:  
  Currently, tasks are categorized based on predefined keyword categories. To enhance this, dynamic categorization could be implemented using techniques like Latent Dirichlet Allocation (LDA) to generate categories based on task context and grouping.

- **Machine Learning Models for Robust Task Extraction**:  
  Incorporating machine learning models, especially supervised learning techniques, could help automate the task extraction process and improve accuracy by training models on manually curated data, as well as improve the identification of tasks with more contextual complexity.
