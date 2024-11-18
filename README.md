# Layer Fusion for Spatially Distributed Memory Dataflow Computing

## Abstract
This project introduces a novel approach for evaluating deep convolutional neural networks (CNNs) by restructuring computations to minimize off-chip memory usage. The method focuses on fusing the computations of multiple adjacent CNN layers to enable efficient data reuse, reducing memory bandwidth requirements and improving overall performance in spatially distributed memory dataflow computing architectures.

## Introduction
Conventional CNN computation processes each layer iteratively, requiring significant off-chip memory bandwidth to store and retrieve intermediate data. This method introduces **layer fusion**, which fuses multiple CNN layers into a single computational pipeline, leveraging localized on-chip data caching. The approach minimizes the need for intermediate data transfers to off-chip memory, reducing bandwidth requirements and improving energy efficiency.

### Key Features
- **Layer Fusion:** Combines adjacent CNN layers into a single computational unit to reduce intermediate data movement.
- **Pyramid-Shaped Dataflow:** Organizes data access in a sliding window structure that enables localized caching and reuse of intermediate results.
- **Tradeoff Analysis:** Balances on-chip memory requirements and recomputation costs to achieve optimal performance.

## Methodology

### Core Concepts
1. **Localized Data Dependencies:** Each output in a CNN layer depends only on a small, localized region of the input, allowing intermediate results to be cached and passed directly between layers.
2. **Pyramid-Shaped Data Access:** A hierarchical sliding window mechanism ensures efficient data reuse during computations, avoiding redundant data transfers.
3. **Reuse vs. Recompute:** Evaluates tradeoffs between recomputing intermediate results or caching them in on-chip buffers for reuse.

### Benefits
- Reduces off-chip data transfers by caching intermediate results on-chip.
- Minimizes energy consumption by avoiding redundant memory accesses.
- Improves performance by leveraging the spatial locality of data in distributed memory architectures.

### Tradeoffs
- Increased on-chip memory usage for storing intermediate results.
- Design complexity due to managing overlapping computation regions and memory buffers.

## Applications
The layer fusion technique is generalizable to any spatially distributed memory architecture, such as systolic arrays, custom ASICs, GPUs, and other dataflow-based computing systems. Potential applications include:
- Real-time image recognition and processing.
- High-performance natural language processing models.
- Large-scale scientific simulations using deep learning models.

## Example Workflow
1. Divide the CNN into computational blocks consisting of adjacent layers.
2. Configure the fused computation pipeline based on the pyramid-shaped data dependencies.
3. Optimize on-chip memory allocation for intermediate data reuse.
4. Evaluate tradeoffs to balance recomputation costs and memory usage.
5. Deploy the fused-layer model on the target spatial computing hardware.

## Key Results
- Significant reduction in off-chip data transfers, up to 95% in typical scenarios.
- Efficient utilization of on-chip memory, achieving high performance with minimal overhead.
- Scalability to larger and deeper networks by fusing additional layers.

## Conclusion
Layer fusion is a transformative approach for spatially distributed memory dataflow computing systems. It optimizes CNN evaluation by drastically reducing memory bandwidth requirements, making it a valuable technique for modern high-performance computing architectures.

## References
For detailed theoretical background and experimental results, refer to the corresponding research paper.
