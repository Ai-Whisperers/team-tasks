# Task Dependencies & Critical Path

Track dependencies between tasks to prevent blockers and identify the critical path.

*Last updated: 2024-11-24*

---

## 🎯 Critical Path Tasks

Tasks that block multiple other high-priority work items. **These should be prioritized above all else.**

### Week 1 Critical Path

| Task ID | Task | Owner | Blocks | ETA | Risk |
|---------|------|-------|--------|-----|------|
| PROD-001 | Fix HTTP/2 vulnerability | Jonathan | Production release | Week 1 | 🔴 High |
| IVAN-001 | Define Company Intelligence requirements | Ivan | All Company Intelligence work | Week 1 | 🟡 Medium |
| KIKI-001 | Complete course content audit | Kiki | Course sales launch | Week 1 | 🟢 Low |

---

## 📊 Dependency Graph

Visual representation of major task dependencies.

### Production Systems (customer-feedback-app)

```
customer-feedback-app Release (PROD-001)
│
├─> [🔴 URGENT] Fix HTTP/2 vulnerability (PROD-002)
│   └─> Blocks: Production deployment
│
├─> [🟠 HIGH] Complete testing (PROD-010)
│   ├─> Depends on: Test dataset creation (PROD-011)
│   ├─> Depends on: Performance benchmarks (PROD-012)
│   └─> Blocks: Kiki demo training (KIKI-050)
│
├─> [🟠 HIGH] Demo environment setup (PROD-030)
│   ├─> Depends on: Testing complete (PROD-010)
│   └─> Blocks: Kiki can demo to customers (KIKI-050)
│
└─> [🟠 HIGH] Monitoring setup (PROD-040)
    └─> Blocks: Production confidence
```

### Ivan's Company Intelligence System

```
Company Intelligence System (IVAN-001)
│
├─> [🔴 URGENT] Define requirements (IVAN-002)
│   └─> Blocks: ALL subsequent tasks
│
├─> [🟠 HIGH] Set up data sources (IVAN-010)
│   ├─> Depends on: Requirements defined (IVAN-002)
│   ├─> Subtask: API integrations (IVAN-011)
│   ├─> Subtask: Scraping setup (IVAN-012)
│   └─> Blocks: Company research (IVAN-020)
│
├─> [🟠 HIGH] Build analysis pipeline (IVAN-020)
│   ├─> Depends on: Data sources ready (IVAN-010)
│   └─> Blocks: Prospect scoring (IVAN-025)
│
├─> [🟡 MEDIUM] Build Streamlit UI (IVAN-030)
│   ├─> Depends on: Analysis pipeline (IVAN-020)
│   └─> Blocks: Kiki can use tool (IVAN-040)
│
└─> [🟡 MEDIUM] Generate prospect packages for Kiki (IVAN-040)
    ├─> Depends on: UI ready (IVAN-030)
    └─> Blocks: Kiki LATAM outreach (KIKI-100)
```

### Ivan's Meeting Recording Analysis

```
Meeting Analysis System (IVAN-050)
│
├─> [🔴 URGENT] Catalog all recordings (IVAN-051)
│   └─> Blocks: Prioritization of which to process
│
├─> [🟠 HIGH] Build transcription pipeline (IVAN-060)
│   ├─> Depends on: Catalog complete (IVAN-051)
│   ├─> Depends on: audio-to-text working (DATA-010)
│   └─> Blocks: Content extraction (IVAN-070)
│
├─> [🟠 HIGH] Extract content (IVAN-070)
│   ├─> Depends on: Transcription pipeline (IVAN-060)
│   └─> Blocks: Document generation (IVAN-080)
│
└─> [🟡 MEDIUM] Generate documents (IVAN-080)
    ├─> Depends on: Content extraction (IVAN-070)
    └─> Blocks: Service productization (IVAN-090)
```

### Kiki's Course & Marketing

