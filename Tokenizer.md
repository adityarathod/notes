# Tokenizer
#wiki #cs3377 
In **programming**, a **tokenizer** splits a string into individual tokens that make sense for the given [[Formal Language Theory#Formal Languages|formal language]]. **Tokenization** is also formally called **lexical analysis**. 

Tokenization is usually performed by writing a series of [[Regular Expression|regular expressions]]. Some tokenizers also provide metadata on the particular token.

> **Note**: Lexical analysis does not evaluate the order or the correctness of what it sees. A tokenizer only matches tokens and returns them.

## Simple Tokens vs. Complex Tokens
**Simple** tokens are tokens that require no other information except the class of token.

**Complex** tokens require additional processing or meta-information.