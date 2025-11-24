# Active Blockers

Track and manage all tasks that are currently blocked. Update this file daily.

*Last updated: 2024-11-24*

---

## 🚨 Current Blockers

| ID | Task | Owner | Blocker | Reported | Age | Severity | Status |
|----|------|-------|---------|----------|-----|----------|--------|
| - | - | - | - | - | - | - | - |

**No active blockers** 🎉

---

## Blocker Details

### Template (Delete this when adding real blockers)

```markdown
### B-001: Blocker Title
- **Task:** [TASK-ID] Task name
- **Owner:** [Name]
- **Blocker:** Detailed description of what's blocking progress
- **Impact:** What can't be done because of this blocker
- **Action:** Who needs to do what to unblock
- **Workaround:** Temporary solution if available
- **Resolution ETA:** Expected resolution date
- **Reported:** 2024-11-24
- **Status:** Active / Escalated / Resolved

**Updates:**
- 2024-11-24: Initial report
- 2024-11-25: Followed up with [person]
```

---

## 📋 Resolved Blockers (Last 30 Days)

| ID | Task | Blocker | Resolution | Days Blocked | Resolved Date |
|----|------|---------|------------|--------------|---------------|
| - | - | - | - | - | - |

**No recently resolved blockers**

---

## 🔧 Blocker Severity Levels

### 🔴 Critical (Resolve <1 day)
- Production system down
- Security breach
- Customer unable to use service
- Blocking all other work

### 🟠 High (Resolve <3 days)
- Blocking sprint milestone
- Multiple team members affected
- Customer demo scheduled
- Revenue-impacting feature

### 🟡 Medium (Resolve <1 week)
- Blocking individual contributor
- Workaround available
- Internal tooling issue
- Non-critical dependency

### 🟢 Low (Resolve <2 weeks)
- Nice-to-have feature
- Minimal impact
- Easy workaround exists
- Not time-sensitive

---

## 📢 Escalation Procedure

Follow this process when blocked:

### Day 1: Identify & Document
- [x] Mark task as `[!]` blocked in your task file
- [x] Add entry to this BLOCKERS.md file
- [x] Post in Slack with details
- [x] Attempt to find workaround

### Day 2: Active Resolution
- [x] Follow up with person/team who can unblock
- [x] Explore alternative solutions
- [x] Update blocker status
- [x] Continue work on other tasks

### Day 3: Escalate if Unresolved
- [x] Escalate to team lead (Ivan)
- [x] Discuss in daily standup
- [x] Identify if blocker is critical
- [x] Set resolution deadline

### Day 5: All-Hands if Critical
- [x] If critical blocker unresolved after 5 days, escalate to all-hands
- [x] Re-prioritize team work to resolve blocker
- [x] Consider external help if needed

---

## 🛡️ Common Blockers & Prevention

### 1. Waiting for API Access

**Prevention:**
- Request access 2 weeks in advance
- Keep a list of common APIs and access procedures
- Build relationships with vendor support teams

**Workaround:**
- Use alternative data sources
- Mock API responses for development
- Build feature without external dependency first

---

### 2. Waiting for Code Review

**Prevention:**
- Set SLA: Reviews completed within 24 hours
- Tag reviewer in PR and Slack
- Keep PRs small (< 400 lines) for faster review

**Workaround:**
- Work on next task while waiting
- If urgent, pair review in real-time
- After 24h, escalate to Ivan

---

### 3. Waiting for Design Approval

**Prevention:**
- Set up weekly design review meetings
- Share designs early for async feedback
- Use design system for consistency

**Workaround:**
- Proceed with draft design, refactor after approval
- Use similar approved designs as reference
- Get informal feedback first

---

### 4. Waiting for Client Data/Feedback

**Prevention:**
- Set clear deadlines when requesting data
- Provide specific format requirements
- Follow up 2 days before deadline

**Workaround:**
- Use synthetic test data
- Build feature with placeholder data
- Demo with mock data

---

### 5. Blocked by Another Task

**Prevention:**
- Check [DEPENDENCIES.md](DEPENDENCIES.md) before starting work
- Communicate with task owner for ETA
- Plan tasks in dependency order

**Workaround:**
- Start next independent task
- Build stub/mock for dependency
- Parallelize where possible

