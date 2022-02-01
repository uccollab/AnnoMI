# AnnoMI: A Dataset of Expert-Annotated Counselling Dialogues

## Dataset Introduction

Research on natural language processing approaches to analysing counselling dialogues has seen substantial development in recent years, but access to this area remains extremely limited, due to the lack of publicly available expert-annotated therapy conversations. In this paper, we introduce _**AnnoMI**_, the first publicly and freely accessible dataset of professionally transcribed dialogues demonstrating high- and low-quality motivational interviewing (MI), an effective counselling technique, with annotations on key MI aspects by domain experts.

This version contains:

* Metadata of each transcript & utterance, e.g. the demonstrated MI quality and the URL of the original video
* Each utterance
* The annotation on each utterance: **(Main) Therapist Behaviour** for each therapist utterance and **Client Talk Type** for each client utterance

## Dataset Format

The dataset is stored in `dataset.csv`, in the same folder as this README. **Each row represents the information associated with an utterance.**

`dataset.csv` has the following columns:

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

## Citation
If you use this dataset in your research, please cite our [paper](https://zixiu-alex-wu.github.io/files/AnnoMI_ICASSP_Camera_Ready_Personal_Use.pdf) in the format below:
```bash
@inproceedings{wu2022anno,
  title={Anno-MI: A Dataset Of Expert-Annotated Counselling Dialogues},
  author={Wu, Zixiu and Balloccu, Simone and Kumar, Vivek and Helaoui, Rim and Reiter, Ehud and Reforgiato Recupero, Diego and Riboni, Daniele},
  booktitle={ICASSP 2022-2022 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)},
  year={2022},
  organization={IEEE}
}
```
