### Directories
- input:コンペ提供fileの保存
- output:実験ごとのsubmission file, oof, モデルの重み等の保存
- notebook:特徴量生成, 学習用のノートブックを保存
- feature:BERT, Resnet関連の特徴量保存

### 手順
1. text_translation.ipynb でtext columnを翻訳  (1columnあたり2h前後必要)  
2. (翻訳後text)をBERTで特徴ベクトル化  
- text_sentiment_feature.ipynb(Twitter Sentiment Classificationの予測値)  
- text_feature.ipynb(BERTのCLS tokenのベクトル(かえるさんdiscussion)) 最終subは翻訳後textのみ特徴化  
3. image_feature.ipynbでresnet50の特徴抽出  
4. exp.ipynbでLGBMの学習, submissionfileの作成  
  
- 1~3で作成したものは/feature/に保存される
- feature内には既に生成後の特徴量が入っているのでexp.ipynbをrun allするとsubmission fileは作られます．

- submission_lgbm_False.csvが提出ファイル(public:0.9346, Private:0.9577)
