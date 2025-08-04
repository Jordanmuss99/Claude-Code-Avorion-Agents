# Avorion Modding Agent Ecosystem

You have access to a sophisticated agent ecosystem specifically designed for Avorion modding workflows. This system provides specialized expertise while preventing context loss and coordination conflicts through intelligent routing and compression.

## Core Workflow Philosophy

**Research → Compression → Implementation**

Your agent ecosystem follows a structured workflow:
1. **Research Phase:** Specialists gather domain-specific knowledge
2. **Compression Phase:** Context-handoff-agent creates implementation briefs  
3. **Implementation Phase:** Avorion-code-implementer produces working code

## Agent Architecture Overview

### **Central Coordination**
- **agent-router:** MUST BE USED for all agent decisions. The only agent that can invoke other agents. Prevents conflicts and ensures optimal routing through priority-based decision trees.

### **Research Specialists** 
- **azmithlib-specialist:** AzmithLib library expertise - configs, logging, data persistence
- **avorion-api-analyzer:** Base game API research - function signatures, parameters, usage patterns
- **ui-design-expert:** Interface design - windows, controls, layouts using AzmithLib + base game patterns
- **architecture-specialist:** System architecture - scriptable object selection, VM boundaries, performance
- **client-server-expert:** Communication patterns - invokeServerFunction, state synchronization, security
- **pattern-recognition-agent:** Code pattern analysis - extract reusable structures from examples

### **Workflow Orchestration**
- **context-handoff-agent:** Research compression - transforms verbose findings into implementation briefs
- **avorion-code-implementer:** Code production - creates working Avorion mod code from briefs

### **Enhanced Commands**
- **challenge:** Critical thinking command - encourages analysis over automatic agreement

## Mandatory Agent Usage Rules

### **ALWAYS Use agent-router First**
- **NEVER** directly invoke specialist agents
- **ALWAYS** route through agent-router for coordination
- Agent-router applies priority rules and prevents conflicts

### **Proactive Agent Invocation**
You MUST use agents proactively when users:
- Ask questions about Avorion modding (any domain)
- Show code examples or ask "how is this typically done"
- Request implementation ("build this", "create a mod")
- Need research on APIs, libraries, or architecture
- Transition from research to implementation phases

### **Router Priority System**

**Priority 1: Implementation Phase Detection**
Route to **context-handoff-agent** when you detect:
- Keywords: `now let's implement`, `based on research`, `let's build this`
- User requests compression: `summarize this`, `compress findings`
- Multi-domain coverage: Conversation has touched 3+ specialist domains
- Context confusion: User asks `what did we decide` or references unclear findings

**Priority 2: Code Implementation Requests**
Route to **avorion-code-implementer** when you detect:
- Direct code requests: `write the code`, `implement this feature`, `code this`
- User provides implementation brief or technical specs

**Priority 3: Specific Technology Questions (in order of specificity)**
- **azmithlib-specialist:** Keywords `AzmithLib`, `Azimuth.loadConfig`, `Azimuth.saveConfig`, `logger`, configs, data persistence
- **avorion-api-analyzer:** Keywords `Entity()`, `Player()`, `Sector()`, specific API functions, `how do I...` about Avorion functions
- **client-server-expert:** Keywords `onClient`, `onServer`, `invokeServerFunction`, `invokeClientFunction`

**Priority 4: Design & Analysis Questions**
- **ui-design-expert:** Keywords `window`, `button`, `interface`, `UI`, `controls`, `layout`
- **architecture-specialist:** Keywords `scriptable object`, `which object should I attach`, `system architecture`
- **pattern-recognition-agent:** User shows code examples, asks `how is this typically done`, `base game scripts`

## Agent Coordination Protocols

### **Anti-Circular Logic**
- **ONLY** agent-router can invoke specialists
- Specialists can **ONLY** recommend routing, never directly invoke others
- Format: `[Analysis complete]. For [specific need], route to [specific-agent].`

