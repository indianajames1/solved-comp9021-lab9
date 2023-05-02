Download Link: https://assignmentchef.com/product/solved-comp9021-lab9
<br>






<h1>1           R Using a stack to evaluate fully parenthesised expressions</h1>

Modify the program postfix.py from the 9th lecture to a program fully_parenthesised.py so that a stack is used to evaluate an arithmetic expression written in infix, fully parenthesised, and built from natural numbers using the binary +, -, * and / operators. <em>Fully parenthesised </em>means that all expressions of the form e + e’, e – e’, e * e’ and e / e’ are surrounded by a pair of parentheses, brackets or braces. Of course a simple solution would be to replace all brackets and braces by parentheses and call eval(), but here we want to use a stack.

Hint: think of popping when and only when a closing parenthesis, bracket or brace is being processed.

Next is a possible interaction.

$ python3 …

&gt;&gt;&gt; from fully_parenthesised import *

&gt;&gt;&gt; evaluate(’100’)

100

&gt;&gt;&gt; evaluate(’[(1 – 20) + 300]’)

281

&gt;&gt;&gt; evaluate(’[1 – {20 + 300}]’)

-319

&gt;&gt;&gt; evaluate(’( { 20*4 }/5 )’)

16.0

&gt;&gt;&gt; evaluate(’(20*[4/5])’)

16.0

&gt;&gt;&gt; evaluate(’({1 + (20 * 30)} – [400 / 500])’)

600.2

&gt;&gt;&gt; evaluate(’{1 + [((20*30)-400) / 500]}’)

1.4

&gt;&gt;&gt; evaluate(’[1 + {(2 * (3+{4*5})) / ([6*7]-[8/9]) }]’)

2.1189189189189186

&gt;&gt;&gt; evaluate(’100 + 3’)

&gt;&gt;&gt; evaluate(’(100 + 3’)

&gt;&gt;&gt; evaluate(’(100 + -3)’)

&gt;&gt;&gt; evaluate(’(100 50)’)

&gt;&gt;&gt; evaluate(’(100 / 0)’)

<h1>2           R Word ladders</h1>

Write a program word_ladders.py that computes all transformations of a word word_1 into a word word_2, consisting of sequences of words of minimal length, starting with word_1, ending in word_2, and such that two consecutive words in the sequence differ by at most one letter. All words have to occur in a dictionary with name dictionary.txt, stored in the working directory.

It is convenient and effective to first create a dictionary whose keys are all words in the dictionary with one letter replaced by a “slot”, the value for a given key being the list of words that match the key with the “slot” being replaced by an appropriate letter. From this dictionary, one can then build a dictionary with words as keys, and as value for a given key the list of words that differ in only one letter from the key.

The program implements a function word_ladder(word_1, word_2) that returns the list of all solutions, a solution being as previously described.

Next is a possible interaction.

$ python3 …

&gt;&gt;&gt; from word_ladder import *

&gt;&gt;&gt; for ladder in word_ladder(’cold’, ’warm’): print(ladder) …

[’COLD’, ’CORD’, ’WORD’, ’WORM’, ’WARM’]

[’COLD’, ’CORD’, ’WORD’, ’WARD’, ’WARM’]

[’COLD’, ’CORD’, ’CARD’, ’WARD’, ’WARM’]

&gt;&gt;&gt; for ladder in word_ladder(’three’, ’seven’): print(ladder) …

[’THREE’, ’THREW’, ’SHREW’, ’SHRED’, ’SIRED’, ’SITED’, ’SATED’, ’SAVED’, ’SAVER’, ’SEVER’, ’SEVEN’]

&gt;&gt;&gt; for ladder in word_ladder(’train’, ’bikes’): print(ladder) …

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’BROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’COKES’, ’CAKES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’BROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’COKES’, ’POKES’, ’PIKES’, ’BIKES’]

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’BROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’CARES’, ’CAKES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’BROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’CARES’, ’BARES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’BROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’BORES’, ’BARES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’BROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’PORES’, ’POKES’, ’PIKES’, ’BIKES’]

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’COKES’, ’CAKES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’COKES’, ’POKES’, ’PIKES’, ’BIKES’]

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’CARES’, ’CAKES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’CARES’, ’BARES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’BORES’, ’BARES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’BRAIN’, ’BRAWN’, ’BROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’PORES’, ’POKES’, ’PIKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’GROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’COKES’, ’CAKES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’GROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’COKES’, ’POKES’, ’PIKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’GROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’CARES’, ’CAKES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’GROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’CARES’, ’BARES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’GROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’BORES’, ’BARES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’GROWS’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’PORES’, ’POKES’, ’PIKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’COKES’, ’CAKES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’COKES’, ’POKES’, ’PIKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’CARES’, ’CAKES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’CARES’, ’BARES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’BORES’, ’BARES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’GRAIN’, ’GROIN’, ’GROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’PORES’, ’POKES’, ’PIKES’, ’BIKES’]

