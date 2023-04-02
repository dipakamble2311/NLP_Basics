
# Basic Pre processing of Text Data

Natural Langauge processing is branch of DATA SCIENCE which deals with Text Data.

NLP is mandatory for follwing application :
   
    Sentiment Analysis

    Named Entity Recognition

    Machine Translation

    Text Summarization

    Chatbots and Virtual Assistants 

# Basic steps for pre- processing 
## importing libraries
    import nltk
    from nltk.tokenize import word_tokenize,sent_tokenize,WhitespaceTokenizer
    from nltk.stem import WordNetLemmatizer,LancasterStemmer
    from nltk.corpus import stopwords
    from string import punctuation
    from unidecode import unidecode
## Tokenization
### sentence tokenization
    sent = sent_tokenize(text_data)
### word tokenization
    tokens = word_tokenize(text_data)
### whitespace tokenization
    tokens = WhitespaceTokenizer().tokenize(text_data)
### Normalization
    lower_text = [word.lower() for word in tokens]

### Remove punctuations
    text_without_punct = [word for word in lower_text if word not in punctuation]
### Remove stopwords
    stopword_list = stopwords.words('english')

### contractions
    import contractions

    text = '''Hello mom! Yes, I'm fine. How're you? No, I didn't have lunch. I'm about to go.
    Are you coming next weekend? I've been missing you.'''
 
    expanded_text = []   
    for word in text.split():
    expanded_text.append(contractions.fix(word))  
   
    expanded_text = ' '.join(expanded_text)
    print('Input : ' + text)
    print('\n')
    print('Output: ' + expanded_text)

### stemming and lemmatizer
    stemming = LancasterStemmer()
    lemmatizer = WordNetLemmatizer()
    for word in text_without_stop:
    stemmed_word = stemming.stem(word)
    lemmatized_word = lemmatizer.lemmatize(word)
    print(f'Original word >> {word}')
    print(f'stemmed_word >> {stemmed_word}')
    print(f'lemmatized_word >> {lemmatized_word}')
    print('*'*100)
### Handling accented characters
    accented_character = "á, À, ä, Å, É"
    fixed_words = unidecode(accented_character)
### Langauge Translation
    from textblob import TextBlob
    a = 'mussage'
    b = TextBlob(a)
    print(b.correct())
### Auto correct
    from autocorrect import Speller
    spell = Speller(lang='en')
    print(spell('mussage'))
    print(spell('survice'))
    
