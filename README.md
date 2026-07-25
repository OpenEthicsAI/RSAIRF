# Really Simple AI Risk Framework (RSAIRF)

**Really Simple AI Risk Framework** is your go to tool to identify and mitigate AI/ML-specific risks. The AI Risk Register of this framework is carefully curated based on various sources and internal incident learnings of our clients.

[![RSAIRF](https://img.shields.io/badge/Open%20Ethics-RSAIRF-blue?style=flat-square&logo=github)](https://github.com/OpenEthicsAI/RSAIRF)

## AI Lifecycle

Every AI initiative moves through lifecycle stages such as Development, Deployment, Use, and Monitoring. Not every organization develops AI models, but all AI initiatives involve Deployment and Use. Gaps in Monitoring and shadow Deployments are common sources of risk.

```mermaid
flowchart TB
	subgraph system_design[System Design]
		development_stage[Model Development] --> deployment_stage[Model/Component Deployment]
		deployment_stage --> use_stage[AI Use]
		monitoring_stage((Continuous\nMonitoring and Evaluation))
		development_stage -.-> monitoring_stage
		deployment_stage -.-> monitoring_stage
		use_stage -.-> monitoring_stage
		monitoring_stage -.-> development_stage
		monitoring_stage -.-> deployment_stage
		monitoring_stage -.-> use_stage
	end

	classDef development fill:#ffe6cc,stroke:#b85c00,color:#222;
	classDef nonDevelopment fill:#d9f0ff,stroke:#1f6fa8,color:#222;
	class development_stage development;
	class deployment_stage,use_stage,monitoring_stage nonDevelopment;
```

- **Development**: You design or materially change AI behavior (for example, selecting data, training, tuning, evaluation).
- **Deployment**: You do not build the model, but you integrate, configure, and release AI components into production workflows.
- **Use**: You consume a deployed AI solution in business operations and make decisions or actions based on its outputs (via chat, CLI, or another interface).
- **Monitoring**: You track risk, quality, and incidents over time; this is continuous and should run across all other stages.



## How to use this framework?

```mermaid
flowchart TD
	start((Start))
	step1[1. Check which lifecycle stages are applicable for your initiative]
	step2[2. Map risks using register.csv]
	step3[3. For each applicable AIR## risk, record likelihood, impact, responsible, and mitigation]
	missing_risk{Missing risk in register.csv?}
	step5[Create repository issue with the missing risk]
	stop_check{Any new stage transition or newly in-scope risk?}
	end_node((End))

	start --> step1 --> step2 --> step3 --> missing_risk
	missing_risk -- Yes --> step5 --> stop_check
	missing_risk -- No --> stop_check
	stop_check -- Yes --> step1
	stop_check -- No --> end_node

	classDef core fill:#e9f7ef,stroke:#2e8b57,color:#1f2937;
	classDef governance fill:#e8f1ff,stroke:#2563eb,color:#1f2937;
	classDef startNode fill:#fee2e2,stroke:#dc2626,color:#7f1d1d;
	classDef endNode fill:#dcfce7,stroke:#16a34a,color:#14532d;
	classDef decision fill:#fff7ed,stroke:#c2410c,color:#1f2937;
	class step1,step2,step3 core;
	class step5 governance;
	class start startNode;
	class end_node endNode;
	class missing_risk,stop_check decision;
```

1. Check which lifecycle stages are applicable for your initiative. If unclear, run a discovery session with your technical team.
2. For the stage(s) your initiative is currently in, consult the [register.csv](./register.csv). Stage tags in the risk register indicate where each risk is typically introduced or first exploitable. Several risks span more than one stage and are tagged accordingly.
3. For every risk that applies to your system, record: likelihood, impact, an owner, and a mitigation or control. Reference risks by their AIR## ID in your project’s risk log, security review, or audit so findings stay traceable back to this register. “AIR” stands for AI Risk.

> Re-check the register at each stage transition (e.g., moving from Development to Deployment) — a risk that was out of scope earlier may now apply.

> Treat this as a living list: if you identify a risk not represented here, propose it by [creating an issue](https://github.com/OpenEthicsAI/RSAIRF/issues/new) in this repository, your contribution may help other teams.

## License

This work is licensed under the Creative Commons Attribution 4.0
International License [CC BY 4.0](./LICENSE).
