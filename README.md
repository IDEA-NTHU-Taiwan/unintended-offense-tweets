# Unintended Offense Dataset collected from Twitter
Repository for "Leveraging Conflicts in Social Media Posts: Unintended Offense Dataset" paper, published in EMNLP 2024. All updates on this public dataset can be found in this repository.

## Dataset Details
Unintended Offense tweets (UO) collected through the method proposed in the paper are combined with negatives from hatespeech-twitter dataset to build this Unintended Offense Dataset.
The details of the combination are listed below.

### Train & Validation
3 types of train & validation set are provided, under 3 different settings as the experiment section in the paper: 

| Type       | Size (train+val) | Positives                 | Negatives            |
| --------- | ---------------- | -------------------------- | -------------------- |
| Annotated | 2088 (1670+418)  | UO(50+)                    | Founta(negatives)    | 
| Mixed     | 5322 (4256+1066) | UO(50+) & UO(unannotated)  | Founta(negatives)    |
| Full      | 7504 (6022+1502) | UO(all)                    | Founta(negatives)    |

(50+ means only the tweets with offensiveness annotation >50 are included)

### Test
  
1 type of test set is provided under the "Mixed" setting
  
| Type       | Size (test) | Positives                 | Negatives            |
| --------- | ------------ | ------------------------- | -------------------- |
| Mixed     | 524          | UO(50+) & UO(unannotated) | Founta(negatives)    |


***Also, The following is the biblatex of the work of Founta. Please cite their paper in any published work that uses any of resources from their work.***

>@inproceedings{founta2018large,   
  >&nbsp;&nbsp;&nbsp;&nbsp;title={Large Scale Crowdsourcing and Characterization of Twitter Abusive Behavior},   
  >&nbsp;&nbsp;&nbsp;&nbsp;author={Founta, Antigoni-Maria and Djouvas, Constantinos and Chatzakou, Despoina and Leontiadis, Ilias and Blackburn, Jeremy and Stringhini, Gianluca and Vakali, Athena and Sirivianos, Michael and Kourtellis, Nicolas},  
  >&nbsp;&nbsp;&nbsp;&nbsp;booktitle={11th International Conference on Web and Social Media, ICWSM 2018},  
  >&nbsp;&nbsp;&nbsp;&nbsp;year={2018},  
  >&nbsp;&nbsp;&nbsp;&nbsp;organization={AAAI Press}  
}
