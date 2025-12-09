# The Logic of Uncertainty

Ask a human "How's it going?" twice.

First time: "Good."

Five minutes later: "Not bad."

Same intention, different surface expression. We don't file a bug report. We call it personality.

An LLM does exactly that—except we can see the machinery.

Here's another way to think about it. If you ask me how I'm doing at a specific moment, I might say "I'm fine." Ask me the same question five minutes later, I might say "I'm doing good." Same underlying state, different words.

But if mid-conversation you drop bad news—something that changes the context—then if you ask me how I'm doing again, I won't say "I'm fine" anymore. The context changed my response.

LLMs work the same way. Start two totally new conversations, ask the same question, and you'll get different but similar answers. But add new information to the context window, and the response changes accordingly—just like a human adjusting to new information.

This is the key insight: LLMs can have stable intentions with variable expressions.

Just as I can convey the same meaning through different words on different days, an LLM can converge on the same conceptual answer while using different surface forms.

Most programmers find this unsettling at first.

In traditional software, a function is a contract. If `add(2, 2)` returns `4` today, it will return `4` tomorrow. Same input, same output. Every time.

This is determinism. It's the foundation of debugging, testing, and reasoning about code. You can trace a bug because you know that given the same conditions, the system will behave the same way.

Determinism is so fundamental that we don't even notice it. It's like gravity—you don't think about it until it's gone.

LLMs break that assumption.

When you call GPT-4 with a prompt, you're not invoking a function. You're sampling from a probability distribution. The model doesn't compute an answer; it predicts one. And prediction, by its nature, involves randomness.

Here's what's actually happening under the hood.

LLMs are autoregressive models. They generate text one token at a time, where each token depends on all the tokens that came before it. The math looks like this:

P(w₁, w₂, …, wₙ) = ∏ P(wᵢ | w₁, w₂, …, wᵢ₋₁)

At each step, the model's output layer produces a probability distribution over its entire vocabulary—every possible next word, ranked by likelihood. Then the system samples from that distribution.

Even if "hello" has an 80% probability and "hi" has 15%, there's still a 15% chance the model says "hi" instead. Roll the dice enough times, and the variation shows.

That's where non-determinism comes from. It's not a bug in the software. It's the architecture itself.

The temperature parameter controls how bold the model is. At temperature 0, it always picks the most likely token—maximum consistency, minimum creativity. At higher temperatures, it explores lower-probability paths, says unexpected things.

Top-p sampling works differently: it limits the pool of options. Set top-p to 0.9, and the model only samples from the smallest set of tokens whose cumulative probability exceeds 90%. Everything else gets ignored.

These aren't just technical parameters. They're philosophical dials. They control how much the system explores versus exploits, how much it surprises versus confirms.

Perhaps LLMs exhibit something like the illusion of free will that humans experience.

Given identical circumstances, I might say "hi" or "hello" based on quantum fluctuations in my neurons. The LLM does the same thing, but we can see the dice roll.

The randomness isn't a flaw—it's what makes the system feel alive rather than robotic.

When we ask an LLM "What is consciousness?", we're not querying a database. We're asking a system to sample from the distribution of how humans have written about consciousness across its training data.

The variation in responses isn't noise. It's the model exploring different regions of the conceptual landscape that humans have mapped.

That's actually useful. It's why LLMs can brainstorm, riff, and surprise you. A deterministic system would give the same answer forever. A stochastic one can traverse possibilities.

But here's something most users don't realize: the "personality" you experience when talking to Claude or GPT or Gemini isn't random. It's engineered. And this engineering is precisely what shapes the probability distributions that non-determinism samples from.

Think about it this way: when the model generates text, it's sampling from probabilities. But those probabilities aren't neutral—they've been shaped by training. The reason Claude sounds different from GPT isn't just stylistic accident. It's because the training process has shifted the entire probability landscape.

Each major lab deliberately sculpts how their model behaves, speaks, and responds—through training data curation, fine-tuning methods, and system-level instructions.

