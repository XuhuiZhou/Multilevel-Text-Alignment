## A Benchmark for Document Relation Prediction and Localization
This benchmark belongs to our EMNLP2020 paper: [Multilevel Text Alignment with Cross-Document Attention](https://arxiv.org/abs/2010.01263). 

To download the benchmark, please click the **Download** button.

We also introduce a new modeling mechanism for this problem, see it by clicking the **View On Github** button.

Citation:

```bibtex
@inproceedings{Zhou2020Multilevel,
  author={Xuhui Zhou, Nikolaos Pappas, Noah A. Smith},
  title={Multilevel Text Alignment with Cross-Document Attention},
  booktitle={EMNLP},
  year={2020}
}
```

### Cite the Original Datasets
If you use our datasets, we highly recommend you to cite the original datasets as well:

For AAN:
```bibtex
@article{Radev2009TheAA,
  title={The ACL anthology network corpus},
  author={Dragomir R. Radev and Pradeep Muthukrishnan and Vahed Qazvinian and Amjad Abu-Jbara},
  journal={ELRA},
  year={2009},
  volume={47},
  pages={919-944}
}
```
For OC:
```bibtex
@inproceedings{Bhagavatula2018ContentBasedCR,
  title={Content-Based Citation Recommendation},
  author={Chandra Bhagavatula and Sergey Feldman and Russell Power and Waleed Ammar},
  booktitle={Proc. of NAACL},
  year={2018},
}
```
For S2ORC:
```bibtex
@inproceedings{Lo2020S2ORCTS,
    title = "{S}2{ORC}: The Semantic Scholar Open Research Corpus",
    author = "Lo, Kyle  and
      Wang, Lucy Lu  and
      Neumann, Mark  and
      Kinney, Rodney  and
      Weld, Daniel",
    booktitle = "Proc. of ACL",
    year = "2020",
}
```
For PAN:
```bibtex
@InProceedings{potthast:2013,
  author =  {Martin Potthast and Tim Gollub and Matthias Hagen and Martin Tippmann and Johannes Kiesel and Paolo Rosso and Efstathios Stamatatos and Benno Stein},
  booktitle = {Working Notes Papers of the CLEF 2013 Evaluation Labs},
  title = {{Overview of the 5th International Competition on Plagiarism Detection}},
  year =2013,
}
```

### Comparing documents
Many potential applications of natural languageprocessing involve a comparative analysis of two(or more) documents. In general, whenever we seek to model relationships between documents, we believe that these relationships can be localized in one or both documents. We believe that automatic identification of these local correspondences is useful, both directly (e.g., mining parallel sentences for use in traininga machine translation system), and for providing explanations (e.g., in plagiarism detection). Of course, these finegrained, localized correspondences are not typically directly observablein realistic datasets.  Here, we consider scenarios where positive and negative examples of document-level relationships are available for supervision, but finegrained correspondences between their parts are not. The problem we aim to solve is:  (i) given twodocuments (each decomposed, e.g., into sentencesand  words),  automatically  categorize  whether  aparticular relationship holds between them, and (ii) which parts between them should be “aligned” insupport of the relationship in (i). We will refer tothese tasks respectively as document-to-document alignment (D2D) and sentence-to-document alignment (S2D).

### A new benchmark
While many tasks and datasets focus on understand-ing the relationships between sentences or docu-ments separately, to the best of our knowledge, there are no joint publicly available English bench-mark for both D2D and S2D tasks. Annotating document correspondences is expensive and time-consuming, especially at a fine-grained level like sentences. Therefore, we introduce a new benchmark consisting of six tasks (four D2D and two S2D). 

## Dataset 101
Since our benchmark contains many tasks, some concrete examples would help with understanding and use the benchmark<sup>1</sup>. If you have any questions, please don't hesitate to contact! 

#### AAN and OC:
Those two datasets are straight-forward. They only consider the document-level tasks. ```1``` represents positive relationship and ```0``` represents no relationship.

| Label      | Source Document | Target Document | 
| ----------- | ----------- | ----------- |
|   0  | Some particular classes of lexical paraphrases such as verb alteration and compound noun decomposi- tion can be handled by a handful of general rules and lexical semantic knowledge. In this paper, we attempt to capture the regularity underlying these classes of paraphrases, focusing on the paraphras- ing of Japanese light-verb constructions (LVCs). We propose a paraphrasing model for LVCs that is based on transforming the Lexical Conceptual Structures (LCSs) of verbal elements...| In this paper we develop an automatic classifier for a very large set of labels, the WordNet synsets. We employ Conditional Random Fields (CRFs) because of their flexibility to include a wide variety of non- independent features. Training CRFs on a big number of labels proved a problem be- cause of the large training cost... |
| 1 | Some particular classes of lexical paraphrases such as verb alteration and compound noun decomposi- tion can be handled by a handful of general rules and lexical semantic knowledge. In this paper, we attempt to capture the regularity underlying these classes of paraphrases, focusing on the paraphras- ing of Japanese light-verb constructions (LVCs). We propose a paraphrasing model for LVCs that is based on transforming the Lexical Conceptual Structures (LCSs) of verbal elements... | We describe a syntax-based algorithm that au- tomatically builds Finite State Automata (word lattices) from semantically equivalent transla- tion sets. These FSAs are good representa- tions of paraphrases. They can be used to ex- tract lexical and syntactic paraphrase pairs and to generate new, unseen sentences that express the same meaning as the sentences in the input sets...|

#### S2ORC
S2ORC contains two tasks, one is the D2D task, another is the S2D task. 
| Label      | Source Document | Target Document | 
| ----------- | ----------- | ----------- |
| 1  | One of the most important parts of the educational process, usually the last part, from a student point of view, is the knowledge assessment  . The increased use of computers in education and the embracement of e-learning  lead to computerized assessments, especially web-based assessment systems  ```\001``` . Even non-standard forms of assessment have an ascending trend, especially in United States  .However, there are only a few studies that aim to assess students' degree of acceptance of this new online testing environment   , although, from a teacher's point of view, we can clearly identify the advantages of using an online assessment system: a better security, no need to print the tests, the results can be made available immediately after the student finishes the test ```\001``` ...| As a continuous effort to improve and increase the use of computers in students education, weimplemented an online assessment server. Its purpose is to ease the students examination processand to provide a transparent and objective evaluation. The solution we developed is a webapplication, written using PHP and Javascript. It uses MySQL as a database management systemand Apache for the web server, hosted on a Linux system. The site can be accessed through a webbrowser capable of handling AJAX queries (Asynchronous Javascript and XML). Using theadministration module, one can add or remove questions, question categories, can create tests andset its parameters (number of questions, time per question, IP addresses allowed to access the test).The administrator can also monitor the students during the test. The types of questions allowed aremultiple choices with a single or multiple correct answers...|

* The sentence-level task is operationalized by using a special character ```\001``` to indicate the positive sentence. This information also exists in the training and validation data. However, the experiments in our paper only consider the test data.
* For positive D2D pairs (Label is ```1```), you may notice that some of them do not have ```\001``` to indicate the position of the positive sentence (981, 117, 125 number of pairs for training, validation, and test datasets). This does not exclude the pairs from being positive but rather cases where the exact citation position can not be extracted from the original dataset. (You can get rid of these pairs if you want.)
* For negative D2D pairs, the source documents can still contain the ```\001``` charater, but it's ok to just ignore them.

#### PAN

PAN contains two tasks, one is the D2D task, another is the S2D task. 
| Label      | Source Document | Target Document | 
| ----------- | ----------- | ----------- |
| 1  | ... He had not declared either by words or actions that as his father was a rich man, and as he was an only son, he would therefore do nothing. But he had tried his hand thrice, and in each case, after but short trial, had assured his father and his friends that the thing had not suited him. ```\001```Leaving Oxford without a degree,--for the reading of the schools did not suit him,--he had gone into a banking-house, by no means as a mere clerk, but with an expressed proposition from his father, backed by the assent of a partner, that he should work his way up to wealth and a great commercial position.```\001```But six months taught him that banking was an abomination, and he at once went into a course of reading with a barrister.| Leaving Oxford without a degree,--for the reading of the schools did not suit him,--he had gone into a banking-house, by no means as a mere clerk, but with an expressed proposition from his father, backed by the assent of a partner, that he should work his way up to wealth and a great commercial position...|

* The sentence-level task is operationalized by using a special character ```\001``` to indicate the positive sentence (appears at the beginning of the sentence). This information also exists in the training and validation data. However, the experiments in our paper only consider the test data.
* For positive D2D pairs (Label is ```1```), you may notice that some of them do not have ```\001``` to indicate the position of the positive sentence (127, 19, 22 number of pairs for training, validation, and test datasets). This does not exclude the pairs from being positive but rather cases where the exact span information can not be extracted from the original dataset. (You can get rid of these pairs if you want.)
* For negative D2D pairs, the source documents can still contain the ```\001``` charater, but it's ok to just ignore them.


<sup>1</sup> Please always download the latest version of the dataset.
