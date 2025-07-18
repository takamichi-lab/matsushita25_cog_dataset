# Video Stimuli for Measuring Time Delay Tolerance in Third-Person Live Commentary for Super Smash Bros. Ultimate
- This repository contains the open-source dataset published in the short paper at IEEE CoG 2025.
- This study proposes a methodology for measuring the acceptable delay tolerance for third-person game commentary.
- This site describes how to create videos shown to subjects in order to measure the acceptable delay tolerance.
- Please refer to the image below for an overview of the acceptable delay tolerance.
- ![Overview](./overview.png)


## Download Original Video
The video set for this experiment was created based on 32 one-on-one videos collected from [SMASH corpus](https://ss-takashi.sakura.ne.jp/corpus/smash/).
SMASH corpus includes match videos (without audio), commentary audio, and CSV files annotated with speech start and end times as well as topic tags.

## 'result.csv':Participant attributes and video stimuli information
| gender | age | known | experience | third_person_commentary | first_person_commentary | place | user_id | score | original_file | delay | utterance_id | topic_tag |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 男性 | 30代 | 知っている | 機会があれば，家族や友人とプレイをすることもある程度 | 数回程度見たことがある | 数回程度見たことがある | 自宅 | user42399_20241205201949-0272 | 3 | MM3 | -1 | 14 | 対戦風景 |
| ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |


- `gender`: Evaluator gender．　Male (男性),　Female (女性), N/A (回答しない).
- `age`: Evaluator gender． 10s (10代), 20s (20代), 30s (30代), 40s (40代), 50s (50代), 60s (60代), 70s< (70代以上).
- `known`: Does the evaluator know about this game? Yes (知っている), No(知らない).
- `experience`: How much has the evaluator played this game? Competitive (日常的に頻繁にやっており，ランク対戦など他者と競うプレイをすることが多い), Enjoy (日常的に頻繁にやっており，競うより楽しむことを目的としてプレイをすることが多い), Sometimes (機会があれば，家族や友人とプレイをすることもある程度), Only seen (自分でプレイした経験はないが，対戦動画をみたことがある程度), Never (知らない). 
- `third_person_commentary`: Have you ever watched third-person commentary (commentary by someone other than the player)? Often (よく見る), Sometimes (数回程度見たことがある), Never (見たことがない).
- `first_person_commentary`: Have you ever watched first-person commentary (player commentary)? Often (よく見る), Sometimes (数回程度見たことがある), Never (見たことがない).
- `place`: Place where the evaluation was performed.
- `user_id`: Evaluator ID (same ID means same evaluator).
- `score`: 5-point score on MOS.
- `original_file`: Number of which original video was used as a reference.
- `delay`: The number of seconds that the audio is delayed relative to the video (plus means the audio is delayed, minus means the audio is early).
- `utterance_id`: A number indicating the number of the evaluated utterance in the original video of the SMASH corpus.
- `topic_tag`: Topic tag of the evaluated utterance.

## Creating a Dataset
- Download data from [SMASH corpus](https://ss-takashi.sakura.ne.jp/corpus/smash/).
- Determine the video stimulus to create by referring to `original_file` and `utterance_id` in result.csv.
- The data included in [SMASH corpus](https://ss-takashi.sakura.ne.jp/corpus/smash/) includes csv files that include utterance numbers, etc., so please refer to them together with `utterance_id`.
- The duration of one video stimulus was at most 20 seconds, and included the target utterance (`utterance_id`) and the N utterances before it.
- The number of utterances is the maximum number within 20 seconds.
- Synchronize the match video and live audio by delaying the audio by the value of `delay`.

## License
- MIT

## Contributors
- Ryosuke Matsushita (Keio University, Japan, main contributor)
- Shinnosuke Takamichi (Keio University, Japan)

## Reference
- Ryosuke Matsushita, Ryosuke Sakai, Koki Fukuda, Shinnosuke Takamichi, Kota Iura, Yuki Saito, Graham Neubig, Katsuhito Sudoh, Hiroya Takamura, Tatsuya Ishigaki, "Measuring Time Delay Tolerance in Third-Person Live Commentary for Super Smash Bros. Ultimate", IEEE CoG, 2025.
