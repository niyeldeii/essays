# The Multiplication Problem

In *The Matrix Reloaded*, Agent Smith discovers he can copy himself.

One becomes two. Two becomes four. Four becomes a hundred. By the end of the film, he's an army—identical, coordinated, relentless. Neo fights one and fights them all.

It was terrifying science fiction in 2003. In 2024, it's a deployment strategy.

Consider what you can do today with off-the-shelf tools.

You can spin up a thousand browser instances. You can give each one an autonomous agent—Claude, GPT-4, an open-source model fine-tuned to your specs. You can point them at social media platforms with instructions to post, reply, engage, and argue.

Each agent can maintain a persona, remember conversation history, adapt its tone to the platform. Each can generate original content—not recycled templates, but fresh text indistinguishable from human writing.

For the cost of API tokens, you can deploy Agent Smith.

This isn't hypothetical. In early 2025, researchers at a university secretly infiltrated a popular Reddit forum with AI bots. The bots weren't detected. They influenced discussions, shaped opinions, and only came to light when the researchers published their paper.

The outrage was predictable. But forget the ethics of the experiment—what mattered was the proof of concept.

If a university research team can do this with a handful of bots and limited resources, what can a state actor do? What can a political campaign do? What can anyone with motivation and a credit card do?

We're not prepared for this.

When I read about the Reddit infiltration, I decided to make my own foray into the problem. I built a bot detection system for Twitter—now X—using RoBERTa-large as the foundation. The idea was to combine the language understanding capabilities of a transformer model with numerical and behavioral features from user profiles: follower counts, account age, verification status, posting patterns.

The architecture was straightforward. RoBERTa processes the tweet text and produces an embedding from the [CLS] token. That embedding gets concatenated with the numerical and boolean features. The combined vector passes through a classification head—layer normalization, a hidden layer, dropout, and a final linear layer that outputs bot or not-bot.

I froze the first 20 of RoBERTa's 24 encoder layers and only fine-tuned the top 4. This let me leverage the pre-trained knowledge while adapting to the specific task without overfitting on a limited dataset.

The results were promising but imperfect. On sample data, the model achieved 67% accuracy, 0.60 F1, and 0.64 ROC AUC. Not production-ready, but enough to demonstrate the approach.

The bigger lesson was what I learned about the problem itself. Bot detection is an arms race, and the bots are winning.

Traditional detection relied on behavioral signals. Bots posted too frequently. They had suspicious follower ratios. They used repetitive language. Their accounts were too new.

These heuristics worked against simple bots—scheduled tweets, amplification scripts, basic spam.

They don't work against LLM-powered agents.

An LLM can vary its language naturally. It can space out its posts to mimic human activity patterns. It can engage in genuine-seeming conversations. It can even make "mistakes"—typos, incomplete thoughts, casual tone—that make it seem more human.

The very non-determinism we talked about in the previous essay—the thing that makes LLMs feel alive—also makes them harder to detect as artificial.

Every advantage we have in building useful AI agents is also an advantage for building malicious ones.

And it gets worse.

Consider the 2016 and 2020 US elections. There were confirmed cases of foreign actors using troll farms—actual humans, in actual rooms, posting propaganda at scale. The Internet Research Agency in St. Petersburg became infamous.

That required infrastructure. It required payroll. It required managing humans who might leak, might defect, might make mistakes that expose the operation.

LLMs remove all of those constraints.

You don't need a building full of humans. You need a server. You don't need to pay salaries. You need to pay for tokens. You don't need to worry about leaks. The agents don't have opinions about their employers.

A sufficiently motivated actor can now deploy influence operations at scale that would have required state-level resources a decade ago.

And it's not just text.

Sora can generate photorealistic video. Voice cloning can replicate anyone's speech patterns from a few minutes of audio. Image generators can fabricate evidence—fake screenshots, fake documents, fake photographs of events that never happened.

We're entering an era where seeing is no longer believing.

The multimedia capabilities of modern AI mean that the attack surface isn't just social media posts. It's every channel of information humans use to understand the world.

A fake video of a politician saying something inflammatory, released 48 hours before an election. A cloned voice leaving a threatening voicemail, attributed to someone who never made the call. A fabricated photograph of a crime that never occurred.

These aren't theoretical. They're happening. And our detection systems are behind.

Computer use agents make this even more concerning.

Anthropic, Google, and others have released models that can control a computer—navigate browsers, click buttons, fill forms, interact with web applications. The intent is legitimate: let AI assistants help with complex tasks.

The implication is that AI agents can now impersonate humans not just in text, but in behavior. They can sign up for accounts, solve CAPTCHAs (or delegate to CAPTCHA farms), build post histories, establish "credibility" over time, and then activate when needed.

You can pre-position agents months before you need them.

The bot I might detect today could have been created, cultivated, and made to look legitimate six months ago. By the time it starts spreading propaganda, its account looks indistinguishable from a real user's.

So what do we do?

The answer has to be adversarial systems—detection systems that evolve alongside the threats.

My bot detection project taught me several things about what this requires.

First, multimodal is essential.

Text alone isn't enough. An LLM can fool text classifiers. But combining text with behavioral patterns, temporal features, network analysis, and interaction graphs creates a much harder target for adversaries to game.

My system used numerical features like follower counts and account age alongside the text embeddings. A real detection system would go further: graph neural networks for social relationships, temporal models for activity patterns, anomaly detection for coordinated behavior.

Second, real-time monitoring matters.

Batch classification—scanning accounts periodically—isn't fast enough. By the time you detect a coordinated campaign, the damage is done.

We need streaming architectures that can flag suspicious activity as it happens. This is harder technically and more expensive computationally, but it's the only way to respond at the speed of viral content.

Third, the models need continuous updating.

A classifier trained on 2023 bot behavior will miss 2025 bot behavior. The adversaries adapt faster than annual model refreshes.

This requires infrastructure for rapid retraining, active learning from flagged content, and feedback loops from human reviewers. It's not just ML—it's MLOps at a level most organizations aren't prepared for.

Fourth, we need to accept imperfection.

My model got 67% accuracy. That sounds bad for a binary classifier—barely better than chance on a balanced dataset.

But in real-world bot detection, the goal isn't perfect classification. It's raising the cost of attack. If 60% of bot accounts get flagged, the adversary needs to create more accounts, vary their tactics more, spend more resources staying under the radar.

Detection doesn't have to be perfect to be useful. It has to make the attack economically or operationally harder.

Fifth, transparency and coordination matter.

No single platform can solve this alone. Bots banned from Twitter migrate to Facebook. Narratives seeded on Reddit spread to YouTube.

Cross-platform information sharing—at least for coordinated inauthentic behavior—is essential. So is public research, academic collaboration, and open datasets for training detection models.

My project was small, imperfect, and is probably already outdated. The bots have evolved since I built it.

But it taught me to think about the problem correctly.

The goal isn't building classifiers. What we need are immune systems.

Immune systems don't prevent infection perfectly. They detect threats, mount responses, remember pathogens, and evolve over time. They coordinate across the body and accept that some invaders will get through, focusing instead on limiting damage and building resistance.

That's the mental model for AI safety in the age of generative models.

The multiplication problem—the Agent Smith scenario—is real. Anyone can now create armies of autonomous agents capable of writing propaganda, arguing positions, manipulating opinions, and deceiving at scale.

The only response is to build systems that can match that scale—detecting threats, responding quickly, and adapting as the adversaries evolve.

This is one of the reasons I started this blog. Not just to explore the technical capabilities of these systems, but to think through their implications.

The sand is thinking. And some of what it's thinking isn't good for us.

Learning to defend against it is part of the work.
