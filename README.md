# STOCK-SENTIMENT-ANALYSIS
The provided code conducts sentiment analysis on stock-related news headlines using a Random Forest classifier. Here's a summary of the key steps in the code:

1. **Data Loading:**
   The code loads stock-related data from a CSV file into a DataFrame, encoding it with 'ISO-8859-1'.

2. **Train-Test Split:**
   The data is split into training and testing sets based on the date. Training data consists of dates before '20150101', while testing data includes dates after '20141231'.

3. **Text Preprocessing:**
   - **Selecting Relevant Columns:** Columns 2 to 26 are selected, which likely contain textual information.
   - **Removing Punctuations:** Non-alphabetic characters are removed from the selected text columns using regular expressions.
   - **Lowercasing:** All text is converted to lowercase for uniformity.

4. **Creating Headlines:**
   For each row in the training set, headlines are constructed by joining the cleaned text from columns '0' to '24' into a single paragraph.

5. **Feature Extraction (Vectorization):**
   The CountVectorizer from scikit-learn is employed to convert the paragraphs into a matrix of token counts. It considers bigrams (n-grams of size 2) during this process.

6. **Random Forest Classification:**
   A Random Forest classifier with 200 trees and entropy as the criterion is initialized and trained using the training dataset.

7. **Testing and Evaluation:**
   - The text in the testing set is preprocessed similarly to the training set.
   - The test set is transformed using the same CountVectorizer as the training set.
   - Predictions are made using the trained Random Forest classifier.
   - Evaluation metrics, including a confusion matrix, accuracy, and a classification report, are generated to assess the model's performance.

In summary, the code preprocesses the text data by removing punctuations and converting it to lowercase. It then constructs paragraphs from the cleaned text, applies feature extraction using CountVectorizer to convert the text into numerical features, and employs a Random Forest classifier for sentiment analysis. The model's performance is evaluated on the testing set using standard classification metrics.
