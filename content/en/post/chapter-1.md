---
date: 2025-05-30
description: "Embrace the power of the model itself."
featured_image: "/images/HumanandRobotHands.jpeg"
tags: ["Function Call"]
title: "Enhancing Large Language Models' Function Calling via Self-Refinement Multiscale Loss and Automated Data Refinement"
---
Function call becomes a fundamental concept in Large Language Models, enabling more efficient interaction.

We propose FunReason, FunReason enhances LLMs' function calling by balancing reasoning and execution accuracy. Using automated data refinement and Self-Refinement Multiscale Loss (SRML), it generates high-quality training data for query parseability, reasoning coherence, and precise function calls. SRML optimizes both aspects during training, matching GPT-4o performance while minimizing forgetting. 

**Overview of FunReason's data refinement pipeline.** The pipeline consists of five stages: Function Call Classification, Query and Tool Identification, CoT Identification, Function and Parameter Identification, and Format Identification. Each stage ensures specific aspects of data quality, with failing examples either being discarded or regenerated.

**We will release all the data that refined in this process, whcih contains 60k high quality CoT data for function call.**

**Self-Refinement Multiscale Loss.** Traditional loss functions often overemphasize the lengthy reasoning process at the expense of function call accuracy. The inherent trade-off between reasoning quality and function call correctness, leading to the development of our balanced approach.

**Self Refinement Strategy.** Following the MSL training, we employ a Self-Refinement strategy to further enhance the model capabilities. In this phase, the MSL-trained model samples from the original xLAM dataset, generating its own Chain-of-Thought reasoning and corresponding function calls. Subsequently, this self-generated data is fed into the data refinement pipeline for automated inspection and improvement. Only the refined data, having passed the rigorous quality checks of the data refinement, is then used to further update the model's parameters. This iterative process allows the model to learn from its own improved outputs, leading to continuous self-enhancement of its function calling and reasoning abilities.