```
Course Launch (KIKI-001)
│
├─> [🔴 URGENT] Audit course content (KIKI-002)
│   └─> Blocks: Content completion (KIKI-010)
│
├─> [🟠 HIGH] Complete course content (KIKI-010)
│   ├─> Depends on: Audit complete (KIKI-002)
│   └─> Blocks: Course platform upload (KIKI-020)
│
├─> [🟠 HIGH] Deploy courses platform (KIKI-020)
│   ├─> Depends on: Content ready (KIKI-010)
│   ├─> Depends on: Stripe integration (KIKI-021)
│   └─> Blocks: Course sales (KIKI-030)
│
└─> [🟠 HIGH] Customer feedback app demo ready (KIKI-050)
    ├─> Depends on: Demo environment (PROD-030)
    ├─> Depends on: Training from Jonathan (PROD-031)
    └─> Blocks: LATAM client demos (KIKI-060)
```

---

## 🔗 Inter-Team Dependencies

Tasks where one team member is waiting on another.

| Task | Owner | Waiting For | From | Needed By | Status | Notes |
|------|-------|-------------|------|-----------|--------|-------|
| KIKI-050 | Kiki | Demo environment | Jonathan | Week 3 | ⏳ Pending | Kiki needs to learn system |
| KIKI-100 | Kiki | Prospect packages | Ivan | Week 4 | ⏳ Pending | For LATAM outreach |
| IVAN-060 | Ivan | audio-to-text working | Jonathan | Week 2 | ⏳ Pending | For transcription pipeline |
| PROD-010 | Jonathan | Test data from client | External | Week 2 | ⏳ Pending | Can use synthetic data |

**Legend:**
- ⏳ Pending - Dependency not yet ready
- ✅ Ready - Dependency satisfied, can proceed
- 🚫 Blocked - Dependency delayed, task blocked

---

## 📋 Dependency Types

### 1. Hard Dependencies (Must Have)
Tasks that **cannot** start until the dependency is complete.

```markdown
- [ ] **Build API integration** (8 hours)
  - **Hard Dependency:** [PROD-042] Security patches must be deployed first
  - Cannot start without this
```

### 2. Soft Dependencies (Should Have)
Tasks that are better with the dependency but can start without it.

```markdown
- [ ] **Write user documentation** (4 hours)
  - **Soft Dependency:** [PROD-030] Demo environment helps with screenshots
  - Can write docs without demo, but screenshots better with it
```

### 3. Parallel Dependencies (Work Together)
Tasks that should be done in parallel for efficiency.

```markdown
- [ ] **Frontend UI** (12 hours)
  - **Parallel Dependency:** [BACK-010] Backend API being built simultaneously
  - Coordinate on API contract
```

---

## ⚠️ Dependency Risks

### High-Risk Dependencies

| Dependency | Risk | Impact | Mitigation |
|------------|------|--------|------------|
| External API access | 🔴 High | Blocks Company Intelligence | Request 2 weeks early, have backup data source |
| Client test data | 🟠 Medium | Blocks testing accuracy | Use synthetic data as workaround |
| Design approvals | 🟡 Low | Delays UI work | Proceed with draft, refactor after approval |

---

## 📝 How to Document Dependencies

### In Task Files

When creating or working on a task, document dependencies clearly:

```markdown
- [ ] **Task name** (X hours)
  - Description
  - Subtasks

  **Dependencies:**
  - **Depends on:** [TASK-ID] What you need before starting
  - **Blocks:** [TASK-ID] What tasks are waiting for this
  - **Related:** [TASK-ID] Tasks that should be done together

  **Dependency Status:**
  - [TASK-ID]: ✅ Ready / ⏳ Pending / 🚫 Blocked
```

### Example: Task with Multiple Dependencies

```markdown
- [ ] **Deploy customer-feedback-app to production** (4 hours)
  - Update environment variables
  - Run database migrations
  - Deploy to Render.com
  - Verify monitoring

  **Dependencies:**
  - **Depends on:**
    - [PROD-002] HTTP/2 vulnerability fixed (✅ Ready)
    - [PROD-010] Testing complete (⏳ Pending - Week 2)
    - [PROD-040] Monitoring setup (⏳ Pending - Week 2)

  - **Blocks:**
    - [KIKI-050] Kiki demo training
    - [PROD-050] Customer pilot launch

  - **Related:**
    - [PROD-031] Demo environment should be deployed at same time
```

---

## 🔍 How to Use This File

### Before Starting a Task

1. **Check if dependencies are ready**
   - Look up task in dependency graph
   - Verify all "Depends on" tasks are complete
   - If not ready, pick another task

