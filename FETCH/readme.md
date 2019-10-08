**Fetch Rewards Data Engineer Coding Challenge**

This challenge will focus on the similarity between two texts.  Your objective is to write a program that takes as inputs two file paths and uses a metric to determine how similar they are.  Documents that are exactly the same should get a score of 1, and documents that don&#39;t have any words in common should get a score of 0.

You will have to make a number of decisions as you develop this solution:

- Do you count punctuation or only words?

**The instructions do not specify if "similarity" refers to words themselves or the meaning of the words. In other words, two texts with no words in common could mean pretty much the same thing.**

**For the purpose of this challenge I am counting words and punctuation. In addition, I am converting  all text to the same case (lower) to minimize the impact of punctuation as well as same words not matching due to difference in lower vs upper case.**

- Which words should matter in the similarity comparison?

**I am comparing all words since I am not looking for meaning but similarity.**

- Do you care about the ordering of words?

**Yes, I am caring about the order of words because of the same reason, similarity in text but not necessarily in meaning.**

- What metric do you use to assign a numerical value to the similarity?

**I decide to use Mathematics to come up with a metric that could make sense. There is an extended number of research in this area. Different approaches exists that try to come up with ways to measure the similarity between two texts. Some of those are:**

1. [Hamming distance](http://en.wikipedia.org/wiki/Hamming_distance)
2. [Levenshtein distance](http://en.wikipedia.org/wiki/Levenshtein_distance)
3. [Damerau–Levenshtein distance](http://en.wikipedia.org/wiki/Damerau%E2%80%93Levenshtein_distance)
4. [Jaro–Winkler distance](http://en.wikipedia.org/wiki/Jaro%E2%80%93Winkler_distance)

**Some of these methods, as well as many others, have their own libraries created. You indicated below that only standard libraries could be used. For that reason, I am defining a function in Python while only using the _numpy_ library in Python.**

** Two identical texts will have a value of 1, two completely different texts will have a value of 0. Text with similarities will have a ratio of a number between 0 and 1. As an example, for text sample 1 and sample 2 my code provides a value of 0.8753541076487252. For text sample 1 and sample 3 the value is 0.4681404421326398. For sample 2 and 3 this value is 0.4589308996088657. We can easily convert those to percentage (%) if desired.**

- What type of data structures should be used?  (Hint: Dictionaries and lists are particularly helpful data structures that can be leveraged to calculate the similarity of two pieces of text.)

**I am using a matrix and vectors in memory to calculate the number of deletions, additions and substitutions needed to make two texts the same. Please see the Levenshtein distance link above to see the mathematical model.**

Requirements:

- The document similarity algorithm does not need to perform well, and you don&#39;t need to account for all edge cases.   **Focus on having some fun with it and producing code that we can discuss together.**
- Use the 3 sample texts provided below to develop your app.  Samples 1 and 2 should be more similar than samples 1 and 3.
- You may choose any language you like, but only standard libraries may be used (i.e., no sci-kit learn, nltk, spacy, etc. – that&#39;s cheating!).
- **The code, at a minimum, must run.**  Please provide clear instructions on how to run it.
- When complete, please upload your codebase to a public Git repo (GitHub, Bitbucket, etc.) and email us the link.  Please double-check this is publicly accessible.

Samples:

- **Sample 1**

_The easiest way to earn points with Fetch Rewards is to just shop for the products you already love. If you have any participating brands on your receipt, you&#39;ll get points based on the cost of the products. You don&#39;t need to clip any coupons or scan individual barcodes. Just scan each grocery receipt after you shop and we&#39;ll find the savings for you._

- **Sample 2**

_The easiest way to earn points with Fetch Rewards is to just shop for the items you already buy. If you have any eligible brands on your receipt, you will get points based on the total cost of the products. You do not need to cut out any coupons or scan individual UPCs. Just scan your receipt after you check out and we will find the savings for you._

- **Sample 3**

_We are always looking for opportunities for you to earn more points, which is why we also give you a selection of Special Offers. These Special Offers are opportunities to earn bonus points on top of the regular points you earn every time you purchase a participating brand. No need to pre-select these offers, we&#39;ll give you the points whether or not you knew about the offer. We just think it is easier that way._

Bonus Points:

- Package this application as a web service that performs the comparison in response to a POST request containing the two texts in the body of the payload.  You may use external libraries (i.e., flask).
- Let&#39;s take it a step further and package the web service in a Docker container that can be built and run locally or pulled down and run via Docker Hub.
