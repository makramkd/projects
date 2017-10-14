# Projects

This document outlines the various projects I have completed throughout the last
couple of years, with links to the source code where applicable.

I have been fortunate enough to work on things in very different areas of computer
science:

* Compilers and interpreters: by far my favorite topic, in close tandem with
the theory of programming languages.
* Numerical computing: a topic that is overlooked but has many insights onto the
limits of computing and techniques in high performance computing.
* Machine learning: the study of techniques on data to perform a particular task.
Extremely general and powerful, but also very difficult to master.
* Metaprogramming: a type of programming that generates programs, rather than
machine code. Also called compile-time computation.

## Machine Learning Projects

I only took two machine learning classes in university, which was a shame, but I
ended up learning a lot about this deep field of knowledge, which turned out to
still be a speck of a speck of what machine learning is today.

### Tweet Sentiment Analysis

Language: Python 2.7
Date: February 2016

This was the first machine learning project I completed, and I worked on this with
a friend who was taking the class with me as a partner. We:

* Extracted feature information from a corpus of 1.6 million tweets in order to
assess the underlying sentiment of a tweet, i.e happy or sad. 
* Used sequential minimal optimization support vector machines, C4.5 Decision Trees, 
and Naive Bayes classifiers in order to do so, leveraging the WEKA machine 
learning toolkit.

This project helped me learn the basics of data gathering, sanitation, and cleanup
so that it can actually get processed by machine learning algorithms. Although I
didn't implement any of the above algorithms, tuning the hyperparameters of them
was helpful to understanding how they work under the hood.

### Handwritten Digit Recognition

Language: Python 2.7
Date: February 2016

This project was part of an assignment that consisted of other questions on the
theory of machine learning. I:

* Classified handwritten digits using the k-nearest-neighbors and logistic 
regression classifiers, programmed in Python using NumPy. 
* Assessed the accuracy of both classifiers and wrote a report entailing 
the differences between the two and optimal settings of their parameters 
and hyperparameters.

In this project I actually implemented k-nearest-neighbors and logistic regression.
This was a good learning exercise, though of course the code was not in any
way the most optimal or efficient.

### Statistical Machine Translation Using IBM Model 1

Language: MATLAB
Date: March 2016

This was a very interesting project.

Statistical machine translation is the idea of using statistical models 
in order to translate between languages. Given a (ideally large) set of
translations between two languages, say English and French, we construct 
a statistical model of the languages and a translation model of how 
things are translated. The task given to me was to create a statistical 
machine translation model to translate French to English, given the 
Canadian Hansard proceedings, which are maintained in both English and French.

In order to do this, I used the IBM Model 1 machine translation model, 
which has two key ingredients: a language model for each language, and a 
translation model to translate between languages. The main task in the 
translation model is word alignment: given the translations from the 
Hansard proceedings, we want to try and figure out the French word that 
gives us the maximum probability that it is aligned to an English word. 
This procedure requires implementing the expectation-maximization algorithm 
for IBM Model 1, which achieves fairly decent accuracy in terms of unigram 
BLEU scores, given how much simplifying assumptions are made in the model.

Actually implementing the EM algorithm was a great learning experience. The
amount of pitfalls one can run into, as well as the types of optimizations one
can perform, one can never actually learn unless one actually implements it
by hand.

### Speaker Identification using Gaussian Mixture Models, Speech Recognition using Hidden Markov Models

Language: MATLAB
Date: April 2016

This was the final project of the natural language computing course I took
in the last semester of my bachelor's degree, and also by far the most
rewarding in terms of learning.

Speaker identification is the problem encountered when trying to identify, 
only from a recording of a person’s voice, who the speaker is, given 
previous voice recordings of that speaker. This task required me to 
translate a representation of the sound to a vector format common for 
audio called Mel-frequency cepstral coefficients, or MFCCs. I then used 
the idea of clustering the data of each speaker using a powerful probabilistic 
data model called a Gaussian mixture model. This involved implementing the 
expectation-maximization algorithm. Despite there being much detail to the 
procedure, the general idea is that in order to identify the speaker, 
we take the model that the voice sample belonged to with maximum likelihood, 
out of all models. This method achieved 80% accuracy of identification.

Speech recognition is the problem of recognizing what is being said; 
more specifically, what words were spoken. For this problem I leveraged 
the Bayes Net Toolbox and their hidden Markov model implementation, which 
was trained on speech data given by the instructor of the course. The performance 
was poor because of the simplicity of the model, where performance was analyzed 
using Levenshtein distance, which is a way to measure the difference between two sentences.

## Compilers and Interpreters

I regret that this section is actually smaller than the machine learning section,
but I have more textbooks on compilers than I do on any other topic (perhaps other
than philosophy).

### Pseudopascal Compiler

Language: Java
Date: January - May 2016

This project was the one I was looking forward to the most. Having implemented various
DSLs using compiler principles I learned in the Dragon book and others, I was itching to
build a compiler for a classroom programming language.

This language took inspiration mostly from Pascal but was not quite Pascal. However, it
was sufficient to learn the fundamentals of compiler construction from A to Z.

As the leader of a 4 person team - that eventually became 3 - I designed and implemented 
a compiler for a classroom programming language, as well as assigned and delegated necessary 
tasks to team members. The language includes the following constructs: 
lexical scope, functions and procedures, constant propagation, static typing, and terminal I/O. 

The most interesting aspects of this project for me was the LR parsing theory as well
as the code generator.

### Functional Shakespeare Interpreter

Language: Racket
Date: October 2015

Although a toy language, this was my first experience writing a nontrivial program in
the Racket dialect of Scheme. It was extremely fun and intellectually stimulating.

It was also required that we implement this interpreter in a pure manner - i.e no
side effects.

Implemented an interpreter for a programming language called Functional Shakespeare, 
which is fashioned after Shakespearean plays. It includes variables, function calls, 
and implicit if statements. The program that implemented it was completely pure - i.e free of any side effects.

## Numerical Computing

I finished various projects on numerical computing, which is quite an interesting field
on it's own.

### Numerical Algorithms Collection

I wrote my own implementation of various numerical algorithms. They are:

* Numerical integration algorithms, specifically three of them, which you can find
the implementation of [here](https://github.com/makramkd/numerical-integration).
* Gaussian elimination algorithms. Implemented for a class, did it in templated C++,
and made use of `enable_if`: [here](https://github.com/makramkd/gaussian-elimination).
* QR Decomposition. The QR decomposition algorithm is essential to finding an orthonormal
basis of a vector space numerically. The implementation is [here](https://github.com/makramkd/qr-decomposition).
* Root finding algorithms of various shapes and forms. I was always interested in how
root finding was done numerically (algebraically it is obviously different). Code is [here](https://github.com/makramkd/root-finding).

## Metaprogramming

Although this is a space I am still an amateur in, I am still very much interested in
metaprogramming, especially in C++. [Here](https://github.com/makramkd/metaprogramming-cpp) is
where I implement some of the common metaprogramming constructs in C++ on my own.
