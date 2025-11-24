# TODO System Usage Guide

Complete guide to using the AI-Whisperers task management system effectively.

---

## 📋 Quick Overview

This system helps the team track ~950 tasks across 37 repositories. Everything is organized in markdown files with clear priorities and time estimates.

**Key Files:**
- [README.md](README.md) - Team overview, products, milestones
- [team_todos.md](team_todos.md) - Weekly milestones and deliverables
- [team-assignments/](team-assignments/) - Individual task files (ivan, jonathan, kiki)
- [backlog/](backlog/) - 9 organized category files with all available tasks
- [BLOCKERS.md](BLOCKERS.md) - Active blockers and escalation
- [DEPENDENCIES.md](DEPENDENCIES.md) - Task dependencies

---

## 🎯 Daily Workflow

### Morning (15 minutes)

1. **Check your personal task file**
   - Ivan → [team-assignments/ivan-tasks.md](team-assignments/ivan-tasks.md)
   - Jonathan → [team-assignments/jonathan-tasks.md](team-assignments/jonathan-tasks.md)
   - Kiki → [team-assignments/kiki-tasks.md](team-assignments/kiki-tasks.md)

2. **Review blockers**
   - Check [BLOCKERS.md](BLOCKERS.md) for any blockers affecting you
   - Update status if you resolved any blockers yesterday

3. **Pick 2-3 tasks for today**
   - Start with 🔴 URGENT priority
   - Consider your weekly milestone goals
   - Match tasks to your available time (use time estimates)

4. **Check dependencies**
   - Review [DEPENDENCIES.md](DEPENDENCIES.md) to see if anyone is waiting on you
   - Verify your tasks aren't blocked by dependencies

### During the Day

1. **Update task status as you progress**
   ```markdown
   - [ ] Not started          (checkbox empty)
   - [~] In progress         (change to ~)
   - [x] Complete            (change to x)
   - [!] Blocked             (change to !, add blocker note)
   ```

2. **If you get blocked**
   - Mark task as `[!]` blocked
   - Add blocker details in task notes
   - Add entry to [BLOCKERS.md](BLOCKERS.md)
   - Notify team in Slack/async update
   - Move to next task while waiting

3. **Link commits to tasks**
   - Use task IDs in commit messages: `[PROD-042] fix: HTTP/2 vulnerability patched`
   - This helps track code changes to tasks

### End of Day (10 minutes)

1. **Update task statuses**
   - Mark completed tasks as `[x]`
   - Update in-progress tasks with notes
   - Document any new blockers

2. **Log time spent** (optional but recommended)
   - Note actual time vs estimated time
   - Helps improve future estimates

3. **Review tomorrow's plan**
   - Do you have tasks ready to start?
   - Any dependencies you need to follow up on?

---

## 📅 Weekly Workflow

### Monday Morning (30 minutes)

1. **Review weekly milestones** in [team_todos.md](team_todos.md)
   - What are your deliverables this week?
   - What's the team's focus?

2. **Plan your week**
   - Break milestones into daily tasks
   - Identify any dependencies early
   - Flag potential blockers

3. **Update your personal task file**
   - Move completed tasks from last week to "Done" section
   - Add new tasks from backlog if needed
   - Adjust priorities based on current sprint

### Wednesday Mid-Week Check (async, 15 minutes)

1. **Progress check**
   - Are you on track for weekly milestones?
   - Any blockers or risks?

2. **Communicate if needed**
   - Post async update in Slack if behind schedule
   - Request help if blocked
   - Notify team of any changes

### Friday Team Sync (60 minutes)

1. **Weekly standup** (30 minutes)
   - What did you complete this week?
   - What's in progress?
   - Any blockers or help needed?

2. **Next week planning** (20 minutes)
   - Review next week's milestones
   - Discuss priorities
   - Identify potential issues

3. **Backlog grooming** (10 minutes)
   - Quick review of URGENT/HIGH tasks
   - Adjust priorities if needed

---

## 🎯 How to Pick Tasks

### 1. Check Priority First

**Priority Order:**
1. 🔴 **URGENT** - Drop everything, do this now (this week)
2. 🟠 **HIGH** - Critical for revenue/customers (within 2 weeks)
3. 🟡 **MEDIUM** - Important but not urgent (this month)
4. 🟢 **LOW** - Nice to have (someday)

### 2. Consider Your Weekly Milestones

Check [team_todos.md](team_todos.md) for your deliverables this week. Pick tasks that move you toward those milestones.

### 3. Match Task to Available Time

**Have 15-30 minutes?**
→ [backlog/08-quick-wins.md](backlog/08-quick-wins.md)
- Add READMEs
- Fix typos
- Quick config changes

**Have 2-4 hours?**
→ Pick a HIGH priority task from your focus area
- Bug fixes
- Small features
- Documentation

**Have a full day?**
→ Pick a major feature
- Complete integrations
- Build new features
- Set up infrastructure

