AAIS — Adaptive Assistant Intelligence System
Behavior enforced, not implied.

AAIS is a local‑first, law‑governed assistant runtime.
It does not rely on “model vibes,” hidden heuristics, or implicit trust.
Every request, every decision, every reroute is explicit, visible, and accountable.

AAIS is built for environments where behavior matters more than output.

Why AAIS Exists
Most assistant systems optimize for answers.
AAIS optimizes for behavior.

One clear operating contract per turn

No silent reroutes or hidden fallbacks

Risky or experimental work is isolated from normal work

Operator control is preserved, not abstracted away

Every decision leaves a signed, time‑bound trace

The doctrine is simple:

Stabilize and Free  
Stability before freedom.
The system earns more responsibility by staying inside clear rules, explaining its behavior, and failing in a controlled way.

If it cannot do that, it slows down, asks for confirmation, or stops.

Quick Start
bash
pip install -e .
python -m aais start --data-dir ./.runtime/aais-data
Then open:

Surface	URL
App	http://127.0.0.1:8000/app
Jarvis Console	http://127.0.0.1:8000/app/jarvis
Health	http://127.0.0.1:8000/health


Optional preflight:

bash
python -m aais prepare --force-build --data-dir ./.runtime/aais-data
python -m aais doctor --data-dir ./.runtime/aais-data
Frontend dev server:

bash
cd frontend
npm install
npm run dev
Surfaces:
localhost:3000/jarvis, localhost:3000/workbench, localhost:3000/memory

Requirements
Use requirements.txt for standard local setup.

Other files:

File	Purpose
requirements-local.txt	Local dev extras
requirements-laptop.txt	Constrained/laptop env
requirements-advanced.txt	Full feature set
requirements-training.txt	Training pipeline only


Optional: Claude Provider
bash
export ANTHROPIC_API_KEY=your_key
export AAIS_CLAUDE_MODEL=claude-sonnet-4-20250514
export AAIS_ENABLE_CLAUDE_AUTO_ROUTING=true
Or pin Claude via provider_mode=claude_first.

Architecture Overview
AAIS is a governed stack, not a single service.
Every request moves through a fixed, law‑bound path:

Code
Client
  → Bridge / Jarvis
  → Forge / OTEM / Workflows
  → Core Runtime
  → Evolve Engine
  → Storage / Providers
1. Ingress Layer — Bridge / Jarvis
All input enters through a bridge‑enforced lane

Requests are classified and checked against project law

Fail‑closed by default

Every decision is signed and time‑bound

Shows why something was admitted, downgraded, or blocked

This is the system’s front door and primary safety boundary.

2. Dispatch Layer — Forge / OTEM / Workflows
Forge — isolated contractor lane for code execution

OTEM — bounded task + memory support

Workflows — packaged app routes

Normal work and risky work are separated by design.

3. Core Runtime — aais/, engine/, evolve_engine/
The runtime enforces:

Turn contracts

Invariants

Role boundaries

Continuity

Traceability

The Evolve Engine learns from outcomes but cannot rewrite roles or law.

4. Memory, Providers, and Subsystems
Memory is governed and bounded

Providers (LLMs, tools, APIs) are routed through controlled interfaces

Subsystems (e.g., Nova) are admitted only through documented contracts

Nothing is “plug and play.”
Everything is documented, traced, and law‑bound.

5. Surfaces — frontend/, mobile/, api/
Thin shells over the governed runtime:

Web app

Mobile app

API

They expose behavior; they do not define it.

Documentation Spine
Authoritative system understanding lives in:

docs/spine/ — canonical reading path

docs/runtime/ — runtime maps and system references

docs/contracts/ — laws, protocols, doctrine

docs/subsystems/ — admitted subsystem packs

docs/audit/ — coverage and status records

docs/_archive/ and docs/_future/ are non‑authoritative.

Repository Structure
Code
aais/                  Core runtime
api/                   API surface
app/                   Packaged shell + workflows
src/                   Entry points (jarvis_operator.py, api.py)
docs/
  spine/               Canonical explanation
  runtime/             System references
  contracts/           Laws + contracts
  subsystems/          Subsystem packs
  audit/               Status + coverage
  _archive/            Lineage (not active)
  _future/             Planned (not active)
engine/                Foundation layer
forge/                 Bounded contractor lane
evolve_engine/         Outcome-based adaptation
evals/                 Evaluation harness
tests/                 Full test suite
frontend/              Web app
mobile/                Expo mobile app
training/              Training pipeline
Only docs/ (excluding _archive/ and _future/) is authoritative.

Key Internal Layers
Layer	Role
Jarvis	Main authority lane — ingress + runtime control
Forge	Isolated contractor lane for code execution
OTEM	Task + memory support
Workflow Shell	App route layer
Evolve Engine	Learns from outcomes (within bounds)


Cognitive Architecture
Unified Architectural Hyper‑Systemizer  
Formal specification of the cognitive engine behind Project Infinity (May 5, 2026).
(See linked Zenodo document.)

Project Laws
Document	Governs
README Law v1	Documentation rules
External Suggestion Admission	How external input enters the system
ARIS Runtime Contract	Embedded repo‑intelligence law
Cognitive Bridge Runtime Law	Ingress + attestation rules
REPO_LAWBOOK.md	Full repo operating law


Points of Interest
AAIS contains deeper layers for those who explore:

Internal architecture layers — nested subsystems, lineage, early doctrine

Foundation artifacts — structural invariants, long‑term stability markers

Historical documents — evolution of the system’s philosophy

Compiler‑like behavior — introspective metadata and narrative traces

These are optional and not required for running the system.

Security
See SECURITY.md for disclosure policy.

License
Apache 2.0
