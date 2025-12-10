# Becoming One With the Machine

Programming has always been magic.

For decades, software engineering was sorcery limited to the few who could speak the language of the gods—those who learned the arcane syntax, mastered the sacred incantations, and spent years in the monasteries of computer science departments learning to bend silicon to their will.

If traditional coding is witchcraft—hours of careful spellwork, precise ingredients, ancient tomes of documentation—then vibe coding is something else entirely.

It's conjuring a familiar from the depths of the machine. A near-omniscient robotic minion that materializes at your command.

"Please create magic for me."

*Didn't get it right?*

"I'll whip you until you do."

That's the vibe. That's the new craft. And honestly? It's fun as hell.

But I'm getting ahead of myself.

> "You must neither fight the machine nor let it usurp you. Rather, you must become one with it."

That's something I tweeted in a thread a while back. It still feels true—maybe even more true now than when I wrote it.

If you want to build great software, I still think it's important to learn how to code. Master a language. Understand software principles and system design. Know how things work under the hood.

But I cannot deny that programming has changed. Fundamentally.

If you're not using AI assistance to maximize productivity, you are wasting your time. Unless you're specifically trying to learn fundamentals or have some pedagogical goal, there's no reason to write boilerplate by hand in 2025.

My daily driver for the past couple weeks has been Claude Opus 4.5 through Antigravity—shout out to Google for that—and it already feels better at coding than I'll ever be. I don't think I was ever that good to begin with, if I'm honest.

But here's the thing: even with a model that can outcode me, I still have to manually review, step in, and steer.

If I didn't know how to code, if I didn't understand software principles, I would end up stuck in cycles. The model suggests something. I accept it. It breaks something else. The model fixes that. It introduces a new bug. The model patches it. An hour later, the codebase is a mess and I don't know why.

I've watched this happen to people. It's painful.

The frontier models, as amazing as they are, are still in their infancy. They need strong supervision, guidance, and review. Sometimes you need to step in and take the wheel.

This is the uncomfortable truth about AI-assisted coding in 2025: the tools are incredibly powerful, but they're not autonomous engineers. They're collaborators. They need direction.

Andrej Karpathy coined the term "vibe coding" in early 2025 to describe a way of working where you "fully give in to the vibes, embrace exponentials, and forget that the code even exists." He introduced this in the context of rapid prototyping and throwaway weekend projects.

The term took off. Collins Dictionary named it Word of the Year. It became a meme.

But the meme has evolved in ways that do the original concept a disservice. People hear "vibe coding" and think it means prompting your way to production without understanding what the AI wrote.

That's not what Karpathy described. He was talking about low-stakes experimentation. Not building systems that handle user data and financial transactions.

I prefer the term "AI-assisted coding" because it captures the reality better: you're still coding, you're just not alone.

Let me be specific about the numbers, because the numbers are insane.

GitHub Copilot has over 20 million users and is used by over 90% of Fortune 100 companies. Developers using Copilot report completing tasks 55% faster. That's based on controlled experiments—1 hour 11 minutes with Copilot versus 2 hours 41 minutes without.

Cursor hit $500 million ARR by May 2025—the fastest SaaS company ever to reach that milestone. By November, they crossed $1 billion in annualized revenue. Their valuation went from $2.6 billion in January to $29.3 billion by November. They raised $2.3 billion in their Series D, with Nvidia and Google's Alphabet participating.

Cursor users merge 39% more pull requests than non-users. Development cycles compress by 30-50% for complex projects.

AI now generates an estimated 41% of all code written in 2025.

And it's not just Cursor. There's Windsurf, Replit, Bolt.new, Lovable, Claude Code, Amazon Q—the entire ecosystem is exploding. Cognition's Devin, the "AI software engineer," is pushing into agentic territory. The tools are everywhere.

These numbers are real. The productivity gains are real. Teams ship faster. Barriers to entry are lower.

And that's genuinely good.

Product managers can now prototype features themselves. Designers can bring their mocks to life without waiting for engineering time. People with ideas but no formal CS background can build working applications.

We hear about vibecoded apps making real revenue. Indie hackers shipping faster than ever. Solo founders building things that would have required teams five years ago.

The democratization of creation is happening. The sorcery is spreading beyond the monastery walls.

Now, about the dark side.

Yes, studies showed 45-62% of AI-generated code contained security vulnerabilities. XSS, SQL injection, log injection, missing input validation, hardcoded credentials—the classics. The AI learned from public code, and public code was often bad.

I'm using past tense deliberately.

The models are getting better. Genuinely, rapidly, noticeably better.

Before Opus 4.5, something was missing. I could always see when an LLM was doing something wrong—the subtle logic errors, the weird architectural choices, the code that worked but felt off. GPT-4o started the wave, but it had clear limitations.

Opus 4.5 feels like heaven and earth compared to what came before. It's just reliable. Not perfect, but reliable enough that I trust it for real work. I still review, but I'm catching fewer mistakes.