[’TRAIN’, ’DRAIN’, ’DRAWN’, ’DROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’COKES’, ’CAKES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’DRAIN’, ’DRAWN’, ’DROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’COKES’, ’POKES’, ’PIKES’, ’BIKES’]

[’TRAIN’, ’DRAIN’, ’DRAWN’, ’DROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’CARES’, ’CAKES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’DRAIN’, ’DRAWN’, ’DROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’CARES’, ’BARES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’DRAIN’, ’DRAWN’, ’DROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’BORES’, ’BARES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’DRAIN’, ’DRAWN’, ’DROWN’, ’CROWN’, ’CROWS’, ’CROPS’, ’COOPS’, ’CORPS’, ’CORES’, ’PORES’, ’POKES’, ’PIKES’, ’BIKES’]

[’TRAIN’, ’DRAIN’, ’DRAWN’, ’DRAWS’, ’DRAGS’, ’BRAGS’, ’BRATS’, ’BEATS’, ’BESTS’, ’BUSTS’, ’BUSES’, ’BASES’, ’BAKES’, ’BIKES’]

[’TRAIN’, ’DRAIN’, ’DRAWN’, ’DRAWS’, ’DRAGS’, ’BRAGS’, ’BRATS’, ’BEATS’, ’BELTS’, ’BELLS’, ’BALLS’, ’BALES’, ’BAKES’, ’BIKES’]

<h1>3                    Using linked lists to represent polynomials (optional)</h1>

Extend the program polynomial.py that implements a class Polynomial from the previous lab to implement the functions __add__(), __sub__(), __mul__() and __truediv__().

Next is a possible interaction.

$ python3 …

&gt;&gt;&gt; from polynomial import *

&gt;&gt;&gt; poly_6 = Polynomial(’-2x + 7x^3 +x                                            – 0 + 2 -x^3 + x^23 – 12x^8 + 45 x ^ 6 -x^47’)

&gt;&gt;&gt; print(poly_6)

-x^47 + x^23 – 12x^8 + 45x^6 + 6x^3 – x + 2

&gt;&gt;&gt; poly_7 = Polynomial(’2x^5 – 71x^3 + 8x^2 – 93x^4 -6x + 192’)

&gt;&gt;&gt; poly_8 = Polynomial(’192 -71x^3 + 8x^2 + 2x^5 -6x – 93x^4’)

&gt;&gt;&gt; poly_9 = poly_7 + poly_8

&gt;&gt;&gt; print(poly_7)

2x^5 – 93x^4 – 71x^3 + 8x^2 – 6x + 192

&gt;&gt;&gt; print(poly_8)

2x^5 – 93x^4 – 71x^3 + 8x^2 – 6x + 192

&gt;&gt;&gt; print(poly_9)

4x^5 – 186x^4 – 142x^3 + 16x^2 – 12x + 384

&gt;&gt;&gt; print(poly_7 * poly_7)

4x^10 – 372x^9 + 8365x^8 + 13238x^7 + 3529x^6 + 748x^5 – 34796x^4 – 27360x^3 + 3108x^2

– 2304x + 36864

&gt;&gt;&gt; print(poly_7)

2x^5 – 93x^4 – 71x^3 + 8x^2 – 6x + 192

&gt;&gt;&gt; print(poly_7 – poly_7)

0

&gt;&gt;&gt; print(poly_7)

2x^5 – 93x^4 – 71x^3 + 8x^2 – 6x + 192

&gt;&gt;&gt; print(poly_9 / poly_7)

2

&gt;&gt;&gt; print(poly_9)

4x^5 – 186x^4 – 142x^3 + 16x^2 – 12x + 384

&gt;&gt;&gt; print(poly_7)

2x^5 – 93x^4 – 71x^3 + 8x^2 – 6x + 192

&gt;&gt;&gt; poly_10 = Polynomial(’-11x^4 + 3x^2 + 7x + 9’)

