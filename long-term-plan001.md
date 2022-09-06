# Long Term Plan

Date: 20220904

## Status
* feature plan.

## Context and Problem Statement
* After we have the testing, we could have more brave changes or any refactoring with modern framework.
* In this adr I'll plan it with a simple AI, to do auto tagging.

## Considered Options
* use exists AI library
   * rubixml (PHP)
   * TensorFlow 

## Decision Outcome

### How to make it happen and intermediate milestones
* Train model
  * use exists tags for classification.
  * use Ngram to get each classification's feature.
  * use this feature (which is extracted by Ngram), to go with KNN for train model.
* Use model
  * raw data use Ngram to get feature
  * use KNN model to know this raw data should go with which tag.

### Positive Consequences
  * It's worth a try to add new features with new code structure. 

### Negative Consequences
  * The AI classification may increase running time, could use async to resolve it. 
