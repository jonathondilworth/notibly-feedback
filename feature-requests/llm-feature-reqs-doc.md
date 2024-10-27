# Self-Hosting Feature Requests Service

### Introduction

After reviewing tools like [https://features.vote](https://features.vote), I wanted to explore similar software options for gathering feature requests. These tools are useful for any product-driven project, but subscription costs are high for solo developers (up to ~\$350/year). Self-hosting can drastically reduce costs, so I investigated open-source alternatives that could be run on personal or cloud-based infrastructure.

### Findings

There are a few promising self-hosted tools worth exploring as alternatives to commercial products. Here’s a summary of my findings:

* ClearFlask
	* URL: [https://clearflask.com/](https://clearflask.com/)
	* GitHub URL:
	* Cost: $9/month (optional license fee).
	* Tech Stack: Written in Java, uses Tomcat, with substantial dependencies.
	* Setup: Complicated, with a detailed setup guide that implies potential points of failure.
	* Conclusion: Functional but requires Java familiarity for modifications.

* Fider
	* URL: [https://fider.io/](https://fider.io/)
	* GitHub URL:
	* Cost: Free and fully open-source.
	* Tech Stack: Runs on Docker, easily configured with NGINX and SSL via Let’s Encrypt.
	* UX: Simple but somewhat outdated in aesthetics.
	* Conclusion: Good for quick deployment; front end uses React, TypeScript, and SASS, making customization feasible.

* UseFeedback
	* Project URL: [https://usefeedback.vercel.app/](https://usefeedback.vercel.app/)
	* GitHub URL: [https://github.com/Munadil16/use-feedback](https://github.com/Munadil16/use-feedback)
	* Cost: Free.
	* Tech Stack: Built with Next.js, TypeScript, and Tailwind CSS.
	* Conclusion: Designed for testimonials but could be adapted for feature requests. See GitHub - UseFeedback for the source.

* NHS Open-Source Feedback Tools & User Feedback Store
	* Project URL: 
	* GitHub URL:
	* Conclusion: Complicated setup, many issues. Not recommended without significant modification.

* Planka
	* Project URL:
	* GitHub URL:
	* Purpose: Kanban-style project management.
	* Conclusion: Usable for organizing feedback but not optimized for feature requests.

* Open Feedback
	* Project URL: 
	* GitHub URL:
	* Conclusion: Looks promising but requires further exploration.

* GitHub Discussions
	* Conclusion: Suitable for developers using GitHub, though lacks non-developer accessibility.

Comparison with features.vote

Most open-source solutions lack the polish and simplicity of features.vote, which, despite a $99 lifetime license option, is still under development. While feature-rich and minimal, it may lack the robustness of other tools that are more battle-tested.

Conclusions

If you’re looking to avoid commercial licensing fees, here are some recommended actions:

	1.	Consider UseFeedback: Great for testimonials but could be adapted to handle feature requests with some modifications.
	2.	Deploy Fider: Simple setup, free, and customizable, making it a good choice for non-developer feedback.
	3.	GitHub for Developer Projects: GitHub Discussions works well for open-source projects and developer-oriented feedback.

If open-source isn’t a necessity, features.vote offers great value, and Supahub provides more features at a premium.

Summary:

	•	features.vote: Promising tool in active development; $99 lifetime license available.
	•	UseFeedback: Adaptable for collecting feedback and testimonials.
	•	Fider: Free, straightforward deployment.
	•	Paid options:
	•	Supahub (recommended for premium features)
	•	featurefind.io
	•	nolt.io

This is a concise version based on my research and recommendations.

