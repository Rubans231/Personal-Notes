
2025-09-12 05:52

Status:

Tags: [[machine learning]] [[coding]] [[learning]] [[python]] 




# To remember in Pandas

- always use **`pd.set_option('display.max_columns',100)`** as a good practice to always show all available columns so I could pick out the ones i do want
- To slice a certain number of columns from a dataframe, you should use `df[[]]` since the interior brackets are for list and the outside brackets are indexing operator. If you use a single bracket you get a series and you get a dataframe if you use double brackets 
- Best to convert all words to lowercase to avoid duplicates (crimes and Crimes would be examples of such duplicates) 
- If there are names, remove spaces and make each name into one singular token respectively to normalize(could in theory just use with the spaces but this is more efficient and is a good practice)
- df.iterrows returns a copy of the rows and thus does not make any changes to the original df
- `rake_nltk` is a really good natural language toolkit used for extracting significant keywords in the entirety of available text(keybert is a good alternative)
- use `inplace=True` if you wanna edit the original dataframe for example
	- `df.drop('A', inplace = True)` 

### sklearn count

- `fit_transform()` performs both of these operations sequentially:
    - It first calls `fit()` to learn the vocabulary from the input text.
    - Then, it immediately calls `transform()` to convert the same input text into the document-term matrix using the newly learned vocabulary.




# References