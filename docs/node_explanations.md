# docs/node-explanations.md

# Node Explanations

---

# Load Image

## Purpose

Loads the original image into the workflow.

## Why did I use this node?

The objective is image editing rather than image generation.

The original approved image must be preserved.

### Interview Question

Why use the original image instead of generating from scratch?

### Answer

The task requires modifying only a specific region while preserving the rest of the image.

---

# Mask Editor

## Purpose

Defines the editable region.

## Why did I use this node?

Only the neck area should be modified.

Everything else should remain unchanged.

### Interview Question

Why is masking important?

### Answer

Masking constrains AI modifications to selected image regions.

This prevents unwanted changes elsewhere.

---

# Load Checkpoint

## Purpose

Loads the SDXL Inpainting model.

## Why did I use this node?

The workflow requires a model trained for image editing tasks.

### Interview Question

Why use an Inpainting model?

### Answer

Inpainting models are optimized to regenerate masked regions while preserving surrounding content.

---

# Positive Prompt Encoder

## Purpose

Defines the desired modification.

### Prompt

Add simple pearl necklace,
keep outfit unchanged,
keep pose unchanged

### Interview Question

Why is prompt design important?

### Answer

The prompt guides the model toward the desired object while preserving the original image.

---

# Negative Prompt Encoder

## Purpose

Prevents unwanted artifacts.

### Example

extra jewelry,
multiple necklaces,
blurry,
distorted neck,
deformed clothing

### Interview Question

Why use negative prompts?

### Answer

Negative conditioning reduces common image generation errors.

---

# Inpaint Conditioning

## Purpose

Combines:

* Original image
* Mask
* Prompt

into a conditioned latent representation.

## Why did I use this node?

This node enables localized editing.

### Interview Question

What problem does Inpainting solve?

### Answer

Inpainting enables targeted image modification without regenerating the entire image.

---

# KSampler

## Purpose

Performs diffusion within the masked area.

## Recommended Settings

Steps: 25

CFG: 7

Denoise: 0.5

### Interview Question

Why use Denoise 0.5?

### Answer

It provides enough freedom to generate the necklace while preserving the original neck structure.

---

# VAE Decode

## Purpose

Converts latent data into a visible image.

### Interview Question

Why is VAE Decode necessary?

### Answer

The diffusion process operates in latent space and must be converted into RGB image space.

---

# Save Image

## Purpose

Exports the final edited image.

---

# Key Learning Outcomes

This project demonstrates:

* AI Inpainting
* Mask-Based Editing
* Localized Diffusion
* Commercial Retouching Workflows
* Production-Oriented Editing Pipelines
