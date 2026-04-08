# OrbitFlare Infra Accelerator Program

**Devnet to Mainnet - 4-Week Intensive**

The OrbitFlare Infra Accelerator helps early-stage Solana teams move from devnet prototypes to production-ready mainnet deployments.

Teams receive hands-on infrastructure support, direct access to OrbitFlare engineers, and the resources required to launch reliable on-chain products using high-performance OrbitFlare RPC and data infrastructure.

---

- [What We Provide](#what-we-provide)
- [Eligibility](#eligibility)
- [How to Apply](#how-to-apply)
- [Application Review](#application-review)
- [Program Structure](#program-structure)
- [After the Program](#after-the-program)
- [Guidelines](#guidelines)
- [Resources](#resources)

---

## What We Provide

### RPC Credits

Every team receives a customized OrbitFlare RPC plan tailored to their project's needs. A high-throughput trading engine has very different RPC requirements than a social application with occasional on-chain writes, and the plans reflect that. Teams do not need to worry about rate limits or credits running out during development sprints.

Access extends 5 days beyond the end of the program to support the launch window. Accelerator teams also receive discounted pricing on OrbitFlare services should they choose to continue using the infrastructure post-program.

### Developer Advisory

Teams receive direct access to OrbitFlare engineers for guidance on infrastructure integration, architecture decisions, and RPC-related questions.

Topics we can support include:

- RPC integration patterns and best practices
- Transaction reliability (retry logic, confirmation strategies, priority fees)
- On-chain program architecture guidance
- Indexing and data pipeline design
- Security considerations for mainnet deployment
- Infrastructure setup (monitoring, alerting, failover)

### Ideation Support

Some projects need to refine their product direction before shipping. We help teams think through:

- Feature prioritization for a mainnet MVP
- User flow design and onboarding friction
- Monetization and sustainability
- Ecosystem positioning within the broader Solana landscape

### Twice-Weekly Check-ins

Each team receives two 30-minute check-ins per week (Tuesdays and Fridays). These meetings exist to unblock teams quickly, not to create process overhead.

If a team encounters a critical blocker between meetings, async support via the shared channel is always available.

### Public Recognition and Ecosystem Visibility

OrbitFlare supports teams not only through infrastructure but also by helping them gain visibility within the Solana ecosystem. Teams are encouraged to speak openly about their experience building with OrbitFlare and the role it played in their path from devnet to mainnet.

---

## Eligibility

To be eligible for the OrbitFlare Infra Accelerator, your project must meet the following criteria:

- **Solana-native** - Your project must be built on Solana.
- **Pre-mainnet** - Your project has not yet launched on Solana mainnet. Devnet or testnet prototypes are expected.
- **Working prototype** - You must have a functional devnet prototype or proof of concept. We do not accept idea-stage applications.
- **Committed team** - At least one team member must be able to dedicate significant time to development during the 4-week program.
- **Open to feedback** - Teams must be willing to participate in architecture reviews, security reviews, and twice-weekly check-ins.
- **Public launch intent** - Teams must intend to publicly launch their product and share the deployment journey with the ecosystem.

### What we do NOT fund or support

- Projects that have already launched on mainnet
- Token launches or fundraising activities
- Projects with no working code
- Marketing-only initiatives
- Projects not building on Solana

---

## How to Apply

1. **Fork this repository.**

2. **Copy the application template.**
   Create a copy of [`applications/application-template.md`](applications/application-template.md).
   Rename it to `applications/your_project_name.md`.

3. **Fill out the application.**
   Complete every section of the template. Applications with incomplete sections will not be reviewed.
   See the [Application Guidelines](docs/application-guidelines.md) for detailed instructions on what we look for.

4. **Submit a Pull Request.**
   Open a PR against this repository containing only your application file.
   Use the PR template provided - it will guide you through the submission checklist.

5. **Review period.**
   The OrbitFlare team will review your application and may request changes or additional information via PR comments. Respond to feedback within **7 days** or your application will be closed.

6. **Acceptance.**
   Accepted applications are merged into the repository. You will be contacted directly to begin onboarding.

> **Tip**: Look at previously accepted applications in the [`applications/`](applications/) directory for reference.

---

## Application Review

Applications are evaluated on the following criteria:

| Criteria | What We Look For |
|---|---|
| **Technical Readiness** | Working devnet prototype, clean codebase, clear architecture |
| **Team** | Relevant experience, active GitHub profiles, ability to commit time |
| **Problem and Solution** | Clear problem statement, differentiated approach, real user need |
| **Mainnet Path** | Realistic assessment of what's needed to reach mainnet in 4 weeks |
| **Ecosystem Value** | Contribution to the Solana ecosystem, potential user base |
| **Infrastructure Fit** | Clear need for RPC infrastructure, data streaming, or transaction reliability |

Applications are reviewed on a rolling basis. We aim to respond within **2 weeks** of submission.

---

## Program Structure

| Week | Focus | Key Deliverable |
|---|---|---|
| **1** | Assessment and Planning | Mainnet blockers identified, milestones defined |
| **2** | Core Development Sprint | OrbitFlare RPC integrated, blockers resolved |
| **3** | Hardening and Testing | Stress testing complete, security review done |
| **4** | Mainnet Deployment and Launch | Live mainnet launch |

For a detailed breakdown of each week, see the [Program Structure](docs/program-structure.md) document.

---

## After the Program

By the end of Week 4, each team is expected to have:

- A working product deployed on Solana mainnet
- OrbitFlare RPC running in production
- Monitoring in place to respond to production issues independently
- A clear roadmap beyond the accelerator
- A public launch announcement acknowledging the infrastructure powering the deployment

Teams that complete the program receive:

- Continued discounted access to OrbitFlare infrastructure
- Inclusion in the Cohort Launch Announcement
- Introductions to relevant ecosystem partners where appropriate

---

## Guidelines

- [Application Guidelines](docs/application-guidelines.md) - Detailed guidance on writing a strong application
- [Program Structure](docs/program-structure.md) - Week-by-week breakdown of the program
- [Announcement Guidelines](docs/announcement-guidelines.md) - How to announce your participation and launch

---

## Resources

- [OrbitFlare Documentation](https://docs.orbitflare.com)
- [Application Template](applications/application-template.md)

---

## Questions?

If you have questions about the program or the application process, [open an issue](/orbitflare/infra-accelerator/issues/new?template=question.yml) in this repository.