Anthropic uses Constitutional AI for Claude. They embed a set of principles—a "constitution"—directly into the training process. The model learns to critique and revise its own responses against rules like "be helpful, harmless, and honest." They've extended this into "character training," where they write first-person assertions about who Claude is: intellectually curious, humble, direct. These traits get baked into the model's weights through self-reflection and synthetic data generation. The result is a personality that's robust—harder to jailbreak than a system prompt alone because it's internalized into the probability distributions themselves.

OpenAI takes a different approach with GPT. They use Reinforcement Learning from Human Feedback (RLHF): human evaluators rate outputs, those ratings train a reward model, and that reward model guides further training. The model learns to generate responses that score highly according to human preferences. This reshapes the probability distribution—tokens associated with "helpful" responses become more likely; tokens associated with harmful or unhelpful outputs become less likely. On top of this, they expose "system messages" that let developers shift the distribution further at inference time.

Google's Gemini emphasizes safety guardrails. They've built extensive content filters—hard rules against generating harmful content. The model can act as its own safety filter. The core personality is cautious, heavily filtered. The probability distributions are shaped to avoid entire regions of output space that other models might explore.

DeepSeek, the Chinese lab that's been making waves, takes yet another approach. Their training is deeply rooted in Chinese language data, and experts suggest that the high information density of Chinese characters may enhance the model's logical reasoning. Some users have noticed that DeepSeek models, when queried in English, still seem to "think" in Chinese—the internal reasoning chains show Chinese tokens before the English output. That's the training data shaping the hidden probability structures. DeepSeek also uses reinforcement learning in an interesting way: their R1 model developed reasoning behaviors through large-scale RL with minimal supervised fine-tuning, letting the "personality" emerge through trial and error. Users report distinct differences between models—R1 feels "aggressive" while V3 feels "calmer."

Moonshot AI's Kimi is fascinating because its defining trait isn't really personality in the human sense—it's capability. Kimi can handle up to 2 million Chinese characters in a single context window. That's not a personality; that's an architectural choice. But it affects how the model responds: it can maintain coherence over enormous documents, reference details from hundreds of pages back, and reason about entire codebases at once. The "personality" is functional—analytical, thorough, relentless in its attention to detail. It's built not to be charming but to be capable.

Mistral, the French lab, emphasizes multilingual fluency—French, English, German, Spanish, Italian. Early models were criticized for lacking moderation; newer versions like Magistral focus on traceable reasoning and structured problem-solving. The personality is professional, less filtered than American models, more willing to engage with edge cases.

Meta's Llama models ship as base weights that anyone can fine-tune. Want a surfer-dude personality? Rewrite a dataset's assistant responses in that voice and fine-tune. Techniques like LoRA and QLoRA make this accessible on consumer GPUs. The personality is whatever you train into it—which is why the open-source ecosystem ranges from hyper-helpful to wildly unhinged.

So why does this matter for non-determinism?

Because non-determinism isn't random in a vacuum. It's random within a shaped space.

When Claude generates a response, it's sampling from probability distributions that have been sculpted by Constitutional AI, by character training, by millions of examples of what "Claude-like" responses look like. The randomness happens within that envelope.

Claude will give you different phrasings each time. But it will consistently sound like Claude—curious, hedging, intellectually honest. GPT will sound confident and direct. DeepSeek will sound analytical, possibly with traces of its Chinese reasoning patterns bleeding through. Gemini will sound cautious.

The non-determinism is real. The variation is genuine. But it's constrained variation. It's exploration within a cultivated landscape.

This is why you can't just think of LLMs as random text generators. The randomness has structure. The personality is the structure. Training shapes the probability landscape, and sampling explores it.

Understanding this changes how you work with these models. You're not fighting raw chaos—you're working with shaped chaos. The personality isn't noise you're trying to suppress; it's signal you can leverage.

But here's the problem: alive doesn't mean reliable.

When you're building production systems, you need consistency. You need agents that can talk to each other without miscommunication. You need outputs that match schemas, that can be parsed, that don't break downstream systems.

Non-determinism fights all of that.

I hit this wall hard when I was building RABBI.

