
# Group Project 2 Implementation of Dynamic Scene Graph Generation and Understanding with Soccer

## Goals
The original goal of this project was to take american football frames and be able to classify formations and plays. This was later changed to focus on soccer since it is much more scarse in object detection datasets with less objects needed to be classified. Furthermore, we intend to generate captions depending on the move, whether it be classification of relations or natural language processing.

## Background

Video Scene Graph Generation (VidSGG) has been an interesting development in the field of computer vision. Multiple approaches have been compiled however we limited ourselves to object detection datasets, with potentially adding relationships if need be.

Originally we looked at the PVSG paper [https://arxiv.org/pdf/2311.17058] which gave a good overview of the VidSGG path however, object detection approaches had an easier implementation versus segmentation approaches like this.

After futher literary review, we looked at the set of papers that provided object detection implementaitons while also providing knowledge on other works in this field:

Spatial-Temporal Transformer for Dynamic Scene Graph Generation (https://arxiv.org/pdf/2107.12309):

- Provided a base model utilizing a FasterRCNN101 based on Resnet 101 as the object detector with their Spatial-temporal Transformer (STTran) with a spatial encoder "takes an input frame to extract spatial context and reason about the visual relationships within a frame" and a temporal decoder "takes the output of the spatial encoder as input in order to capture the temporal dependencies between frames and infer the dynamic relationships"

-

Potential Utilizations of Scene **Graphs**
- Captioning
- Visual Question Answering
- image generation

## Implementation



1st Stage: Object Detection

- Faster RCNN (STTran)
- Mask RCNN
- (CYCLO)

These will output the:
- Subject visual
- Subject semantic
- object visual
- object semantic
- sub/obj mask

to represent the relation prediction


2nd stage: Replication Predictors

Progressive:
- Vanilla*

Batch Progressive:
- Handcrafted Window*
- 1D Convolution*
- Transformer Endcoder*
- (STTran)
- (CYCLO)

Hierarchical:
- HIG
- TRACE

*Methods mentioned by nearly all the papers

In addition, theres different level of contraints:
- With constraint: Only allows one Subject, Object, Predicate pair; wont get more than one label 
- No contraint: Allows multiple guesses; Causes wrong information
- Semi constraint: Allowing multiple 

3rd Stage: Captioning



## Dataset
Example dataset from STTran:

Action Geneome

```
|-- action_genome
    |-- annotations   #gt annotations
    |-- frames        #sampled frames
    |-- videos        #original videos
```

Our dataset is built on the AeroEye dataset (CYCLO) whose number of frames is dominated by sports (Figure 4.) and of the sports mentioned Soccer has a plurality as compared to other sports like Basketball and Baseball.

Soccer Relationship predicates = Cheering, Watching, Players, Competing, Passing, Scoring, Kicking, Marking

## Expirements

## Results