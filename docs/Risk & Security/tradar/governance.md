---
title: Governance
deprecated: false
hidden: false
metadata:
  robots: index
---
As tRadar evolves into a more decentralized network, governance – the process by which decisions are made and new participants join – becomes crucial. The **governance model** of tRadar will dictate how the rules of the system can change, how validators are added or removed, and how stakeholders (like token holders, developers, users) have a say in the security framework that guards their transactions.

<br />

**Onboarding New Validators:** In the early stages, tRadar’s validator set may be relatively small and curated (for example, run by t54 Labs and close partners using different AI models for diversity). However, the goal is to open the network to **new validators** – including community-run nodes, third-party security firms, or even other AI developers – who want to contribute their expertise and earn rewards. Onboarding a new validator could follow a process such as:

1. **Application or Proposal:** A prospective validator operator signals interest. This could be as simple as staking a required minimum amount of tokens and broadcasting a “join” transaction, or submitting a proposal to the governance forum if the network is permissioned at that time.
2. **Qualification:** Certain criteria might need to be met. For example, the operator should demonstrate they have the technical infrastructure to run a validator (reliable servers, perhaps GPU capability for AI models, etc.), and that their validator agent (the AI model or rule set they’ll run) meets the network’s standards. There might be a testing period where the new validator runs in parallel (shadow mode) to prove it can make sound judgments in line with existing validators.
3. **Approval:** If the network is still somewhat permissioned, existing governance (the current validators or the core team) might vote to approve the new validator. In a future decentralized scenario, this could be a token-holder vote or automatic if criteria are met (permissionless but with strict slashing conditions for misbehavior). The approval could also determine an initial weight for the validator (for instance, new validators might start with a lower weight that increases as they build performance history).
4. **Staking:** The new validator operator will need to lock up the required stake (a security deposit in tokens). Additionally, if they have supporters (delegators), those delegators can start staking to the new validator, boosting its weight. This stake is a guarantee of honest behavior.
5. **Onboarding Complete:** Once approved and staked, the sequencer (or decentralized equivalent) starts including the new validator in the consensus process. The new validator will receive tasks, vote on transactions, earn rewards, etc., just like others.

<br />

**Governance Mechanisms:** Changes to tRadar’s policies – whether it’s risk rule adjustments, parameter tuning (like quorum thresholds, reward rates), or significant upgrades – will likely be governed by a combination of the t54 team and the community. Early on, governance might be more centralized (the core developers can push updates, since the network is in a nascent state). But the vision would be to move to something like a **DAO (Decentralized Autonomous Organization)** model, where token holders or stakeholders can propose and vote on changes.

Key governance topics include:

* **Risk Rule Updates:** As new threats emerge or false positives are identified, rules may need tweaking. A governance process can allow proposing a new rule (e.g., “ban transactions to X exchange if flagged by regulators”) or changing a limit (e.g., raising the daily limit for trusted agents). Validators themselves could vote on these proposals, or a broader token-holder vote could decide.
* **Validator Set Changes:** Removing a validator is as important as adding one. If a validator is proven malicious or frequently underperforming, governance may decide to eject it (slashing its stake heavily as a penalty). Similarly, adding new validators beyond a certain limit might require community agreement to ensure the network doesn’t get diluted with low-quality validators.
* **Protocol Upgrades:** This covers anything from changing the consensus algorithm, altering the reward/slash mechanism, or integrating with other networks. For example, if tRadar wanted to integrate zero-knowledge proofs for privacy in validation, that would be a major upgrade requiring stakeholder buy-in.
* **Treasury and Funding:** If there is a community treasury (funded by some portion of fees or token inflation), governance would decide how to allocate those funds – perhaps to bug bounties, validator subsidies, grants for research (like improving validator AI models), etc.

<br />

The governance structure could involve a **multi-tier model**: perhaps an elected council of expert validators for fast operational tweaks, and a wider token holder referendum system for big changes. The specifics are likely to be detailed in the platform’s governance whitepaper. For the purpose of this overview, the main point is that **governance ensures tRadar remains adaptive and community-aligned**. The stakeholders who rely on tRadar’s protection (developers, users, partners) will have avenues to influence its evolution, making it a collectively owned security layer.

<br />

**Ease of Onboarding vs. Security:** One challenge in any such system is balancing openness with security. If literally anyone could plug in a validator agent with no oversight, a malicious actor might try to join with an agent that rubber-stamps all risky transactions (to help attackers) or attempts to disrupt consensus. That’s why even in a decentralized future, certain safeguards will exist:

* New validators might be added gradually, and possibly start in a probation period with limited influence.
* There could be a requirement to run known validation models or at least open ones (so the community can audit what logic a validator agent uses). Alternatively, diversity of AI models is good, but a validator could be required to periodically undergo evaluation on a set of test scenarios to ensure its quality.
* The staking mechanism naturally provides some protection: an attacker would have to put up significant capital to gain influence, and they risk losing it all if they misbehave.

<br />

Over time, as trust in the system grows, onboarding can become more permissionless because the economic deterrents (stake & slash) and the collective vigilance of other validators will guard the gates.

In summary, **governance and onboarding** in tRadar aim to create a **self-sustaining, open network** where the best security practices prevail. New validators bring more compute and ideas (in the form of their AI validators) into the system, but entry is gated by community approval and economic commitment to maintain quality. The governance process itself ensures that as the threat landscape shifts or as the platform’s needs change, tRadar’s policies and parameters can be updated in a transparent, organized manner with input from those it protects.