**Have a full week?**
→ Take on a project
- Ivan's Company Intelligence System
- Ivan's Meeting Analysis System
- Major infrastructure work

### 4. Balance Your Work

Try to mix:
- **60%** Planned features/milestones
- **20%** Bug fixes/tech debt
- **20%** Buffer for urgent/unexpected

Don't just do quick wins or just big features. Mix it up!

### 5. Check Dependencies

Before picking a task:
- Is it blocked by another task?
- Do you need someone else's work first?
- Check [DEPENDENCIES.md](DEPENDENCIES.md)

---

## 📝 How to Update Status

### Task Status Markers

```markdown
# Not Started
- [ ] Task description

# In Progress
- [~] Task description
  - Started: 2024-11-24
  - Notes: Working on X, need to do Y

# Completed
- [x] Task description
  - Completed: 2024-11-24
  - Time: 3h (estimated 2h)

# Blocked
- [!] Task description
  - Blocked by: Need API access from vendor
  - Blocking since: 2024-11-20 (4 days)
  - Workaround: Using synthetic data for now
```

### Adding Task Notes

Add notes under the task to track progress:

```markdown
- [~] **Build company research scraper** (6 hours)
  - Extract company description
  - Find team/leadership page
  - Get contact information

  **Progress Notes:**
  - 2024-11-24: Built basic scraper, works for 70% of sites
  - 2024-11-25: Added error handling for edge cases
  - Next: Test with 50 Paraguay companies

  **Time:** 4h spent / 6h estimated
```

---

## 🚧 How to Handle Blockers

### Step-by-Step Process

1. **Identify the blocker**
   - What exactly is blocking you?
   - Can you work around it?

2. **Mark task as blocked**
   - Change checkbox to `[!]`
   - Add blocker details to task

3. **Add to BLOCKERS.md**
   - Open [BLOCKERS.md](BLOCKERS.md)
   - Add entry with: task, blocker, action needed, ETA

4. **Notify the team**
   - Post in Slack: "Blocked on [TASK-ID]: Need [what]"
   - Tag person who can unblock if known

5. **Move to next task**
   - Don't wait idle
   - Pick another task from your list

6. **Follow escalation procedure**
   - Day 1: Document blocker
   - Day 2: Attempt resolution, notify team
   - Day 3: Escalate to Ivan if unresolved
   - Day 5: All-hands to unblock if critical

### Common Blockers & Solutions

**"Waiting for API access"**
- Solution: Request 2 weeks in advance
- Workaround: Use alternative data source or mock API

**"Waiting for code review"**
- Solution: Remind reviewer (SLA: 24h)
- Escalate: Tag Ivan if >2 days

**"Waiting for design approval"**
- Solution: Set up weekly design review
- Workaround: Proceed with draft, refactor later

**"Waiting for client data"**
- Solution: Set clear deadline when requesting
- Workaround: Use synthetic test data

**"Blocked by another task"**
- Solution: Check with task owner for ETA
- Workaround: Start next independent task

---

## 🔗 How to Track Dependencies

### When Creating a Task

Always note dependencies:

```markdown
- [ ] **Build API integration** (8 hours)
  - Depends on: [PROD-042] Security fixes must be deployed
  - Blocks: [KIKI-050] Kiki cannot demo until this is ready
```

### Dependency Syntax

```markdown
**Depends on:** [TASK-ID] Description
  - What you need before starting this task

**Blocks:** [TASK-ID] Description
  - What tasks are waiting for this to complete

**Related:** [TASK-ID] Description
  - Tasks that should be done together but not strictly dependent
```

### Check Dependencies Daily

Before starting work:
1. Open [DEPENDENCIES.md](DEPENDENCIES.md)
2. Check if anyone is waiting on your tasks
3. Prioritize tasks that are blocking others
4. Verify your dependencies are ready

---

## 📊 Finding Tasks in the Backlog

### By Role

**Ivan** → [07-research-experimental.md](backlog/07-research-experimental.md)
- Company Intelligence System
- Meeting Recording Analysis
- Research projects

**Jonathan** → [01-production-systems.md](backlog/01-production-systems.md)
- customer-feedback-app bugs/features
- Infrastructure and DevOps
- Testing and deployment

**Kiki** → [06-websites.md](backlog/06-websites.md)
- Course content development
- Marketing materials
- Website content

### By Category

1. [Production Systems](backlog/01-production-systems.md) - Revenue-generating
2. [Data Processing](backlog/02-data-processing.md) - AI services
3. [Developer Tools](backlog/03-developer-tools.md) - Tools & courses
4. [Infrastructure](backlog/04-infrastructure.md) - DevOps
5. [Support Tools](backlog/05-support-tools.md) - Internal utilities
6. [Websites](backlog/06-websites.md) - Web presence
7. [Research](backlog/07-research-experimental.md) - New projects
8. [Quick Wins](backlog/08-quick-wins.md) - Fast tasks
9. [GitHub Org](backlog/09-github-org.md) - Organization improvements

