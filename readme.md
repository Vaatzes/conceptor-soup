# Conceptor Soup

## Overview
An open-source project aimed at improving model soups using conceptors, focusing on Transformer models but applicable to other architectures.

## Objectives
- Integrate conceptors with Transformer models.
- Analyse model soups using the mathematical conceptor framework.
- Improve model soup performance and efficiency.

## Background
[Model soups](https://arxiv.org/abs/2203.05482) introduced the idea of averaging the weights of multiple fine-tuned models to improve downstream accuracy. This can be done in both a "uniform" fashion, in which all models are used equally, or a "greedy" fashion, selecting models by some criterion. To anyone familiar with the idea of catastrophic interference, this method for performance improvement should be anathema, and yet it works. Needless to say it has sparked a lot of research into a mechanistic explanation of the performance of model soups. To my knowledge, this understanding is not yet there. Understanding the process by which weight averaging affects performance can help us select/train better models, improve on the weight consolidation scheme beyond mere averaging, overcome cases in which model soups fail, and may even further our understanding of deep learning performance in general.

This project was born out of an observation that the output of a single layer of n nodes can often be approximated by a m dimensional manifold, where m''<<''n, especially when training with L2 regularization. If this is the case for the models used in the model soup, then understanding the manifolds on which the output of corresponding layers across multiple models lies can explain how weight averaging across this layer affects its output. There are many cases of manifold learning that could be used to visualize the manifold on which some output lies. However, these often don't allow for direct comparison between different manifolds or don't integrate well into the deep learning pipeline. Along comes [conceptors](https://arxiv.org/abs/1403.3369) (or more concisely [here](https://arxiv.org/abs/1406.2671)), a formalization of the response of a neural network to some input. While not directly applicable to deep learning, efforts have been made to integrate conceptors into backpropagation [here](https://arxiv.org/abs/1707.04853) and [here](https://marcpickett.com/cl2018/CL-2018_paper_55.pdf).

A reason for using conceptors over other ways of representing the manifold on which the output of a layer lies is because conceptors open themselves up for boolean logic. We can get the intersection or union of multiple such representations, or find the "inverse" of a manifold. This inverse represents space outside of the manifold, i.e. unused output space. Furthermore, as conceptors can be integrated into backpropagation, we can train models to be within or outside of a given manifold (represented by a conceptor), project one layer's output onto the "conceptor space" (the subspace of the manifold represented by the conceptor) of the corresponding layer in another model, and identify models/layers which overlap (or not) in their output. An easy first thing to test using this technique is to find models which are overlapping or orthogonal in their (hidden layers') output, and use those exclusively for the model soup. 

## ToDo List
- [ ] Literature review on conceptors and model soups.
- [ ] Baseline performance evaluation of model soups.
- [ ] Theoretical framework development for conceptor integration.
- [ ] Prototype implementation and evaluation.
- [ ] Documentation and refinement based on feedback.

## Usage
To be determined.

## Contributors
**Core Organizer:** Vaatzes

### How to Contribute
Contributions are welcome in the form of research, code, documentation, and ideas. To join the discussion and contribute, please join our Discord server: [Join our Discord](https://discord.gg/WjxStubmnE).

