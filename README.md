# LMAnnotation
Code used to automate the annotation of datasets and data obtained to integrate into the [AICollaboratory](https://ai-collaboratory.jrc.ec.europa.eu/).

## What is AICollaboratory? 💡
[AICollaboratory](https://ai-collaboratory.jrc.ec.europa.eu/) is a tool to analyse, evaluate, compare and monitor the state-of-the art of Artificial Intelligence systems. This project provides an unifying setting that incorporates data, knowledge and measurements to characterise AI systems. The AIcollaboratory is framed in the context of AI watch, a knowledge service of the European Commission carried out by the JRC in collaboration with DG CNECT. 

## Data :page_facing_up:
[Data](https://upvedues-my.sharepoint.com/:f:/g/personal/ymordav_upv_edu_es/ErCCxwQphKFIiRPfIHR1kIUB7Q3UEeplop76e5o24frEkg?e=7HFkup) (OneDrive link) contains a folder for each multiple choice task used in the study, obtained from [BigBench](https://github.com/google/BIG-bench) or [HELM](https://crfm.stanford.edu/helm/latest/). Inside each folder, there are 14 files:

- {task}.csv: original task data.
- {task}_aggreagated_metafeatures.csv: values for the linguistic meta-features for each instance in the task.
- {task}_features_post.csv: meta-feature values for each task sentence after the post-processing stage.
- {task}_rf_noIRT_difficulty_notargers.pdf: scatter plot representing predicted difficulty values by a Random Forest trained with linguistic meta-features vs actual values.
- {task}_rf_readability_difficulty_notargers.pdf: scatter plot representing predicted difficulty values by a Random Forest trained with readability metrics vs actual values.
- gpt-4_{task}: raw answers for meta-feature values for each sentence in the task by GPT-4.
- LexicalDiversity_METRICS.csv: lexical diversity values for each task instance.
- LexicalDiversity_PAIRS.pdf: correlation matrix of lexical diversity metrics.
- LexicalReadability_METRICS.csv: readability metrics values for each task instance.
- LexicalReadability_PAIRS.pdf: correlation matrix of readability metrics.
- meta_features_{task}.pdf: bar plot showing the value distribution of each meta-feature for the task.
- rf_noIRT_difficulty_feature_importance.csv: influence of each meta-feature in the prediction of the Random Forest. 
- rf_readability_difficulty_feature_importance.csv: influence of each lexical diversity and readability metric in the prediction of the Random Forest.

## How to use the code 💻
For annotating any task use the original task data (with the structure followed in {task}.csv mentioned above). The code should be run in the following order:
1. Preproceso
2. GPT4Experiment (an API key with GPT4 access is needed)
3. Postprocessing

For evaluating the predictability of the results use:
- AutomatedRF: for linguistic meta-features annotation.
- AutomatedReadability: for lexical diversity and readability metrics calculation.