And this is currently cutting edge. But we all know how long "cutting edge" lasts in this industry.

Usually less than a few months before something better arrives.

In a year's time, Opus 4.5-level models will be available to everyone at 100x less the price. Look at what the Chinese open-source labs are doing—DeepSeek, Qwen, Yi. They're shipping capable models at a fraction of the cost. The democratization isn't just in tools; it's in the models themselves.

The security concerns? Being addressed. The code quality issues? Improving. The architectural weirdness? Getting better.

The dark side is real, but it's shrinking.

That said, there's still tribalism.

Some programmers feel genuinely threatened by AI-assisted coding. They see it as a devaluation of their skills, an existential threat to their careers. So they reflexively hate on it. Every time they see a vibecoded app, they try to tear it apart. Some go as far as security attacks and spam campaigns against indie projects.

Others call AI-assisted coders lazy. Boomers shaking their fists at the cloud. "You're not really programming." "You're just prompting." "You don't understand what you're building."

The only valid concern in that camp is about code quality—the worry that the promise of AI-assisted development doesn't match reality, that the code is worse, harder to maintain, more bug-prone.

And yes, sometimes that's true. The models aren't perfect. The outputs need review.

But the models will get better. They already are, rapidly. The code quality problems are being addressed. The security issues are being flagged automatically. The tooling is improving month by month.

Vibecoders and vibecoder "tookmakers" sometimes make huge promises that outpace reality. Not everything vibecoded is production-ready. Not every AI-assisted app scales. The hype can outrun the substance.

But ultimately? The models will be better at coding than all of us. That's just the trajectory.

So what do we do?

My traditional engineering background influences how I think about this. When I'm designing and building software now, I work from first principles. I create abstractions at a high level and use them to guide the workflow.

These days, I consider myself more of a systems architect than a line-by-line coder.

What I do is high-level abstract architecture. I define the shape of the system—the components, the interfaces, the data flows, the invariants. Then I use AI to fill in the implementation. I review. I steer. I correct.

The mental model is: I'm the sorcerer; the AI is the familiar. I set the intent; it does the conjuring. But I still inspect the magic.

This is different from both extremes.

It's not "reject AI and write everything yourself." That's a losing strategy. You'll be outcompeted by people who use the tools.

It's not "hand everything to AI and accept whatever it produces." That's how you get security holes, architectural drift, and a codebase nobody understands.

It's integration. Symbiosis. Using the AI as the minion it is and orchestrating it properly.

The skills that matter now are different than they used to be.

Prompt engineering is real, but it's not the main thing. The main thing is still understanding systems. Knowing what good architecture looks like. Understanding performance characteristics. Recognizing security patterns and anti-patterns. Having taste.

The AI can write the code. You need to know if the code is right.

That's harder than it sounds. It requires deep knowledge—the kind you only get from having written a lot of code yourself, from having debugged production systems, from having felt the pain of bad decisions.

There's a study from early 2025 that found experienced open-source developers using AI tools actually took 19% longer to complete tasks than those working without AI. They believed they were faster, but they weren't. The time spent reviewing and correcting "almost right" suggestions ate into the gains.

The lesson isn't that AI is useless. The lesson is that AI-human integration is a skill. You have to learn how to work with these tools. You have to develop judgment about when to accept, when to reject, when to guide.

That's the craft now.

Software engineering is more than just code. It always has been. It's systems design, architecture, understanding requirements, making tradeoffs, communicating with stakeholders, thinking about maintainability and scale.

The code is just the artifact. The thinking is the work.

AI changes what parts of the work you do yourself and what parts you delegate. But the thinking still has to happen. The judgment still has to be exercised. The architecture still has to be designed by someone who understands the problem.

For now, that someone is human.

So here's where I've landed:

Don't fight the machine. You'll lose. The tools are too powerful, the productivity gains too real. Refusing to use AI in 2025 is like refusing to use an IDE in 2010. It's a lifestyle choice, not a competitive strategy.

Don't let it usurp you either. Don't become a mindless prompt jockey who types "make it work" and commits whatever comes out. That path leads to codebases nobody can maintain, security holes nobody noticed, and architectures that collapse under their own weight.

Instead, find the balance.

Learn the fundamentals so you can supervise intelligently. Understand architecture so you can design systems that make sense. Develop taste so you can recognize good code from bad. Then use AI to multiply your output, to handle the tedious parts, to accelerate the implementation.

You're not competing with AI. You're directing it.

Ultimately, the models will keep getting better. Claude 5, GPT-5, whatever comes next—they'll write cleaner code, catch more bugs, understand more context. The gap between human and AI coding ability will close and eventually reverse.

When that happens, the skill that matters won't be "can you write code." It'll be "can you specify what should be built and verify that it was built correctly."

That's systems thinking. That's engineering judgment. That's architecture.

The code is becoming commoditized. The thinking never will be.

The magic is spreading. The familiars are getting smarter. The barriers between idea and implementation are dissolving.

You must neither fight the machine nor let it usurp you.

You must become one with it.
