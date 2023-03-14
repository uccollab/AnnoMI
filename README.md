# UPDATE (14/03/2023): we released the **_full_** version of our AnnoMI dataset. More details below. The original reduced version remains available.
        
## Introduction

Despite the remarkable growth of research in recent years on the analysis of counselling conversations through natural language processing methods, the potential of this field has been greatly limited by the lack of access to publicly available therapy dialogues, especially those with expert annotations.

To benefit research community we release **_AnnoMI_**, containing 133 faithfully transcribed and expert-annotated demonstrations of high- and low-quality motivational interviewing (MI), an effective therapy strategy that evokes client motivation for positive change.

Two versions of AnnoMI are made available:
1) `AnnoMI-simple.csv`: simplified version of AnnoMI consisting of high-level motivational interviewing annotation.
2) `AnnoMI-full.csv`: full version containing further expert-annotated attributes for each utterance and additional annotation data.


## AnnoMI-simple

`AnnoMI-simple.csv` has the following columns:

* `transcript_id`: the unique numerical identifier of the conversation/transcript where this utterance belongs. Note that this identifier is NOT used for ordering, and it is only to distinguish between different conversations in the dataset.
* `mi_quality`: the MI quality demonstrated in the conversation/transcript where this utterance belongs. Either "high" or "low".
* `video_title`: the title of the original video of the conversation/transcript where this utterance belongs.
* `video_url`: the URL of the original video of the conversation/transcript where this utterance belongs.
* `topic`: the topic(s) of the conversation/transcript where this utterance belongs.
* `utterance_id`: the unique numerical index of this utterance. Note that this identifier IS ordering-sensitive, and the utterance whose `utterance_id` is $n$ is the $n$-th utterance of the conversation (identified by the `transcript_id` of this row) where this utterance belongs.
* `interlocutor`: the interlocutor of this utterance. Either "therapist" or "client".
* `timestamp`: the timestamp of this utterance w.r.t the original video of the conversation/transcript where this utterance belongs.
* `utterance_text`: the content of this utterance.
* `main_therapist_behaviour`: the (main) therapist behaviour of this utterance. "n/a" if the utterance is a client utterance, otherwise one of ["reflection", "question", "therapist\_input", "other].
* `client_talk_type`: the client talk type of this utterance. "n/a" if the utterance is a therapist utterance, otherwise one of ["change", "neutral", "sustain"].

## AnnoMI-full

`AnnoMI-full.csv` retains all columns of the simple version, but adds the following ones:

* `annotator_id`: the ID of the annotator that made the annotations of this row. Ranges from 0 to 9.
* `therapist_input_exists`: whether there is input from the therapist in this utterance. "n/a" if the utterance is a client utterance, otherwise one of ["True", "False"].
* `therapist_input_subtype`: the therapist input subtype. "n/a" if the utterance is a client utterance or if `therapist_input_exists` is False, otherwise one of ["information", "advice", "negotiation", "options"].
* `reflection_exists`: whether there is reflection from the therapist in this utterance. "n/a" if the utterance is a client utterance, otherwise one of ["True", "False"]
* `reflection_subtype`: the reflection subtype. "n/a" if the utterance is a client utterance of if `reflection_exists` is False, otherwise one of ["simple", "complex"]
* `question_exists`: whether there is a question from the therapist in this utterance. "n/a" if the utterance is a client utterance, otherwise one of ["True", "False"]
* `question_subtype`: the question subtype. "n/a" if the utterance is a client utterance or if `question_exists` is False, otherwise one of ["open", "closed"]

        

## Citation
If you use this dataset in your research, you can cite our [initial paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9746035) where we first presented AnnoMI  in the format below:
```bash
@INPROCEEDINGS{9746035,
  author={Wu, Zixiu and Balloccu, Simone and Kumar, Vivek and Helaoui, Rim and Reiter, Ehud and Reforgiato Recupero, Diego and Riboni, Daniele},
  booktitle={ICASSP 2022 - 2022 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)}, 
  title={Anno-MI: A Dataset of Expert-Annotated Counselling Dialogues}, 
  year={2022},
  volume={},
  number={},
  pages={6177-6181},
  doi={10.1109/ICASSP43922.2022.9746035}}
}
```

And our [extended paper](https://www.mdpi.com/1999-5903/15/3/110) which contains deeper analysis of the data:
```bash
@Article{fi15030110,
AUTHOR = {Wu, Zixiu and Balloccu, Simone and Kumar, Vivek and Helaoui, Rim and Reforgiato Recupero, Diego and Riboni, Daniele},
TITLE = {Creation, Analysis and Evaluation of AnnoMI, a Dataset of Expert-Annotated Counselling Dialogues},
JOURNAL = {Future Internet},
VOLUME = {15},
YEAR = {2023},
NUMBER = {3},
ARTICLE-NUMBER = {110},
URL = {https://www.mdpi.com/1999-5903/15/3/110},
ISSN = {1999-5903},
ABSTRACT = {Research on the analysis of counselling conversations through natural language processing methods has seen remarkable growth in recent years. However, the potential of this field is still greatly limited by the lack of access to publicly available therapy dialogues, especially those with expert annotations, but it has been alleviated thanks to the recent release of AnnoMI, the first publicly and freely available conversation dataset of 133 faithfully transcribed and expert-annotated demonstrations of high- and low-quality motivational interviewing (MI)&mdash;an effective therapy strategy that evokes client motivation for positive change. In this work, we introduce new expert-annotated utterance attributes to AnnoMI and describe the entire data collection process in more detail, including dialogue source selection, transcription, annotation, and post-processing. Based on the expert annotations on key MI aspects, we carry out thorough analyses of AnnoMI with respect to counselling-related properties on the utterance, conversation, and corpus levels. Furthermore, we introduce utterance-level prediction tasks with potential real-world impacts and build baseline models. Finally, we examine the performance of the models on dialogues of different topics and probe the generalisability of the models to unseen topics.},
DOI = {10.3390/fi15030110}
}
```
