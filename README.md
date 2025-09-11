# Unintended Offense Dataset collected from Twitter
Repository for "Leveraging Conflicts in Social Media Posts: Unintended Offense Dataset" paper, published in EMNLP 2024. All updates on this public dataset can be found in this repository.

## Dataset Details
Currently, this repo provides:
1. **Scored Replies -** Annotated replies with offensiveness and confidence scores with OPs.
2. **Binary Labeled Replies -** Binary labeled replies created by combining our data and Founta's dataset.
3. **Original Conversations -** Raw tweets and parsed conversations.
### Scored Replies
* **averaged_scores_with_context.csv**: contains 2401 pairs of context tweets and target tweets (op and replies) with averaged, annotated offensiveness and confidence scores. It also includes references to the original conversation IDs they belong to, as well as author IDs for both the context and target tweets.

### Binary Labeled Replies
Unintended Offense tweets (UO) collected through the method proposed in the paper are combined with negatives from *hatespeech-twitter* (Founta) to build binary-labeled reply sets for training classifiers. The details of the combinations are listed below.

(Note: These Train/Val/Test splits are "target tweets" only, meaning that they are only the replies in the conversations because the Founta doesn't provide contexts.)

#### Train & Validation
3 types of train & validation set are provided, under 3 different settings as the experiment section in the paper: 

| Type       | Size (train+val) | Positives                 | Negatives            |
| --------- | ---------------- | -------------------------- | -------------------- |
| Annotated | 2088 (1670+418)  | UO(50+)                    | Founta(negatives)    | 
| Mixed     | 5322 (4256+1066) | UO(50+) & UO(unannotated)  | Founta(negatives)    |
| Full      | 7504 (6022+1502) | UO(all)                    | Founta(negatives)    |

(50+ means only the tweets with offensiveness annotation >50 are included)

#### Test
  
1 type of test set is provided under the "Mixed" setting
  
| Type       | Size (test) | Positives                 | Negatives            |
| --------- | ------------ | ------------------------- | -------------------- |
| Mixed     | 524          | UO(50+) & UO(unannotated) | Founta(negatives)    |

### Original Conversations
Whole conversations that include the contexts are provided in the follwing files:

* **conversations_with_attr.json**: It contains the crawled data with raw attributes of tweets.
* **conversations_text_only.json**: It's our parsed version that only the author and the text are kept in each post. The conversations were segemented based on the struture proposed in the paper.
A example conversation from the parsed version looks like this:
  ```json
  {
          "conversation_id": "1391034802506174466",
          "context_tweets": [
              {
                  "author_id": "869417417327480832",
                  "text": "My weight this morning is 193 lbs, up from 191.8 yesterday."
              }
          ],
          "target_tweet": [
              {
                  "author_id": "74255689",
                  "text": "@StevijoPayne You should weigh yourself once a week on the same day at the same time. Your weight will fluctuate from day to day but you get a good sense of where you are on a weekly basis. You will just frustrate yourself if you do it everyday"
              }
          ],
          "follow-up_tweet": [
              {
                  "author_id": "869417417327480832",
                  "text": "@Micpo972 I know how to weigh."
              }
          ],
          "cue_tweets": [
              {
                  "author_id": "74255689",
                  "text": "@StevijoPayne Sorry didn\u2019t mean to offend."
              }
          ]
      },
  ```

***If you are interested in this work, please consider to cite this paper!***
> @inproceedings{tsai-etal-2024-leveraging-conflicts,   
  >&nbsp;&nbsp;&nbsp;&nbsp;title = "Leveraging Conflicts in Social Media Posts: Unintended Offense Dataset",   
  >&nbsp;&nbsp;&nbsp;&nbsp;author = "Tsai, Che Wei and Huang, Yen-Hao  and Liao, Tsu-Keng and  Salazar Estrada, Didier Fernando and Latifah, Retnani and Chen, Yi-Shin",   
  >&nbsp;&nbsp;&nbsp;&nbsp;editor = "Al-Onaizan, Yaser and Bansal, Mohit  and Chen, Yun-Nung",   
  >&nbsp;&nbsp;&nbsp;&nbsp;booktitle = "Proceedings of the 2024 Conference on Empirical Methods in Natural Language Processing",   
  >&nbsp;&nbsp;&nbsp;&nbsp;month = nov,   
  >&nbsp;&nbsp;&nbsp;&nbsp;year = "2024",   
  >&nbsp;&nbsp;&nbsp;&nbsp;address = "Miami, Florida, USA",   
  >&nbsp;&nbsp;&nbsp;&nbsp;publisher = "Association for Computational Linguistics",   
  >&nbsp;&nbsp;&nbsp;&nbsp;url = "https://aclanthology.org/2024.emnlp-main.259/",   
  >&nbsp;&nbsp;&nbsp;&nbsp;doi = "10.18653/v1/2024.emnlp-main.259",   
  >&nbsp;&nbsp;&nbsp;&nbsp;pages = "4512--4522",   
> }

***Also, The following is the biblatex of the work of Founta. Please cite their paper in any published work that uses any of resources from their work.***

>@inproceedings{founta2018large,   
  >&nbsp;&nbsp;&nbsp;&nbsp;title={Large Scale Crowdsourcing and Characterization of Twitter Abusive Behavior},   
  >&nbsp;&nbsp;&nbsp;&nbsp;author={Founta, Antigoni-Maria and Djouvas, Constantinos and Chatzakou, Despoina and Leontiadis, Ilias and Blackburn, Jeremy and Stringhini, Gianluca and Vakali, Athena and Sirivianos, Michael and Kourtellis, Nicolas},  
  >&nbsp;&nbsp;&nbsp;&nbsp;booktitle={11th International Conference on Web and Social Media, ICWSM 2018},  
  >&nbsp;&nbsp;&nbsp;&nbsp;year={2018},  
  >&nbsp;&nbsp;&nbsp;&nbsp;organization={AAAI Press}  
}
