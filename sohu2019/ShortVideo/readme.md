# 短视频内容理解与推荐竞赛
背景介绍
 

近年来，机器学习在图像识别、语音识别等领域取得了重大进步，但在视频内容理解领域仍有许多问题需要探索。字节跳动公司旗下的TikTok（抖音海外版）短视频APP在全球范围内的用户中获得非常多的好评，短视频的内容理解与推荐技术成为了我们关注的焦点。

 

一图胜千言，仅一张图片就包含大量信息，难以用几个词来描述，更何况是短视频这种富媒体形态。面对短视频内容理解的难题，字节跳动作为一家拥有海量短视频素材和上亿级用户行为数据的公司，通过视频内容特征和用户行为数据，可以有充足的数据来预测用户对短视频的喜好。

 

本次竞赛提供多模态的短视频内容特征，包括视觉特征、文本特征和音频特征，同时提供了脱敏后的用户点击、喜爱、关注等交互行为数据。参赛者需要通过一个视频及用户交互行为数据集对用户兴趣进行建模，然后预测该用户在另一视频数据集上的点击行为。

 

竞赛最终根据参赛者提交的模型和预测结果，依据评分进行排名，具体见评估准则。

 

 

竞赛任务
 

通过构建深度学习模型，预测测试数据中每个用户id在对应作品id上是否浏览完作品和是否对作品点赞的概率加权结果。 本次比赛使用 AUC（ROC曲线下面积）作为评估指标。AUC 越高，代表结果越优，排名越靠前。

 

赛道1

大规模数据集，亿级别的数据信息。

 

赛道2

小规模数据集，千万级别的数据信息。

![data-field-cn-2](./image/data-field-cn-2.png)
 

参赛队伍可以在比赛页面的讨论区进行讨论。如有赛题和数据方面的问题，请发邮件至AI-Lab-challenge@bytedance.com。如有竞赛提交方面的问题，请发邮件至support@biendata.com。

 官网：https://biendata.com/competition/icmechallenge2019/

数据集说明：https://biendata.com/competition/icmechallenge2019/data/

训练集
文件说明/Read me：http://drive.bytedance.net/p/DfNmxDIQuLkFGP7qBQ
赛道1 - 大规模数据集，亿级别的数据信息。
参考官网

赛道2 - 小规模数据集，千万级别的数据信息。

final_track2_train.txt.tgz	http://lf1-ttcdn-tos.pstatp.com/obj/icme2019&bytedance_challenge_dataset/final_track2_train.txt.tgz	407M
<br/>
track2_face_attrs.txt.tgz	http://lf1-ttcdn-tos.pstatp.com/obj/icme2019&bytedance_challenge_dataset/track2_face_attrs.txt.tgz	63M
<br/>
track2_title.txt.tgz	http://lf1-ttcdn-tos.pstatp.com/obj/icme2019&bytedance_challenge_dataset/track2_title.txt.tgz	72M
<br/>
track2_video_features.txt.tgz	http://lf1-ttcdn-tos.pstatp.com/obj/icme2019&bytedance_challenge_dataset/track2_video_features.txt.tgz	4.3G
<br/>
测试集
赛道1 - 大规模数据集，亿级别的数据信息。
参考官网

赛道2 - 小规模数据集，千万级别的数据信息。

final_track2_test_no_anwser.txt.tgz	http://lf1-ttcdn-tos.pstatp.com/obj/icme2019&bytedance_challenge_dataset/final_track2_test_no_anwser.txt.tgz	58M
<br/>
测试集下载说明：
1.测试集中finish、like字段值为-1。
2.测试集中包含少部分未曾出现在训练集中的userid。

Baseline 方法代码

github地址：https://github.com/challenge-ICME2019-Bytedance/Bytedance_ICME_challenge
<br/>
竞赛提供的baseline方法使用到以下5个特征：user_id, user_city, item_id，author_id，item_city

TRACK2 LIKE TASK:
auc: 86.5%
#------------------------params-------------------------#
embedding_size = 40
optimizer = adam
lr = 0.0005

TRACK FINISH TASK:
auc: 69.8%
#------------------------params-------------------------#
embedding_size = 40
optimizer = adam
lr = 0.0001 