2. **Notify dependent tasks**
   - If you're starting a task that others need
   - Post in Slack: "Starting [TASK-ID], will unblock [TASK-ID, TASK-ID]"

### While Working on a Task

1. **Update dependency status**
   - If you complete a task others are waiting for
   - Post in Slack: "✅ [TASK-ID] complete, unblocks [TASK-ID, TASK-ID]"
   - Tag the owners of dependent tasks

2. **Communicate delays**
   - If your task will be delayed
   - Notify teams waiting on you immediately
   - Update ETA in Inter-Team Dependencies table

### When Planning Work

1. **Identify critical path**
   - Which tasks block the most other work?
   - Prioritize critical path tasks
   - Ensure critical path owners have capacity

2. **Avoid creating unnecessary dependencies**
   - Can tasks be done in parallel?
   - Can you use stubs/mocks to reduce dependencies?
   - Can you restructure work to remove dependencies?

---

## 🎯 Reducing Dependencies

### Strategies

**1. Interface-First Development**
- Define APIs/contracts first
- Both sides develop against contract
- Reduces waiting for "other side" to finish

**2. Stub/Mock Dependencies**
- Create fake implementations for development
- Swap with real implementation later
- Unblocks parallel development

**3. Feature Flags**
- Deploy incomplete features behind flags
- Reduces "must be 100% done" dependencies
- Enables incremental delivery

**4. Clear Acceptance Criteria**
- Document exactly what "done" means
- Reduces rework and back-and-forth
- Dependent tasks know what to expect

**5. Async Communication**
- Don't wait for real-time responses
- Document questions/decisions
- Keep moving on other work

---

## 📊 Dependency Metrics

Track these to improve planning:

### Current Sprint
- **Total tasks with dependencies:** TBD
- **Tasks blocked by dependencies:** 0
- **Average dependency resolution time:** TBD
- **Critical path length:** ~4 weeks

### Improvement Goals
- Reduce critical path by 20%
- Identify recurring bottlenecks
- Minimize inter-team dependencies
- Improve parallel work opportunities

---

## 🔔 Dependency Notifications

### When to Notify Team

**Dependency Ready:**
```
✅ [TASK-ID] Complete
Unblocks: [TASK-ID], [TASK-ID]
@owner1 @owner2 you can start your tasks now!
```

**Dependency Delayed:**
```
⏰ [TASK-ID] Delayed
New ETA: [date]
Affects: [TASK-ID], [TASK-ID]
@owner1 @owner2 heads up on delay
Workaround: [if available]
```

**New Dependency Added:**
```
🔗 [TASK-ID] now depends on [TASK-ID]
Reason: [why dependency was added]
Impact: [how this affects timeline]
```

---

## 🛠️ Dependency Management Tools

### Current Setup
- Manual tracking in this file
- GitHub issue links
- Slack notifications

### Future Improvements
- Automated dependency graph visualization
- Dependency cycle detection
- Critical path calculation
- Automated notifications when dependencies ready

---

## ✅ Dependency Checklist

Before starting any task:

- [ ] Check this file for dependencies
- [ ] Verify all "Depends on" tasks are complete
- [ ] Check [BLOCKERS.md](BLOCKERS.md) for blockers
- [ ] Notify team if you're starting a task that unblocks others
- [ ] Document any new dependencies discovered
- [ ] Update Inter-Team Dependencies table if needed

When completing a task:

- [ ] Update dependency status in this file
- [ ] Notify teams/people waiting on this task
- [ ] Update related task files
- [ ] Post completion in Slack
- [ ] Check if critical path is updated

---

## 🔗 Related Documentation

- [BLOCKERS.md](BLOCKERS.md) - Active blockers
- [USAGE-GUIDE.md](USAGE-GUIDE.md) - How to use the TODO system
- [team_todos.md](team_todos.md) - Weekly milestones
- [backlog/README.md](backlog/README.md) - Complete backlog guide

---

## 💡 Tips

1. **Communicate early and often** - Don't surprise people with delays
2. **Update this file when dependencies change** - Keep it current
3. **Check daily for tasks you're blocking** - Help unblock others
4. **Design for independence** - Minimize dependencies where possible
5. **Document workarounds** - Help others continue even if blocked

---

*This file should be updated whenever dependencies are discovered, changed, or resolved.*
