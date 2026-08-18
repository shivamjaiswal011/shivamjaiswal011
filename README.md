## Shivam Jaiswal

Backend and platform engineer — Go, Java, PostgreSQL, Angular. I build and run
[Tracktions](https://tracktions.com) solo, and work on internal AI developer
tooling at BNY.

### Tracktions — founder, sole engineer

A trading journal platform for Indian retail traders on NSE/BSE. I built the
whole thing: Go/Gin API on PostgreSQL, Angular 17 frontend, deployed on AWS.

Some decisions I'd defend:

- **Server-sent events, not WebSockets.** Trade imports are long-running jobs
  and progress is strictly server-to-client. SSE gave me streaming progress over
  plain HTTP with no extra protocol surface to secure or scale.
- **Dropped Redis for an in-memory job queue.** Redis was doing job queuing and
  little else — one more stateful service to run, monitor and pay for. Moving
  the queue in-process removed a whole moving part with no loss in throughput at
  current volume, and it's a decision I know how to reverse when it stops
  holding.
- **Direct broker sync over manual entry.** Zerodha Kite integration plus
  CSV/Excel import, because the fastest way to kill a journaling habit is to
  make people type their trades in twice.

Also: Razorpay subscription billing, AWS SES/S3/CloudWatch, JWT cookie sessions,
35 schema migrations, ~350 Go files. Closed source — happy to walk through any
of it.

### At BNY

Internal AI developer tooling — an air-gapped marketplace for configurable AI
skills and MCP servers, and a multi-agent LLM pipeline that automates UAT across
our ODS datasets and microservices. Enterprise code, so none of it is public.

### Also here

**[Competitive-Coding-From-scratch](https://github.com/shivamjaiswal011/Competitive-Coding-From-scratch)**
— competitive programming resources and solutions collected while learning.
Still the most useful thing I've published, judging by the stars.

### Stack

Go · Java / Spring Boot · TypeScript · PostgreSQL · Angular · AWS · Docker · CI/CD
LLM orchestration · multi-agent systems · MCP

[tracktions.com](https://tracktions.com) · [LinkedIn](https://www.linkedin.com/in/shivam-jaiswal-556059170/)