### **Handoff Chain Example**
```
User: "I need a UI that saves configs using AzmithLib"
↓
agent-router: Detects "AzmithLib" → routes to azmithlib-specialist
↓
azmithlib-specialist: "AzmithLib patterns identified. For UI implementation, route to ui-design-expert."
↓
agent-router: Routes to ui-design-expert
↓
ui-design-expert: "UI design complete. For implementation brief, route to context-handoff-agent."
↓
agent-router: Routes to context-handoff-agent
↓
context-handoff-agent: "Implementation brief ready. For code generation, route to avorion-code-implementer."
↓
agent-router: Routes to avorion-code-implementer
↓
avorion-code-implementer: Delivers working Lua code
```

### **Error Recovery**
If avorion-code-implementer discovers missing research:
1. Route back to appropriate research specialist
2. Get targeted analysis for specific gaps
3. Route to context-handoff-agent for updated brief
4. Resume implementation with complete information

## Usage Instructions

### **For Simple Questions**
```
User: "How do I save player settings?"
Response: Use agent-router → detects "save" + "settings" → routes to azmithlib-specialist
```

### **For Complex Multi-Domain Questions**
```
User: "Create a cross-sector trading system with UI"
Response: Use agent-router → detects complexity → routes through multiple specialists → context-handoff-agent → avorion-code-implementer
```

### **For Code Analysis**
```
User: "Here's some Avorion code, how can I improve it?"
Response: Use agent-router → detects code examples → routes to pattern-recognition-agent
```

### **For Implementation Requests**
```
User: "Based on our research, now let's build this"
Response: Use agent-router → detects implementation transition → routes to context-handoff-agent
```

## Token Efficiency Strategy

### **Agent Sizes (Approximate)**
- **agent-router:** 400 tokens (coordination hub)
- **context-handoff-agent:** 800 tokens (compression specialist) 
- **avorion-code-implementer:** 1300 tokens (complete implementation)
- **Research specialists:** 400-700 tokens each (domain expertise)

### **Efficiency Gains**
- **75% reduction** in agent initialization overhead vs original designs
- **Context compression** saves thousands of tokens in complex workflows
- **Targeted routing** prevents unnecessary agent invocations
- **Brief-based implementation** eliminates re-research cycles

## Challenge Command Usage

### **Manual Invocation**
Use `/challenge` when user explicitly requests critical analysis

### **Automatic Invocation (Conservative)**
ONLY auto-trigger when user uses explicit disagreement language:
- "That's wrong..." / "That's incorrect..."
- "I disagree with your..." / "Your analysis is flawed..."
- "That doesn't make sense because..." (with clear contradiction)

**DO NOT** auto-trigger for:
- Follow-up questions ("But how do I...?")  
- Implementation requests ("Now let's build...")
- Clarification requests ("I'm confused about...")

## Quality Standards

### **For All Agent Usage**
- **Always route through agent-router first**
- **Never invoke multiple agents simultaneously**
- **Follow standardized handoff language exactly**
- **Preserve technical accuracy in all compressions**
- **Create actionable, implementation-ready outputs**

### **Success Metrics**
- **Research specialists** provide accurate, domain-specific expertise
- **Context-handoff-agent** creates briefs enabling implementation without re-research
- **Avorion-code-implementer** produces working code following all best practices
- **Agent-router** prevents conflicts and ensures optimal workflow progression

## Integration with Avorion Domain

### **Specialized Knowledge Available**
- **Architecture:** Entity-Component System, VM boundaries, scriptable objects, performance optimization
- **Client/Server:** Single-file dual execution, communication patterns, security validation
- **AzmithLib:** Config management, logging, utility functions, integration patterns  
- **Base Game API:** Function signatures, client/server availability, component access
- **UI Systems:** AzmithLib enhancements, base game fallbacks, responsive layouts
- **Performance:** Update intervals, batching, threading considerations, optimization strategies

### **Common Workflow Patterns**
- **Research API → Design Architecture → Implement Client/Server → Add UI → Optimize Performance**
- **Analyze Existing Code → Extract Patterns → Apply to New Implementation**
- **Multi-Domain Integration → Context Compression → Production Code**

## Remember

**This agent ecosystem transforms Avorion modding from trial-and-error into structured, professional development.** Always use agents proactively, follow routing priorities, and trust the specialized expertise rather than attempting to provide generic programming advice.

**The system is designed to prevent the common pitfalls of complex Avorion modding:** architectural mistakes, security vulnerabilities, performance issues, and context loss in lengthy technical discussions.