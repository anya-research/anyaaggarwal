<script>
	import Card from '$lib/components/Card.svelte';
	import WorkExperience from '$lib/components/WorkExperience.svelte';
	import WorkExperiences from '$lib/components/WorkExperiences.svelte';
	import Project from '$lib/components/Project.svelte';
	import Projects from '$lib/components/Projects.svelte';
	import videoPoster from '$lib/assets/me-poster.webp';
	import Link from '$lib/components/Link.svelte';
	import underResearchLogo from '$lib/assets/companies/under-research.png';
	import independentResearchLogo from '$lib/assets/companies/independent-research.png';
</script>

<div class="intro flex flex-col md:flex-row md:items-center gap-6 md:gap-4 p-4 pt-12 pb-16">
	<div class="shrink-0 self-center md:-ml-8">
		<div class="memoji w-60 md:w-[300px] aspect-square">
			<img
				class="block w-full h-full"
				src={videoPoster}
				alt="Anya Aggarwal"
				width="512"
				height="512"
				decoding="async"
				fetchpriority="high"
			/>
		</div>
	</div>
	<div>
		<p class="note mx-auto md:mx-0">
			Student researcher from India <span class="note-flag">🇮🇳</span>
		</p>
		<h1 class="name text-center md:text-left" aria-label="Hi, I'm Anya">
			{#each ['Hi,', "I'm", 'Anya'] as word, i}<span
					class="word"
					style="--i: {i}"
					aria-hidden="true">{word}</span
				>{' '}{/each}
		</h1>
		<p class="bio max-w-xl text-sm md:text-base">
			<strong>AI/ML researcher</strong> and student researcher at <Link
				inline
				href="https://github.com/Under-Research-Labs">Under Research Labs</Link
			>, focusing on foundation-model systems and agent reasoning. Born and raised in 🇮🇳, based in
			🇬🇧 (remote). Outside of work: open-source AI, reading papers and anime.
		</p>
	</div>
</div>

<Projects>
	<Project emoji="🛡️" title="CONTINUUM" href="https://github.com/Under-Research-Labs/CONTINUUM">
		Verifiable semantic recovery for long-running AI agents. Features semantic checkpoints, an
		idempotent action ledger that refuses duplicate side effects, and a tamper-evident event log
		exposed as a deny-by-default MCP server. Published as <Link
			inline
			href="https://pypi.org/project/continuum-agent/">continuum-agent</Link
		> on PyPI with a live <Link inline href="https://continuum-nu-six.vercel.app/"
			>web dashboard</Link
		>.
	</Project>
	<Project emoji="📡" title="SNAGLINE" href="https://github.com/Under-Research-Labs/SNAGLINE">
		Lightweight, dependency-free real-time failure detection for AI agents. Monitors execution
		streams and flags loops, error cascades, and latency anomalies with a hard fail-open guarantee
		at microsecond-scale overhead (~1.5 µs/step). Zero dependencies, streaming-first architecture.
	</Project>
	<Project
		emoji="⚡"
		title="snapjudge"
		description="Fast, non-autoregressive decision engine in pure C++17 with mathematically calibrated probabilities. Answers typed questions in a single forward pass without generating text or hallucinating."
		href="https://github.com/Cyrax321/snapjudge"
	/>
	<div slot="more" class="space-y-6">
		<Project
			emoji="🔍"
			title="QwerySmith"
			description="Open text-to-SQL models answering from retrieved evidence with machine-verifiable citations, alongside an automated harness that trains (Qwen3-8B QLoRA), evaluates, and releases models to Hugging Face."
			href="https://github.com/Cyrax321/QwerySmith-1.0"
		/>
		<Project emoji="🧸" title="Twinkie-2B" href="https://huggingface.co/Cyrax321/twinkie-2b">
			Child-safe conversational AI learning assistant fine-tuned on Qwen3.5-2B using Unsloth.
			Features an audited, fail-closed safety harness and achieves 100% emergency helpline
			escalation routing across evaluated crisis scenarios.
		</Project>
	</div>
</Projects>

<WorkExperiences>
	<WorkExperience
		company="Under Research Labs"
		period="2024 - Present"
		location="United Kingdom · Remote"
		logo={underResearchLogo}
	>
		<p>
			Conducting AI/ML research on foundation-model systems, agentic reasoning, and verifiable
			execution. Designing reliable reasoning and tool-augmented inference architectures for
			autonomous agents.
		</p>
		<p>
			Contributing to <Link inline href="https://github.com/Under-Research-Labs/CONTINUUM"
				>CONTINUUM</Link
			>, developing verifiable semantic checkpoints, idempotent action ledgers, and tamper-evident
			event logs for crash recovery and durable execution across agent frameworks.
		</p>
		<p>
			Developing <Link inline href="https://github.com/Under-Research-Labs/SNAGLINE">SNAGLINE</Link
			>, a zero-dependency real-time failure monitor detecting execution loops, cascading errors,
			and latency anomalies with microsecond-level overhead.
		</p>
	</WorkExperience>
	<WorkExperience
		company="Independent Research"
		period="2023 - Present"
		location="India · Remote"
		logo={independentResearchLogo}
	>
		<p>
			Conducting independent research on reliable AI systems, non-autoregressive decision models,
			and verifiable agent execution.
		</p>
		<p>
			Architected and developed <Link inline href="https://github.com/Cyrax321/snapjudge"
				>snapjudge</Link
			>, a fast, self-contained decision engine in C++17 with mathematically calibrated
			probabilities that answers typed questions in a single forward pass without hallucinating.
		</p>
		<p>
			Built <Link inline href="https://github.com/Cyrax321/QwerySmith-1.0">QwerySmith</Link> (open text-to-SQL
			models answering from retrieved evidence with machine-verifiable citations) and trained <Link
				inline
				href="https://huggingface.co/Cyrax321/twinkie-2b">Twinkie-2B</Link
			>, a child-safe learning assistant fine-tuned on Qwen3.5-2B with 100% emergency helpline
			escalation routing.
		</p>
	</WorkExperience>
</WorkExperiences>

<Card title="📫 Contact me">
	<p>
		Check out my <Link href="https://github.com/anya-research">GitHub</Link>, <Link
			href="https://x.com/anya_research">Twitter</Link
		>, or <Link href="https://linkedin.com/in/anya-aggarwal">LinkedIn</Link> profile
	</p>
	<p>
		Or reach me via <Link href="mailto:aggarwal31317@gmail.com">aggarwal31317@gmail.com</Link>
	</p>

	<div slot="footer" class="hidden md:block absolute inset-0 pointer-events-none">
		<span class="emoji" style="top: -15px; right: 20px;">🔬</span>
		<span class="emoji" style="top: 25px; right: 70px;">🤖</span>
		<span class="emoji" style="top: 65px; right: 120px;">💡</span>
		<span class="emoji" style="top: 105px; right: 170px;">⚡</span>
		<!--Second row-->
		<span class="emoji" style="top: 40px; right: -10px;">📚</span>
		<span class="emoji" style="top: 80px; right: 40px;">✨</span>
		<span class="emoji" style="top: 120px; right: 90px;">🔥</span>
		<span class="emoji" style="top: 105px; right: 170px;">🧠</span>
		<!--Third row-->
		<span class="emoji" style="top: 95px; right: -20px;">🇮🇳</span>
		<span class="emoji" style="top: 135px; right: 30px;">💻</span>
	</div>
</Card>

<style>
	.emoji {
		position: absolute;
		font-size: 2.6rem;
		pointer-events: none;
	}

	.note {
		width: fit-content;
		font-family: 'Caveat', cursive;
		font-size: 1.5rem;
		line-height: 1.2;
		color: #737373;
		rotate: -2deg;
		transform-origin: left center;
	}

	.note-flag {
		margin-inline: 0.1em 0.15em;
		font-size: 0.8em;
	}

	.name {
		margin: 0.375rem 0 1.25rem;
		font-family: 'Fraunces', Georgia, serif;
		font-size: clamp(3.25rem, 8vw, 4.75rem);
		font-weight: 400;
		line-height: 1;
		letter-spacing: -0.03em;
		font-variation-settings: 'opsz' 144;
	}

	.bio {
		line-height: 1.7;
		color: #525252;
	}

	.bio strong {
		color: #18181b;
	}

	/* Entrance: memoji, then the handwritten line writes itself, then the name, bio and cards */
	@media (prefers-reduced-motion: no-preference) {
		.memoji {
			animation: appear calc(0.8s / 1.3 / 1.2) cubic-bezier(0.2, 0.8, 0.2, 1) both;
		}

		.note {
			mask-image: linear-gradient(90deg, #000 40%, transparent 60%);
			mask-size: 250% 100%;
			animation: write calc(1.1s / 1.3 / 1.2) ease-in-out calc(0.25s / 1.3 / 1.2) both;
		}

		.note-flag {
			display: inline-block;
			animation: pop calc(0.5s / 1.3 / 1.2) cubic-bezier(0.3, 1.6, 0.5, 1) calc(1.2s / 1.3 / 1.2)
				both;
		}

		.word {
			display: inline-block;
			animation: rise calc(0.8s / 1.3 / 1.2) cubic-bezier(0.2, 0.8, 0.2, 1) both;
			animation-delay: calc((0.45s + var(--i) * 0.12s) / 1.3 / 1.2);
		}

		.bio {
			animation: fade-up calc(0.7s / 1.3 / 1.2) ease-out calc(0.95s / 1.3 / 1.2) both;
		}

		.intro + :global(.card) {
			animation: settle calc(0.9s / 1.3 / 1.2) cubic-bezier(0.2, 0.8, 0.2, 1)
				calc(1.15s / 1.3 / 1.2) both;
		}
	}

	@keyframes appear {
		from {
			opacity: 0;
			scale: 0.9;
		}
	}

	@keyframes write {
		from {
			mask-position: 100% 0;
		}
		to {
			mask-position: 0 0;
		}
	}

	@keyframes pop {
		from {
			scale: 0;
		}
	}

	@keyframes rise {
		from {
			opacity: 0;
			translate: 0 0.3em;
			filter: blur(10px);
		}
	}

	@keyframes fade-up {
		from {
			opacity: 0;
			translate: 0 8px;
		}
	}

	@keyframes -global-settle {
		from {
			opacity: 0;
			translate: 0 32px;
			scale: 0.98;
		}
	}

	@media (prefers-color-scheme: dark) {
		.note {
			color: #9a9a9a;
		}

		.bio {
			color: #c4c4c4;
		}

		.bio strong {
			color: #e8e8e8;
		}
	}
</style>
