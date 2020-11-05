## A Benchmark for Document Relation Prediction and Localization
This benchmark belongs to our EMNLP2020 paper: [Multilevel Text Alignment with Cross-Document Attention](https://arxiv.org/abs/2010.01263). 

To download the benchmark, please click the **Download.zip** button.

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



