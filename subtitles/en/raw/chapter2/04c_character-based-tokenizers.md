Before diving in character-based tokenization, understanding why this kind of tokenization is interesting requires understanding the flaws of word-based tokenization. If you haven't seen the first video on word-based tokenization we recommend you check it out before looking at this video. Let's take a look at character-based tokenization. We now split our text into individual characters, rather than words. There are generally a lot of different words in languages, while the number of characters stays low. Here for example, for the English language that has an estimated 170,000 different words, we would need a very large vocabulary to encompass all words. With a character-based vocabulary, we can get by with only 256 characters! Even languages with a lot of different characters like the Chinese languages have dictionaries with ~20,000 different characters but more than 375,000 different words. Character-based vocabularies let us fewer different tokens than the word-based tokenization dictionaries we would otherwise use. These vocabularies are also more complete than their word-based vocabularies counterparts. As our vocabulary contains all characters used in a language, even words unseen during the tokenizer training can still be tokenized, so out-of-vocabulary tokens will be less frequent. This includes the ability to correctly tokenize misspelled words, rather than discarding them as unknown straight away. However, this algorithm isn't perfect either! Intuitively, characters do not hold as much information individually as a word would hold. For example, "Let's" holds more information than "l". Of course, this is not true for all languages, as some languages like ideogram-based languages have a lot of information held in single characters, but for others like roman-based languages, the model will have to make sense of multiple tokens at a time to get the information held in a single word. This leads to another issue with character-based tokenizers: their sequences are translated into very large amount of tokens to be processed by the model. This can have an impact on the size of the context the model will carry around, and will reduce the size of the text we can use as input for our model. This tokenization, while it has some issues, has seen some very good results in the past and should be considered when approaching a new problem as it solves some issues encountered in the word-based algorithm.