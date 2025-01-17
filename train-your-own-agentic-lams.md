---
description: >-
  This page is still being updated...! We'll be back with a comprehensive
  walk-through so anyone can build a LAM
icon: wand-magic-sparkles
---

# Train Your Own Agentic LAMs

### Quick Start

While LAMs are new to most, we've refined the training process to its essence: one-click and \~50 examples are all it takes to create autonomous computer-use agents that outperform OCR-based solutions by 30% on real world tasks.

<figure><img src=".gitbook/assets/image (11).png" alt="" width="563"><figcaption><p>Screenshot of the Training History page, where user's can export agentic knowledge they've collected</p></figcaption></figure>



## From playing games, to a capable LAM in 4 easy steps!

1.  **Record Some Skills**

    Hop into the Training Gym and start completing tasks. The system automatically translates your on-screen behavior into rich trajectories that our agents can learn from.

    > Or, if you prefer, you can trade or acquire datasets from other users in the Data Marketplace (coming soon).
2. **Export Your Data**\
   Once you’ve accumulated enough demonstrations, click ![](<.gitbook/assets/image (13).png>)
   1. OpenAI: You’ll get a `.jsonl` file, containing human behavior enriched with the context and synthetic reasoning behind each action, perfect for finetuning. Other export formats and integration guides are on their way!
3.  **Fine-Tune the Model**\
    Watch as your agent’s performance leaps forward, thanks to real human demonstrations in your dataset.

    1. Using OpenAI’s API, or any compatible service, to fine-tune GPT-4o (guides for QWEN and Phi are coming soon).

    <figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption><p>GPT-4o fine-tuning metrics from a fine-tuning experiment with 1 million training tokens (50 gym tasks)</p></figcaption></figure>
4. &#x20;**Deploy Your Agent!**\
   Once trained, your LAM is ready to tackle tasks that involve actual computer use—whether it’s playing a new game or automating daily workflows. Keep track of new trajectories in the [**Training History**](https://viralmind.ai/gym/history), and watch the **Neural Skill Network** expand as your agent learns even more skills. Simply edit the config file of your favorite agent runtimes/frameworks to use your enhanced model (i.e. replace `model: "gpt-4o-2024-08-06"`with `model: "ft:gpt-4o-2024-08-06:personal:computer-use:ARtrFFE"`). More information coming soon!