### By Priority

Search for emoji in any backlog file:
- Search: `🔴` for URGENT tasks
- Search: `🟠` for HIGH tasks
- Search: `🟡` for MEDIUM tasks
- Search: `🟢` for LOW tasks

---

## ✅ Definition of Done

A task is only "done" when ALL of these are complete:

### For Code Tasks
- [x] Code written and tested locally
- [x] Tests written and passing
- [x] Code reviewed and approved
- [x] PR merged to main
- [x] Deployed to staging (if applicable)
- [x] Verified in staging
- [x] Deployed to production (if applicable)
- [x] Monitoring confirmed working
- [x] Documentation updated

### For Documentation Tasks
- [x] Content written
- [x] Technical accuracy reviewed
- [x] Spelling/grammar checked
- [x] Examples tested (if code examples)
- [x] Links verified working
- [x] Published/committed
- [x] Team notified

### For Research Tasks
- [x] Research completed
- [x] Findings documented
- [x] Recommendations provided
- [x] Decision made or next steps defined
- [x] Stakeholders informed

**If not fully done:** Mark as `[~]` in progress, not `[x]` complete!

---

## 🎓 Best Practices

### DO ✅

- **Start with URGENT tasks** - Always check 🔴 priority first
- **Update status daily** - Keep your task file current
- **Document blockers immediately** - Don't wait
- **Break large tasks** - If >8 hours, break into subtasks
- **Ask for help** - If stuck >1 hour, reach out
- **Link commits** - Use task IDs in commit messages
- **Track actual time** - Helps improve estimates
- **Communicate proactively** - Don't surprise the team

### DON'T ❌

- **Don't hoard tasks** - Only take what you can do this sprint
- **Don't skip updates** - Team needs visibility
- **Don't work in silence** - Share progress and blockers
- **Don't ignore dependencies** - Check before starting
- **Don't mark incomplete tasks done** - Use Definition of Done
- **Don't start LOW priority** - Unless all HIGH are done
- **Don't forget to commit** - Push code and task updates

---

## 🔧 Common Tasks

### Adding a New Task

1. Find the right category in [backlog/](backlog/)
2. Use this template:

```markdown
- [ ] **Task title** (X hours)
  - Subtask 1
  - Subtask 2
  - Subtask 3

  **Priority:** 🔴 URGENT / 🟠 HIGH / 🟡 MEDIUM / 🟢 LOW
  **Owner:** [Name]
  **Depends on:** [TASK-ID] if applicable
  **Blocks:** [TASK-ID] if applicable
```

### Moving a Task to Your List

1. Copy task from backlog
2. Paste in your personal file
3. Add to appropriate priority section
4. Update "Owner" field to your name

### Completing a Task

1. Mark as `[x]` in your file
2. Update time spent vs estimated
3. Move to "Done" section (optional)
4. Remove from active sprint
5. If it was blocking others, notify them

### Archiving Old Tasks

At the end of each month:
1. Move all `[x]` completed tasks to archive section
2. Review `[!]` blocked tasks - still relevant?
3. Review `[ ]` not started tasks - still needed?
4. Clean up stale tasks

---

## 📞 Getting Help

### Questions About Tasks
- Check task description for details
- Check [DEPENDENCIES.md](DEPENDENCIES.md) for context
- Ask in Slack #team channel

### Blockers
- Add to [BLOCKERS.md](BLOCKERS.md)
- Post in Slack with details
- Tag person who can help

### Technical Questions
- **Frontend:** Ask Jonathan
- **Backend:** Ask Ivan or Jonathan
- **DevOps:** Ask Jonathan
- **Product:** Ask Ivan
- **Marketing:** Ask Kiki

### Emergencies

**Production Down:**
1. Notify Jonathan + Ivan immediately
2. Check status page / monitoring
3. Follow emergency procedures

**Security Issue:**
1. Notify Ivan immediately (private)
2. Don't discuss publicly until patched
3. Follow security disclosure process

**Customer Complaint:**
1. Notify Ivan + Kiki
2. Document the issue
3. Respond within 24h

---

## 📚 Additional Resources

- [README.md](README.md) - Team overview, products, milestones
- [team_todos.md](team_todos.md) - Weekly milestones
- [backlog/README.md](backlog/README.md) - Complete backlog guide
- [BLOCKERS.md](BLOCKERS.md) - Active blockers
- [DEPENDENCIES.md](DEPENDENCIES.md) - Task dependencies
- [project-analysis/](project-analysis/) - Detailed repo analysis
- [team-assignments/repo-improvements.md](team-assignments/repo-improvements.md) - GitHub best practices

---

## 🔄 System Improvements

This system is constantly evolving. If you have suggestions:

1. Document your idea
2. Discuss in Friday team sync
3. Update the docs if approved
4. Notify team of changes

**Suggested improvements welcomed!**

---

*Last updated: 2024-11-24*