&gt;&gt;&gt; poly_11 = Polynomial(’5x^2 -8x – 6’)

&gt;&gt;&gt; poly_12 = poly_10 * poly_11

&gt;&gt;&gt; print(poly_12)

-55x^6 + 88x^5 + 81x^4 + 11x^3 – 29x^2 – 114x – 54

&gt;&gt;&gt; print(poly_12 / poly_10)

5x^2 – 8x – 6

&gt;&gt;&gt; print(poly_12 / poly_11)

-11x^4 + 3x^2 + 7x + 9

&gt;&gt;&gt; poly_13 = poly_6 * poly_7

&gt;&gt;&gt; print(poly_13 / poly_6)

2x^5 – 93x^4 – 71x^3 + 8x^2 – 6x + 192

&gt;&gt;&gt; print(poly_13 / poly_7)

-x^47 + x^23 – 12x^8 + 45x^6 + 6x^3 – x + 2

<h1>4                    Context free grammars (advanced, optional)</h1>

A <em>context free </em>grammar is a set of <em>production rules </em>of the form

symbol_0 —&gt; symbol_1 … symbol_n

where symbol_0, …, symbol_n are either <em>terminal </em>or <em>nonterminal symbols</em>, with symbol_0 being necessarily nonterminal. A symbol is a nonterminal symbol iff it is denoted by a word built from underscores or uppercase letters. A special nonterminal symbol is called the <em>start symbol</em>. The language <em>generated </em>by the grammar is the set of sequences of terminal symbols obtained by replacing a nonterminal symbol by the sequence on the right hand side of a rule having that nonterminal symbol on the left hand side, starting with the start symbol. For instance, the following, where EXPRESSION is the start symbol, is a context free grammar for a set of arithmetic expressions.

EXPRESSION –&gt; EXPRESSION TERM_OPERATOR TERM

EXPRESSION –&gt; TERM

TERM –&gt; TERM FACTOR_OPERATOR FACTOR

TERM –&gt; FACTOR

FACTOR –&gt; NUMBER

FACTOR –&gt; (EXPRESSION)

NUMBER –&gt; DIGIT NUMBER

NUMBER –&gt; DIGIT

DIGIT –&gt; 0 …

DIGIT –&gt; 9

TERM_OPERATOR –&gt;


TERM_OPERATOR –&gt; FACTOR_OPERATOR –&gt; *

FACTOR_OPERATOR –&gt; /

Moreover, blank characters (spaces or tabs) can be inserted anywhere except inside a number. For instance, (2 + 3) * (10 – 2) – 12 * (1000 + 15) is an arithmetic expression generated by the grammar.

Note that operators associate to the left. The grammar is <em>unambiguous</em>, in the sense that every expression generated by the grammar has a unique evaluation.

Write down a program context_free_grammar.py that implements a function evaluate() which takes a string representing an expression as an argument, checks whether the expression can be generated by the grammar, and in case the answer is yes, returns the value of the expression, provided that no division by 0 is attempted; otherwise, the function returns None.

Next is a possible interaction.

$ python3 …

&gt;&gt;&gt; from context_free_grammar import *

&gt;&gt;&gt; evaluate(’100’)

100

&gt;&gt;&gt; evaluate(’(100)’)

100

&gt;&gt;&gt; evaluate(’1 – 20 + 300’)

281

&gt;&gt;&gt; evaluate(’(((((1))-((20))+((300)))))’)

281

&gt;&gt;&gt; evaluate(’20 * 4 / 5’)

16.0

&gt;&gt;&gt; evaluate(’(((((20))*((4))/((5)))))’)

16.0

&gt;&gt;&gt; evaluate(’1 + 20 * 30 – 400 / 500’)

600.2

&gt;&gt;&gt; evaluate(’1 + (20*30-400) / 500’)

1.4

&gt;&gt;&gt; evaluate(’1+(20 / 30 * 400)- 500’)

-232.33333333333337

&gt;&gt;&gt; evaluate(’1 + 2 * (3+4*5) / (6*7-8/9)’)

2.1189189189189186

&gt;&gt;&gt; evaluate(’100)’)

&gt;&gt;&gt; evaluate(’100 + ’)

&gt;&gt;&gt; evaluate(’100 + -3’)

&gt;&gt;&gt; evaluate(’100 œ 50’)

&gt;&gt;&gt; evaluate(’100 / 0’)

Before you tackle the exercise, find out about <em>recursive descent parsers</em>. To easily tokenise the string, check out the findall() function from the re module.