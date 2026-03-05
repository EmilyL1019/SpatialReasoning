---
title: A Spatial Reasoning Benchmark for Multimodal Language Models

exports:
    - format: pdf
      template: arxiv_nips
date: 2026-03-04
authors:
  - name: Emily Light
    affiliations:
      - University of Rhode Island
  - name: Ethen Puls
    affiliations:
      - University of Rhode Island
  - name: Alex Garcia
    affiliations:
      - University of Rhode Island
  - name: Jack Lanoie
    affiliations:
      - University of Rhode Island
  - name: Cody
    affiliations:
      - University of Rhode Island

---
# Introduction

# Concept & Operationalization
This benchmark will have several exercises to measure LLM's ability to use common-sense spatial reasoning. We define common-sense reasoning as the ability to correctly infer relative orientation, rotation, and spatial displacement of objects under geometric transformations, using either textual descriptions alone or text grounded in visual input. This includes; mental rotation, relative positioning, directional movement inference, and transformation composition. 
* *Mental transformation* is the ability to infer an object orientation after rotation, sequential composition of transformation. This includes both single-step transformations (e.g., rotate 90° clockwise) and sequential composition of transformations (e.g., rotate 90° clockwise and then 180°). Correctly completing these types of exercises requires maintaining an internal representation of orientation and correctly updating it under rule-based operations.
* *Relative positioning* is the ability to define an object’s spatial location with respect to another object or reference point. For example, in the statement “The ball is to the left of the chair.”, the model must correctly interpret directional relationships within a shared coordinate frame. This includes reasoning about object-centered versus global reference frames and maintaining consistency when the reference object changes.
* *Directional movement* is the ability to interpret and apply movement commands, such as up, forward, clockwise, or counterclockwise. These tasks require mapping keywords to geometric operations and updating positional states accordingly. Movement reasoning may involve translating a point across a grid, following the direction of an arrow, or applying rotation to a facing object.
* *Transformation composition* is the ability to apply multiple spatial transformations sequentially to one object and identify its final state. This tests whether the models are  performing true compositional reasoning or relying on shallow pattern recognition. For example, combining rotation and translation requires maintaining intermediate state representations and applying transformation rules in order.
Including these four categories of capabilities will evaluate whether a model maintains internally consistent spatial representations that are stable across textual and visual modalities.
Our tasks for this benchmark will be split into two types of exercises; text-only spatial reasoning tasks and image + text multimodal tasks. Each task will have a standardized input-output structure, meaning that all tasks will follow a uniform prompt template. Each task will explicitly instruct the model to select a single-word answer from a predefined answer bank.
This benchmark will test models performance on these topics using various exercises. We will construct it as a controlled benchmark composed of discrete tasks across multimodal settings. Each task will evaluate a specific skill under the large umbrella of spatial reasoning.  By using this benchmark, we will evaluate how effectively large language models understand and manipulate physical space layouts, and object relationships. 

# Related Benchmarks

# Structure
The benchmark will contain two broad categories of tasks:
1. Generic Transformations, as well as and "common sense" style questions as to how transformations alter the interactivity or functionality of objects.
2. Pattern and algorithmic style questions, in an attempt to measure more complex spatial awareness and competence.

## Generic Transformations
A series of templated spatial tasks will be presented to the model, with an answer bank containing valid answers. Models will be prompted to respond with a single word from the answer bank. Scoring is binary, questions given the correct answer from the given answer bank are correct. Incorrect answers, or answers containing words from outside of the answer bank are marked incorrect. Scoring will be displayed as total correct/incorrect, as well as by tags (2-Dimensional, 3-Dimensional, transformation only, "common selse" style question, specific object transformed).
These questions will be either multi modal (image + text) or text-based, and will fit four categories:
1. 2D Spatial Transformations
2. 3D Spatial Transformations
3. 2D Spatial Transformations + Common Sense Style Question
4. 3D Spatial Transformations + Common Sense Style Question

### Sample Tasks

```{figure} /content/images/figures/prop_fig1.png
:label: fig1
:alt: A multimodal question example
:align: center

A sample multimodal question. The image, along with words in brackets, will be swapped to create a wide variety of generic questions. Tags for scoring display would be: multimodal, 2d, transformation_only, arrow

```

```{figure} /content/images/figures/prop_fig2.png
:label: fig2
:alt: A text based question example
:align: center

A sample text-based question, focusing on "common-sense" usability of objects after applying transformations to their positions. Tags for scoring display would be: 3d, text_based, common_sense, car

```

### Task Generation Strategy
Demonstrated in [](#fig1) and [](#fig2), 5-10 generic "template" questions will be designed, and then populated with values to create at least 50 questions. Large language models may be used to generate more questions, and if done, each question will be reviewed for accuracy and the answer will be answered manually by a team member.

## Algorithmic/Pattern Matching
### Sample Task
### Task Generation Strategy


