# technical-prose
Curb the graphomania of LLMs

## The problem

LLMs have a compulsion to write needlessly long prose in code comments above exported constants, function definitions, test fixtures, readmes, repeating the same thing over and over again, when a single short explanation stated once in the appropriate section of the documentation would suffice. LLMs are trained to produce long streams of text with flowery language, often using techniques to draw out the suspense. This is inappropriate for technical prose, but that's the training data we deal with. An ideal solution would be a model trained specifically to write decent technical literature, but such models aren't widely available and the average SWE with an AI just wants to ship his PR without leaving his Claude Code CLI. The word out on [the internets](https://www.reddit.com/r/PromptEngineering/comments/1tokx1h/i_tested_4_methods_to_make_llms_write_literary/) is that a manageable amount of positive examples beats elaborately designed skills with complex rules and counterexamples when trying to make a model do the opposite of what its training data dictates. This repository attempts to collect a number of such positive examples.

## Examples

A docstring above a named constant for a Kubernetes annotation key:

```go
	// AnnotationVPCIP is an annotation key holding a copy of the object's VPC IP.
	AnnotationVPCIP = "sdn.cozystack.io/vpc-ip"
```

## See also

[**dontyap**](https://github.com/lllamnyp/dontyap) -- deterministic tooling seems to be the most effective way to make an AI do what you want. There's plenty of linters for a minimum comment-to-code ratio. I made one that enforces a maximum.

[**AI-Driven Code Documentation: Comparative Evaluation of LLMs for Commit Message Generation**](https://www.mdpi.com/2073-431x/15/2/87) -- _A set of pilot experiments revealed that simple questions like “Summarize this diff”resulted in verbose and redundant responses lacking explicit explanation. Upon several rounds of tuning on the validation subset, the following final template instruction has been adopted:_

> _You are a senior software engineer. Write a short (<=12 words) Git commit message that clearly describes what changed and why._
