20190123 // IMPC hackathon
--------------------------

DAY 1
=====

1) Hamed
  - Essential genes
  - Using machine learning to predict lethatlity in genes

2) Gregor
  - Suggestion of several ideas
    - Large scale classification of histopath images
    - Predict early death in late adult pipeline(?)
    - predict weight outcome based on early adult pipeline
    - multidimensional phenotpye profile analysis
      - Link to diseases and/or gene sets
    - deep learning on X-ray images
      - label data is very sparse
      - prepared data set

3) Tudor
  - Drug target discovery: AI for drug discovery may not be a panacea
  - Method developed to learn a model for predicting gene associations
  - Proposed Machine learning academy: A collaborative effort to gather ML resources

4) Anna
  - Clustering examples.  Are there any ideas using ML?
  - Cardiovascular data
  - Clustering / network analysis

5) Mariaz
  - Selecting new candidate genes in genreal using ML
  - Transcriptomics based predicting genes
  - QUARK tool

6) Kola
  - ML applied to xray data
  - There is a lot of Xray data; not all is labelled
  - Counting number of ribs, etc. there is very little variation, so it makes it difficult to train

Break out into 3 groups
  - Clustering
  - Xray 
  - Implementing the IDG method

Minutes from IDG breakout
  - XGBoost selected as the ML algorithm
    - Grid search to determine the best model (tuning every parameter)
    - Tensorflow evaluated and didn't work so well
  - 50 genes per phenotype (MP Term) required to meet the cutoff to be included in the analysis
  - blind.predictions in the list of files is not ordered, but the highest p-values are the candidate genes for that phenotype (that's not already in OMIM if it's a disease)

Text mining resource: https://diseases.jensinlab.org


DAY 2
=====

... Continued with discussions from the previous day in the working groups ...

IDG Machine learning extension presentation and discussion
  - Next steps are to try to get the IDG pipeline running at other centers

Xray group presentation and discussion
  - Implemented a CNN method on xray images to determin sex
  - > 90% accuracy
  - Checked other count parameters correlated with Xray for automated counting
  - Next steps will be to try predictions 
  - Discussion about orientation of images


Clustering breakout presentation and discussion
  - Next steps are to see about 
  - see clustering presentation here:
    https://docs.google.com/presentation/d/1lSUnJgj0UwO3eei9Jrwl1rXAL5wx3NLJRPuP6AluByc/edit#slide=id.g4b0acb2a7b_2_98










