# ood
OOD implemenations
1. Gradient X Activatins for OOD Detection
  Modern neural networks can produce confident predictions for unfamiliar (out-of-distribution) inputs.GAIN addresses this by:
    1.Computing attribution scores for neurons (activation × gradient),
    2.Identifying key neurons driving model decisions,
    3.Detecting OOD samples by monitoring shifts in neuron attribution patterns.
  
  For each input sample and selected layer(s):
    1.Forward Pass: Compute neuron activations.
    2.Backward Pass: Compute gradients of model output (usually loss) with respect to activations.
    3.Attribution: For each neuron, calculate GAIN = Activation × Gradient.
    4.Important Neurons: Aggregate and select neurons with the highest GAIN scores as most responsible for the model’s output.
    5.OOD Detection: Compare attribution patterns of incoming samples with those from in-distribution data.
    6.Significant deviation in attribution structure signals a possible OOD input.
