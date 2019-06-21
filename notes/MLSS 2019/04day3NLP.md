
2019, July 19

An Introduction to Natural Language Processing
by Lawrence Carin

- has not quite yet met the level of human performance.  But improving very quickly
- What is NLP
	- Analysis of text and synthesis of text to make decisions or come to recommendations
	- e.g. sentiment analysis can be used to quickly understand free text replies in a survey
	- other examples include:  Translation, synthesis
	- how does this work?
		- it's not a binary classification problem (logistic regression)
		- the fundamental problem is that logistic regression works on numbers.  However, in sentiment analysis we are working with words (i.e. they are not numbers)
		- logistic regression cannot be directly applied to sentiment analysis
		- So we convert the words into numbers
			- count the number of times each word appears (bag of words)
- **Emeddings** or **Word to Vector**
	- this is a fundamental change in the NLP community
	- similarity based on proximity
	- map each word to a point in space
	- `word2vec` can look up each word and map it to a point in space (2 dimentional embeddings)
	- BTW, **topic models** have been superseded by the state of the art
	- google has already embedded the words for us
	- **every word** in the dictionary **is mapped to** an M dimensional **vector** (typically m = 300)
			- "why 300?  because it just works" -- says the neural network people
		- this is a total hack b/c machine learning works on numbers
		- softmax is about **predicting words**
		- **neural text model** = input is word vector ; output is probability of next word
		- **CBOW** continuous bag of words = 2 words before and 2 words after, [softmax] predict the word
		- each dimmension (m) in the multi-dimentional model is roughly analougous to a topic model map
		- 
---
part ii
---
big changes that occur after 2004:  (a) **digital text corpora** and (b)  **GPU**	
**recurrent neural networks** RNN
input is a vector ; mapped through a matrix (yields h) ; h is the input to softmax
but this is **too simple** 
	so **LSTM** (long-short term memory)
	augment memory with a **"memory cell"** (to be able to remembe things that happen further in the past.) (plus a hidden vector)
	memor cell is Cn
	distinguish h from c (c has long term memory) (h has exponential decay)
	here let's introuduce **gate (or gating) netoworks**
	there are three gates:  input, output, and "forget gate"
	plus a memory cell c ~ n
	so then we turn off components of memory (forgetting some stuff) and add (inject) some other memory
	turn off memory for each component of the memory
	do the same thing for the input:   take new memory and multpy by the forget gate
	we hvae now gone from one neural tetwork to four neural networks
	
---
Afternoon
---
### Case Study

NLP in practice  by dinhan shen

-- example is "spoken dialogue systems"

Challenges
- billions of users
- privacy of user data
- fast computation and memory efficeient
- 
	
