Improving Diffusion model fidelity with Vision-Language Guidance

Description\
Tried two approaches, Iterative Refinement and Clip-embedded fine-tuning, to increase fidelity of images generated by Diffusion models.\

Milestones\
Milestone 1: Literature Review, Feasibility Study, and collecting benchmarks.(completed)\
Milestone 2: Datasets and Models' collection and deployment.(completed)\
Milestone 3: Implement vision-language guidance mechanisms into the model. Check the initial results.(completed)\
Milestone 4: Test the model's ability to generate high-fidelity images compared to original models. Evaluate the model against standard benchmarks and metrics.(completed)
Milestone 5: (Optional) Create a demo to show real-time results.(N/A)
Milestone 6: Write a report and create the repository.(completed)

Repo contains two notebooks and a .py training script that need to be manually added into to some place under the root, and change the clip-embedded fine-tune code's script address accordingly.

No extra command is needed. Just run notebooks.

Results:
Iterative Refinement
[23.63835973739624, 24.020499801635744, 24.128654670715333] Average ClipScore of first 100 prompts from parti-prompt dataset with 0,3,6 refinement steps respectively

Clip-Embedded Fine-tune

tensor(23.4626),tensor(23.5181),tensor(23.6169),tensor(23.8905),tensor(23.8673),tensor(23.6294) Average ClipScore of first 100 prompts from parti-prompt dataset with Original SD, 10k step normal fine-tune, 5k step normal fine-tune, 2k step embed fine-tune, 5k step embed fine-tune, 10k step embed fine-tune(guide_scale=0.05)

[18.8323,18.9441,19.6628] Average of ClipScore of 50 chosen prompts with original Clipscore lower than 20 from parti-prompt dataset with Original SD, 5k step normal fine-tune, 2k step embed fine-tune


Conclusions:\

The iterative refinement approach isn’t actually feasible.\

The clip-embedded fine-tune approach does offer a SD model that generate high-fidelity results especially when the given prompt is probably out of the training set distribution.

