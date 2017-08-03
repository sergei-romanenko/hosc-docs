# HOSC: A Higher-Order Supercompiler in Scala

> This site is associated with the project <https://github.com/ilya-klyuchnikov/hosc>.

A [supercompiler](http://sites.google.com/site/keldyshscp/Home/supercompilerconcept)
is a program transformer that traces the possible 
generalized histories of computation by the source program, and builds an 
equivalent target program, whose structure is, in a sense, "simpler" than the 
structure of the source program. The simplification is achieved by removing 
certain "redundant" actions from the source program.

The goal of the project is to implement in [Scala](http://www.scala-lang.org) a
[positive supercompiler](http://sites.google.com/site/keldyshscp/Home/positive-supercompilers)
that is able to deal with higher-order functions.

The current version of hosc can be run as a command-line application
or as a [web-application](http://hosc.appspot.com).

hosc deals with programs written in a
simple lazy functional language with higher-order functions.
The intended operational semantics of the language is normal-order graph 
reduction to weak head normal form.

## News ##

**2010, December** I.G. Klyuchnikov. Towards effective two-level 
supercompilation. _Preprint 81. Keldysh Institute of Applied Mathematics, 
Moscow. 2010_.
[pdf](http://pat.keldysh.ru/~ilya/preprints/2LevelHosc_en.pdf)

**2010, November** Ilya Klyuchnikov. Supercompiler HOSC 1.5: homeomorphic 
embedding and generalization in a higher-order setting. _Preprint 62. Keldysh 
Institute of Applied Mathematics, Moscow. 2010_. 
[pdf](http://pat.keldysh.ru/~ilya/preprints/HOSC15_en.pdf)
(in Russian: [pdf](http://pat.keldysh.ru/~ilya/preprints/HOSC15_ru.pdf))

**2010, November** Ilya Klyuchnikov. "Inferring and proving properties of 
functional programs by means of supercompilation". PhD Thesis (In Russian):
Выявление и доказательство свойств функциональных программ методами 
суперкомпиляции // 
[Диссертация](http://pat.keldysh.ru/~ilya/klyuchnikov-phd.pdf), 
[Авторефереат](http://pat.keldysh.ru/~ilya/klyuchnikov-avtoreferat.pdf)

**2010, September** Ilya Klyuchnikov. Higher-order supercompilation. (In 
Russian): И.Г. Ключников. Суперкомпиляция функций высших порядков // 
_Программные системы: теория и приложения: электрон. научн. журн. 2010. № 3(3), 
с. 37–71_. [pdf](http://psta.psiras.ru/read/psta2010_3_37-71.pdf), 
[link](http://psta.psiras.ru/2010/03(003)/content-03(003).html)

**2010, July** Ilya Klyuchnikov and Sergei Romanenko. Towards Higher-Level 
Supercompilation. In _Proceedings of the Second International Workshop on 
Metacomputation in Russia. Pereslavl-Zalessky, Russia, July 1-5, 2010_. 
[PDF](https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/hosc/TowardsHLSC.pdf) 
[link](http://meta2010.pereslavl.ru/)

**2010, June** I.G. Klyuchnikov. Supercompiler HOSC: proof of correctness.
_Preprint 31, Keldysh Institute of Applied Mathematics, Moscow, 2010_. 
[PDF](https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/hosc/HOSC_Correctness_en.pdf) 
[link](http://library.keldysh.ru/preprint.asp?lg=e&id=2010-31)
(Also available in russian: 
[PDF\_ru](https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/hosc/HOSC_Correctness_ru.pdf) )

**2010, April** I.G. Klyuchnikov. Supercompiler HOSC 1.1: proof of termination.
_Preprint 21, Keldysh Institute of Applied Mathematics, Moscow, 2010_. 
[PDF](https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/hosc/Klyuchnikov_HOSC_proof_of_termination.pdf)
[link](http://library.keldysh.ru/preprint.asp?lg=e&id=2010-21)

**2010, January** HLL is extended with non-exhaustive patterns
[Simple example](http://hosc.appspot.com/view?key=agpzfmhvc2MtaHJkcjULEgZBdXRob3IiGmlseWEua2x5dWNobmlrb3ZAZ21haWwuY29tDAsSB1Byb2dyYW0Y27MBDA)

**2009, December** I.G.Klyuchnikov. Supercompiler HOSC 1.0: under the hood. 
_Preprint 63, Keldysh Institute of Applied Mathematics, Moscow, 2009_. 
[PDF](https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/hosc/Klyuchnikov_HOSC_under_the_hood.pdf) 
[link](http://library.keldysh.ru/preprint.asp?lg=e&id=2009-63)

**2009, June** Ilya Klyuchnikov and Sergei Romanenko. Proving the Equivalence of 
Higher-Order Terms by Means of Supercompilation. In: _Perspectives of Systems 
Informatics (Proceedings of Seventh International Andrei Ershov Memorial 
Conference, PSI 2009, Novosibirsk, Russia, June 15-19, 2009)._ Novosibirsk: A.P. 
Ershov Institute of Informatics Systems, 2009, pages 150-158. 
[PDF](https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/hosc/Klyuchnikov__Romanenko_Proving_the_Equivalence_of_Higher_Order_Terms_by_Means_of_Supercompilation.pdf)
[slides PDF](https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/hosc/psi09.pdf)

## Documentation

* Concepts
    - [The concept of a supercompiler](http://sites.google.com/site/keldyshscp/Home/supercompilerconcept)
    - [Positive supercompilers](http://sites.google.com/site/keldyshscp/Home/positive-supercompilers)
    - [Input language](HigherOrderLazyLanguage.md) (HLL)
* [HOSC web application](http://hosc.appspot.com/)
