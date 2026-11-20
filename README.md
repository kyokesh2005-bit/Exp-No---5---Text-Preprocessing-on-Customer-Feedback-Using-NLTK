Aim:

To perform tokenization, stopword removal, and lemmatization on customer feedback text using the NLTK library for text preprocessing.

Algorithm:

1. Import Libraries – Import nltk and its modules: word_tokenize, stopwords, and WordNetLemmatizer.
2. Download Resources – Use nltk.download() to get required datasets (punkt, stopwords, wordnet).
3. Input Text – Define a sample customer feedback paragraph.
4. Tokenization – Split text into individual words using word_tokenize().
5. Stopword Removal – Remove common words like the, is, and, in using NLTK's English stopword list.
6. Lemmatization – Convert words to their base form using WordNetLemmatizer.
7. Display Results – Print original text, tokens, filtered words, and lemmatized words.
   
Program:

# Text Preprocessing: Tokenization, Stopword Removal,
# and Lemmatization using NLTK

import nltk

from nltk.corpus import stopwords

from nltk.tokenize import word_tokenize

from nltk.stem import WordNetLemmatizer

# Step 1: Download NLTK resources

nltk.download('punkt')

nltk.download('stopwords')

nltk.download('wordnet')

# Step 2: Sample customer feedback text

text = """The product quality is excellent and the delivery
service was very fast.

However, the packaging could have been better."""

print("---- Original Text ----")

print(text)

# Step 3: Tokenization

tokens = word_tokenize(text)

print("\nTokenized Words:")

print(tokens)

# Step 4: Stopword Removal

stop_words = set(stopwords.words('english'))

filtered_tokens = [word for word in tokens
                   if word.lower() not in stop_words
                   and word.isalpha()]

print("\nAfter Stopword Removal:")

print(filtered_tokens)

# Step 5: Lemmatization

lemmatizer = WordNetLemmatizer()

lemmatized_words = [
    lemmatizer.lemmatize(word.lower())
    for word in filtered_tokens
]

print("\nAfter Lemmatization:")

print(lemmatized_words)

output

[nltk_data] Downloading package punkt to /root/nltk_data...
[nltk_data]   Package punkt is already up-to-date!
[nltk_data] Downloading package punkt_tab to /root/nltk_data...
[nltk_data]   Unzipping tokenizers/punkt_tab.zip.
[nltk_data] Downloading package stopwords to /root/nltk_data...
[nltk_data]   Package stopwords is already up-to-date!
[nltk_data] Downloading package wordnet to /root/nltk_data...
[nltk_data]   Package wordnet is already up-to-date!
---- Original Text ----
The product quality is excellent and the delivery
service was very fast.

However, the packaging could have been better.

Tokenized Words:
['The', 'product', 'quality', 'is', 'excellent', 'and', 'the', 'delivery', 'service', 'was', 'very', 'fast', '.', 'However', ',', 'the', 'packaging', 'could', 'have', 'been', 'better', '.']

After Stopword Removal:
['product', 'quality', 'excellent', 'delivery', 'service', 'fast', 'However', 'packaging', 'could', 'better']

After Lemmatization:
['product', 'quality', 'excellent', 'delivery', 'service', 'fast', 'however', 'packaging', 'could', 'better']


Result:

The program successfully performed the essential text preprocessing steps on the customer feedback paragraph using the NLTK library.

