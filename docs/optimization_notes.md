
# docs/optimization-notes.md

# Workflow Optimization Notes

---

# Objective

Add a pearl necklace to a professional office woman while preserving:

* Face
* Hair
* Clothing
* Pose
* Lighting

---

# Experiment 1

## Denoise = 0.3

### Result

Necklace generation was weak.

Minimal modification occurred.

---

# Experiment 2

## Denoise = 0.5

### Result

Best balance.

Necklace appeared naturally while preserving image integrity.

---

# Experiment 3

## Denoise = 0.8

### Result

Neck region changed excessively.

Minor distortion appeared.

---

# Experiment 4

## Prompt Refinement

### Prompt

Add simple pearl necklace

### Result

Generated necklace but occasionally added extra accessories.

---

# Improved Prompt

Add simple pearl necklace,
keep outfit unchanged,
keep pose unchanged

### Result

Much more consistent output.

---

# CFG Tests

## CFG = 5

Output lacked detail.

---

## CFG = 7

Best result.

---

## CFG = 10

Over-constrained generation.

Reduced realism.

---

# Recommended Production Settings

Resolution: Original

Steps: 25

CFG: 7

Denoise: 0.5

Sampler: DPM++ 2M SDE

Scheduler: Karras

---

# Key Learnings

* Small masks improve control.
* Lower denoise values preserve image integrity.
* Prompt specificity improves editing accuracy.
* Inpainting is highly effective for commercial image retouching.

---

# Production Applications

* Jewelry insertion
* Product placement
* Logo replacement
* Fashion editing
* Advertising workflows
* E-commerce image enhancement

---

# Conclusion

This workflow demonstrates a practical production use case for Generative AI.

The final solution enables targeted accessory insertion while maintaining overall image consistency, making it suitable for commercial and creative production environments.