---

### 6. Missing Infrastructure/Environment

**Prevention:**
- Document all environment setup procedures
- Maintain infrastructure-as-code
- Test setup on clean machine regularly

**Workaround:**
- Use local development environment
- Use Docker containers
- Pair with someone who has access

---

### 7. Unclear Requirements

**Prevention:**
- Write acceptance criteria before starting
- Ask clarifying questions upfront
- Review requirements with stakeholder

**Workaround:**
- Make reasonable assumptions and document
- Build MVP to get feedback
- Create multiple options to choose from

---

### 8. Technical Blocker (Don't Know How)

**Prevention:**
- Research before claiming task
- Ask for help early (don't wait >1 hour)
- Pair program on unfamiliar areas

**Workaround:**
- Find similar existing code
- Search documentation/Stack Overflow
- Ask in team Slack channel
- Schedule pairing session

---

## 📊 Blocker Metrics

Track these monthly to identify patterns:

### Current Month (November 2024)
- **Total blockers:** 0
- **Average resolution time:** -
- **Blockers by severity:** 🔴 0, 🟠 0, 🟡 0, 🟢 0
- **Most common blocker type:** -

### Top Blocker Categories
1. -
2. -
3. -

### Prevention Actions Taken
- -

---

## 💡 Tips for Minimizing Blockers

### For Everyone
1. **Check dependencies early** - Review [DEPENDENCIES.md](DEPENDENCIES.md) before starting
2. **Communicate proactively** - Don't wait to be asked
3. **Document blockers immediately** - Don't wait until EOD
4. **Find workarounds** - Don't stop all work

### For Ivan (Product Lead)
1. **Clarify requirements upfront** - Avoid "unclear requirements" blockers
2. **Respond to escalations quickly** - <4 hour response time
3. **Prioritize unblocking team** - Blockers affect velocity

### For Jonathan (Lead Developer)
1. **Review PRs within 24h** - Set the standard
2. **Document infrastructure setup** - Avoid environment blockers
3. **Be available for technical questions** - Quick unblocking

### For Kiki (Marketing)
1. **Provide design feedback quickly** - Don't bottleneck creative work
2. **Share content requirements early** - Avoid back-and-forth
3. **Test features and give feedback** - Help dev team improve

---

## 🔍 How to Use This File

### When You Get Blocked

1. **Add entry to table** at top with severity
2. **Create detailed section** using template above
3. **Post in Slack:** "🚨 Blocker added: [B-XXX] Brief description"
4. **Update daily** with progress and attempts to resolve
5. **Follow escalation procedure** (see above)

### When You Resolve a Blocker

1. **Update Status** in Current Blockers table to "Resolved"
2. **Move to Resolved Blockers** section with resolution details
3. **Post in Slack:** "✅ Blocker resolved: [B-XXX] Brief description"
4. **Notify task owner** so they can resume work
5. **Archive after 30 days**

### Daily Review (Everyone)

- Check if any blockers affect your work
- Update status on blockers you can help resolve
- Age column helps identify stale blockers

### Weekly Review (Ivan)

- Review all blockers >3 days old
- Escalate critical blockers
- Identify patterns and prevention opportunities
- Update blocker metrics

---

## 📝 Blocker ID Convention

Use format: `B-XXX` (e.g., B-001, B-002, etc.)

- Sequential numbering
- Prefix "B-" for easy searching
- Reference in task files: "Blocked by: B-042"

---

## 🔗 Related Documentation

- [DEPENDENCIES.md](DEPENDENCIES.md) - Task dependencies
- [USAGE-GUIDE.md](USAGE-GUIDE.md) - How to use the TODO system
- [team_todos.md](team_todos.md) - Weekly milestones

---

## ✅ Blocker Resolution Checklist

When resolving a blocker:

- [ ] Update blocker status to "Resolved"
- [ ] Add resolution details
- [ ] Calculate days blocked
- [ ] Move to Resolved Blockers section
- [ ] Notify task owner
- [ ] Post in Slack
- [ ] Update task status from `[!]` to `[~]` or `[ ]`
- [ ] Review if prevention measure needed

---

*This file should be updated whenever blockers are added, changed, or resolved. Don't let it get stale!*
