# Med_vqa
creating VQA model for medical imaging data

# Data 

[source](https://www.nature.com/articles/sdata2018251) 

The final VQA-RAD dataset contains 3,515 total visual questions. Of these, 1,515 (43.1%) are free-form. 733 questions are rephrased which means 48.3% of the free-form questions have corresponding paraphrasing. The remaining 1,267 questions are framed and have corresponding free-form and rephrased questions. On average, there are 10 questions per image.
All questions are short, with medians, mean, and modes ranging from 5 to 7 words per question.
Subgroup analysis of free-form questions demonstrates the relationship between question types and answer types. Of the 11 question types, Presence questions dominate, with 36% (483) of free-form questions. The least frequent question type is Counting, with only 1% (15) questions. The QA pairs are split into 42% (637) open-ended answer types and 58% (878) close-ended. Yes/no questions represent 92% of the close-ended QA pairs, and ‘yes’ (405) is as frequent as ‘no’ (406.)

# Workflow

1- Data preprocessing is performed on questions ( for embedding) and images ( to extract feauters).

2- image features are extracted from the last Vgg16 pooling layer,Each feature vector corresponds to a 32 x 32 pixel region.

3- Extracted feauters are combined into one dataset.

4- model is built using that dataset. question vectores are inputed through LSTM before concatenation.

5- General VQA model structure: cnn(for image), LSTM(for questions) => concatenate => flatten => output a propabalistc prediction.