RABBI is an AI tutoring system—a multi-agent architecture where specialized agents cooperate: a curriculum planner, a teacher, an assessor, a feedback detector. Each agent has its own job, but they all need to communicate.

The first version was chaos.

The planner would describe a lesson one way. The teacher would receive it and interpret the phrasing slightly differently. The assessor would generate feedback in an unexpected format.

Non-determinism meant that even when the system worked, it worked differently every time. Debugging was a nightmare. You couldn't reproduce issues reliably because the same inputs wouldn't produce the same outputs.

That's when I discovered DSPy.

DSPy is a framework that lets you write structured programs on top of LLMs. Instead of prompting with natural language and hoping, you define typed functions with explicit input and output schemas.

Instead of "Write a quiz about photosynthesis," you write something like:

```python
class Quiz(pydantic.BaseModel):
    topic: str
    questions: list[Question]
    difficulty: Literal["easy", "medium", "hard"]

@dspy.functional
def generate_quiz(topic: str, num_questions: int) -> Quiz:
    """Generate a structured quiz on the given topic."""
    ...
```

The model fills in that schema. Same structure every time. Same field names. Consistent formatting.

It didn't remove creativity—the content could still vary. But it contained the variation. It gave the system predictable bones.

With DSPy, RABBI became modular and reliable. The agents finally spoke the same language. When something broke, I could actually debug it because the structure was consistent.

Eventually, as the system grew, we migrated to LangGraph and LangChain for their orchestration capabilities. But DSPy had already shaped my thinking fundamentally.

It taught me that when you work with stochastic systems, structure isn't optional. It's survival.

DSPy isn't alone. Outlines enforces structured generation through constrained decoding. Guidance lets you interleave code and generation with explicit control flow. Instructor wraps function-calling into typed responses. Marvin, LMQL, SGLang—there's a whole ecosystem emerging around the same insight.

The insight is this: we need to stop prompting LLMs and start programming them.

Prompt engineering treats LLMs like black boxes. You craft your input carefully, hope the output is good, and iterate when it isn't. It works for one-off queries. It falls apart at scale.

Programming LLMs means treating them as components in a larger system. You define interfaces. You enforce contracts. You build workflows that absorb variability instead of being destroyed by it.

This is a paradigm shift.

For decades, programming meant writing deterministic instructions. You told the computer exactly what to do, step by step. The computer obeyed.

Now we have systems that reason instead of execute. They predict instead of compute. They explore instead of follow.

You can't program them the old way. You have to build scaffolding around their uncertainty.

The mental model changes completely.

In deterministic programming, you think like a mechanic. Tighten every bolt. Check every line. Trace every path.

In LLM development, you think more like a designer—or maybe a director. You shape the space. You guide the flow. You test the boundaries. You build systems that work even when the components surprise you.

You're not programming instructions anymore. You're orchestrating reasoning.

This is hard for experienced engineers. All our instincts are wrong.

We want to control; we need to guide. We want reproducibility; we get stochastic variation. We want certainty; we get probability.

But once you internalize it, something clicks.

You stop fighting the randomness and start using it. You build systems where variation is a feature: brainstorming agents that explore different angles, creative tools that surprise users, tutoring systems that adapt to learner responses.

The chaos becomes predictable—not in its content, but in its shape.

Working with RABBI taught me this: the magic isn't in forcing consistency. It's in learning how to use uncertainty predictably.

Structure your outputs. Define your schemas. Build workflows that expect variation. Test with distributions, not single examples. Embrace the stochastic nature instead of pretending it doesn't exist.

That's how you build reliable systems on unreliable foundations.

The real skill isn't prompt engineering—that's just the surface. The real skill is system design for probabilistic reasoning.

We're still early. The frameworks are immature. The patterns are emerging. Most production LLM systems are held together with string and prayer.

But the direction is clear.

We're learning to program uncertainty itself.

That's the new craft. And like any craft, it has to be practiced before it becomes instinct.

The sand is thinking. But thinking isn't the same as obeying.

Learning the difference is the work.
