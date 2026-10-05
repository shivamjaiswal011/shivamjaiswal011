## Shivam Jaiswal

FullStack and platform engineer — Go, Java, PostgreSQL, Angular. I build and run
[Tracktions](https://tracktions.com) solo, and work on internal AI developer
tooling at BNY.

### Tracktions — founder, sole engineer

A trading journal platform for Indian retail traders on NSE/BSE. I built the
whole thing: Go/Gin API on PostgreSQL, Angular 20 frontend, deployed on AWS.

Some decisions I'd defend:

- **Server-sent events, not WebSockets.** Trade imports are long-running jobs
  and progress is strictly server-to-client. SSE gave me streaming progress over
  plain HTTP with no extra protocol surface to secure or scale.
- **Dropped Redis for an in-memory job queue.** Redis was doing job queuing and
  little else — one more stateful service to run, monitor and pay for. Moving
  the queue in-process removed a whole moving part with no loss in throughput at
  current volume, and it's a decision I know how to reverse when it stops
  holding.
- **Direct broker sync over manual entry.** Four live broker integrations —
  Zerodha, Upstox, Dhan and Fyers — plus CSV/Excel import, because the fastest
  way to kill a journaling habit is to make people type their trades in twice.

Also: Razorpay subscription billing, AWS SES/S3/CloudWatch, JWT cookie sessions,
35 schema migrations, ~350 Go files. Closed source — happy to walk through any
of it.

### At BNY

Internal AI developer tooling — an air-gapped marketplace for configurable AI
skills and MCP servers, and a multi-agent LLM pipeline that automates UAT across
our ODS datasets and microservices. Enterprise code, so none of it is public.

### Writing

**[tracktions-architecture](https://github.com/shivamjaiswal011/tracktions-architecture)**
— the decisions behind the system above, each with the condition that would
reverse it. Why SSE and not WebSockets, why Redis got deleted rather than grown,
where the design runs out of room.

**[codebase-context-pilot](https://github.com/shivamjaiswal011/codebase-context-pilot)**
— I built a code-graph context system to make coding agents cheaper on a
354-file Go codebase, wrote the pass/fail rule before collecting any data,
measured it across 10 tasks, and shut it down when it missed. The repo is the
full record: methodology, numbers, the two measurement bugs that invalidated the
first pass, and what I'd try next. Verdict was no-go; the interesting parts are
why, and the one task shape where it won decisively.

### Also here

**[OneHealth](https://github.com/shivamjaiswal011/health-app)**
— an offline-first training and nutrition tracker built for my own gym and diet.
No server, no account; everything is computed and stored on the phone. Indian
food database with household portions, progressive-overload challenge mode,
308 tests. React Native / Expo.

**[Competitive-Coding-From-scratch](https://github.com/shivamjaiswal011/Competitive-Coding-From-scratch)**
— competitive programming resources and solutions collected while learning.
Still the most useful thing I've published, judging by the stars.

### Stack

Go · Java / Spring Boot · TypeScript · PostgreSQL · Angular · AWS · Docker · CI/CD
LLM orchestration · multi-agent systems · MCP

[tracktions.com](https://tracktions.com) · [LinkedIn](https://www.linkedin.com/in/shivam-jaiswal-556059170/)
