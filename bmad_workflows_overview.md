# BMAD Workflows Overview
*Comprehensive Guide to All BMAD Workflows with Usage Examples*

---

## 📋 Workflow Categories

BMAD provides **40+ workflows** organized across 4 main categories:

1. **[Core Workflows](#core-workflows)** - Foundation workflows (party-mode, brainstorming)
2. **[BMM Development Workflows](#bmm-development-workflows)** - Complete development lifecycle (4 phases)
3. **[BMB Builder Workflows](#bmb-builder-workflows)** - Create custom agents, workflows, modules
4. **[Utility & Support Workflows](#utility--support-workflows)** - Project documentation, diagrams, testing

---

## 🧙 Core Workflows

### party-mode
**Description:** Multi-agent collaboration where all BMAD agents discuss problems together in real-time
**When to use:** Complex problems needing multiple expert perspectives, brainstorming, strategic decisions
**Agent:** BMad Master (orchestrates all agents)
**Tips:** Great for architecture decisions, product strategy, creative problem-solving

**Sample Chat Transcript:**
```
User: *party-mode

🎉 PARTY MODE ACTIVATED! 🎉
All BMAD agents are here and ready for collaboration.

User: "I'm building a payment system for my e-commerce site. What should I consider?"

John (PM): "What's your business model? Subscription vs one-time payments? 
           What's your expected transaction volume?"

Winston (Architect): "Security is critical - PCI compliance is non-negotiable. 
                     We need tokenization, separate payment service, audit logging."

Sally (UX): "Checkout conversion research shows 3-click maximum rule. 
            Need guest checkout and saved payment methods."

Murat (Test): "Critical test scenarios: fraud detection, load testing for peak traffic,
              payment failure recovery flows."

Amelia (Dev): "Tech stack recommendation: Stripe for processing, Redis for sessions,
              PostgreSQL for transaction logs."
```

### brainstorming
**Description:** Structured creative ideation using diverse brainstorming techniques
**When to use:** Need creative solutions, exploring possibilities, generating ideas
**Agent:** Analyst (Mary)
**Tips:** Use for product features, technical approaches, problem-solving

**Sample Chat Transcript:**
```
User: /bmad:core:workflows:brainstorming

Mary (Analyst): "Welcome to our brainstorming session! What challenge are we exploring today?"

User: "How can we improve user onboarding for our SaaS app?"

Mary: "Excellent! Let's use the 'How Might We' technique. I'll generate multiple angles:

- How might we reduce time-to-first-value?
- How might we make setup feel effortless?
- How might we personalize the experience?
- How might we prevent early abandonment?

Which angle resonates most with your current challenges?"

User: "Reducing time-to-first-value is our biggest issue."

Mary: "Perfect! Let's brainstorm solutions:
1. Progressive disclosure - show core features first
2. Smart defaults based on user type
3. Pre-populated demo data
4. Interactive tutorials vs static guides
5. One-click integrations with popular tools

Now let's build on these ideas..."
```

---

## 📋 BMM Development Workflows

### Phase 1: Analysis (Optional)

#### create-product-brief
**Description:** Interactive product strategy and vision definition
**When to use:** Starting new products, aligning stakeholders, strategic planning
**Agent:** Analyst (Mary)
**Tips:** Use interactive mode for best results, feeds directly into PRD workflow

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:create-product-brief

Mary (Analyst): "Let's create a compelling product brief! What product or feature are we defining?"

User: "A project management tool for remote teams"

Mary: "Interesting space! Let me ask some probing questions:

1. What specific pain point are remote teams experiencing that existing tools don't solve?
2. Who exactly is your target user - team leads, individual contributors, executives?
3. What makes this different from Asana, Monday, or Notion?"

User: "Remote teams struggle with async communication and context switching between tools."

Mary: "Aha! So we're solving communication fragmentation. Let me dig deeper:

- What tools are they currently juggling?
- How much time do they waste switching contexts?
- What would 'unified communication' look like to them?

This is shaping up to be about workflow integration, not just task management..."
```

#### research
**Description:** Comprehensive research across market, technical, competitive, and domain areas
**When to use:** Need market validation, technical evaluation, competitive analysis
**Agent:** Analyst (Mary)
**Tips:** Specify research type (market/technical/competitive/user/domain)

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:research

Mary (Analyst): "What type of research shall we conduct?
1. Market Research - TAM/SAM, market validation
2. Technical Research - Technology evaluation, ADRs
3. Competitive Research - Deep competitor analysis
4. User Research - Customer insights, personas
5. Domain Research - Industry deep dives"

User: "Market research for a fintech lending platform"

Mary: "Excellent choice! Let me research the lending platform market:

📊 MARKET ANALYSIS:
- TAM: $7.2T global lending market
- SAM: $180B digital lending (growing 25% YoY)
- Key trends: AI underwriting, embedded finance, regulatory changes

🏆 COMPETITIVE LANDSCAPE:
- Tier 1: Kabbage, OnDeck (acquired)
- Tier 2: Fundbox, BlueVine
- Emerging: Pipe, Clearco (revenue-based)

💡 OPPORTUNITY GAPS:
- SMB lending with 24-hour approval
- Industry-specific underwriting models
- Integrated accounting platform lending

Would you like me to dive deeper into any specific area?"
```

### Phase 2: Planning (Required)

#### workflow-init
**Description:** Smart entry point that analyzes your project and routes to appropriate planning track
**When to use:** Starting any new project - always use this first
**Agent:** PM (John) or Analyst (Mary)
**Tips:** Let it analyze and recommend rather than forcing a specific track

**Sample Chat Transcript:**
```
User: *workflow-init

John (PM): "Welcome to BMad Method! Let's set up your project path.

What are you working on?"

User: "Adding user authentication to our existing web app"

John: "Got it! Let me analyze this...

🔍 ANALYSIS:
- Existing codebase (brownfield)
- Security-sensitive feature
- Moderate complexity

📋 RECOMMENDATION: BMad Method Track
- PRD for security requirements
- Architecture for auth patterns
- Stories for implementation

This isn't a simple bug fix, but not enterprise-level either. 
BMad Method gives you proper planning without over-engineering.

Sound right, or do you see it differently?"

User: "That makes sense. Let's go with BMad Method."

John: "Perfect! I'll create your workflow tracking file and route you to the PRD workflow.

Next step: Load the PM agent and run the PRD workflow to define your authentication requirements."
```

#### create-prd
**Description:** Comprehensive Product Requirements Document with functional and non-functional requirements
**When to use:** Medium to large features, products, complex business logic
**Agent:** PM (John)
**Tips:** Focus on WHAT to build, not HOW. Epic breakdown happens later in Phase 3

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:create-prd

John (PM): "Let's build a solid PRD! What are we defining requirements for?"

User: "User dashboard with analytics for our SaaS platform"

John: "Great! Let me understand the scope:

🎯 DISCOVERY QUESTIONS:
1. Who are the primary users of this dashboard?
2. What key metrics do they need to see?
3. What decisions will they make based on this data?
4. How does this fit into their daily workflow?

Let's start with user types - are we talking about end users viewing their own data, or admins viewing aggregate data?"

User: "End users viewing their own usage data and performance metrics"

John: "Perfect! Self-service analytics. Let me probe deeper:

📊 FUNCTIONAL REQUIREMENTS (Draft):
- FR1: Display usage metrics (sessions, features used, time spent)
- FR2: Show performance trends (week/month/quarter views)
- FR3: Export data capabilities
- FR4: Customizable dashboard layout

⚡ NON-FUNCTIONAL REQUIREMENTS (Draft):
- NFR1: Load time under 2 seconds
- NFR2: Real-time data updates
- NFR3: Mobile responsive design

Does this capture the core functionality you're envisioning?"
```

#### create-tech-spec
**Description:** Lightweight technical specification for Quick Flow track
**When to use:** Bug fixes, simple features, clear scope changes
**Agent:** PM (John) or Quick Flow Solo Dev (Barry)
**Tips:** Perfect for 1-15 story projects, skips Phase 3 architecture

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:create-tech-spec

Barry (Quick Flow Solo Dev): "Let's spec this out fast! What are we building?"

User: "Add password reset functionality to login page"

Barry: "Classic feature! Let me break this down:

🔧 TECHNICAL APPROACH:
- Email-based reset flow
- Secure token generation (UUID + expiry)
- Password validation on reset
- Rate limiting for abuse prevention

📁 FILES TO MODIFY:
- /auth/login.html - Add 'Forgot Password' link
- /auth/reset-password.html - New reset form
- /api/auth.js - Reset endpoints
- /models/user.js - Token methods
- /tests/auth.test.js - Test coverage

⚡ IMPLEMENTATION PLAN:
Story 1: Backend API (token generation, validation)
Story 2: Frontend forms (forgot password, reset password)
Story 3: Email integration (reset email template)
Story 4: Security hardening (rate limiting, validation)

Estimated: 4 stories, 2-3 days total. Sound about right?"
```

#### create-ux-design
**Description:** User experience specification and design system creation
**When to use:** UX-critical projects, design system needs, complex user workflows
**Agent:** UX Designer (Sally)
**Tips:** Use after PRD for best results, creates living design documentation

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:create-ux-design

Sally (UX Designer): "Let's create an amazing user experience! What are we designing?"

User: "Admin dashboard for managing user accounts"

Sally: "Admin interfaces are all about efficiency and clarity! Let me understand the users:

👥 USER RESEARCH:
- Who are these admins? (Customer support, IT, managers?)
- What's their technical skill level?
- How often do they use this interface?
- What's their biggest frustration with current tools?

Let's start with their primary tasks - what do admins need to do most frequently?"

User: "Customer support agents need to quickly find users, view their info, and reset passwords"

Sally: "Perfect! Speed and clarity are key. Let me design this:

🎨 UX APPROACH:
- Search-first interface (prominent search bar)
- Card-based user results (scannable)
- Quick actions (reset password, disable account)
- Contextual user details (expandable cards)

📱 INTERACTION PATTERNS:
- Type-ahead search with filters
- Hover states for quick actions
- Modal dialogs for confirmations
- Keyboard shortcuts for power users

Would you like me to create wireframes for the main search and user detail views?"
```

### Phase 3: Solutioning

#### create-architecture
**Description:** Technical architecture and decision documentation optimized for AI agent consistency
**When to use:** After PRD, before implementation, complex technical decisions
**Agent:** Architect (Winston)
**Tips:** Creates decision-focused docs that prevent agent conflicts during implementation

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:create-architecture

Winston (Architect): "Let's design a solid architecture! I've reviewed your PRD for the user dashboard.

🏗️ ARCHITECTURAL DECISIONS NEEDED:
1. Frontend framework (React, Vue, Angular?)
2. State management (Redux, Zustand, Context?)
3. Data fetching (REST, GraphQL, tRPC?)
4. Real-time updates (WebSockets, SSE, polling?)
5. Caching strategy (Redis, in-memory, CDN?)

Let's start with your current tech stack - what are you already using?"

User: "We're using React with a Node.js backend and PostgreSQL"

Winston: "Good foundation! Let me propose an architecture:

📐 SOLUTION ARCHITECTURE:
- Frontend: React + Zustand (simpler than Redux for dashboards)
- API: REST with GraphQL for complex queries
- Real-time: Server-Sent Events (simpler than WebSockets)
- Caching: Redis for query results, React Query for client cache
- Database: PostgreSQL with materialized views for analytics

🔄 DATA FLOW:
1. User requests dashboard → React Query checks cache
2. Cache miss → GraphQL query to Node.js
3. Node.js queries PostgreSQL materialized views
4. Results cached in Redis (5min TTL)
5. SSE pushes updates for real-time data

This balances performance with simplicity. Thoughts?"
```

#### create-epics-and-stories
**Description:** Transform PRD and Architecture into implementation-ready epics and user stories
**When to use:** After PRD and Architecture are complete, before implementation
**Agent:** Scrum Master (Bob)
**Tips:** V6 improvement - creates stories AFTER architecture for better technical context

**Sample Chat Transcript:**
```
User: /bmad:bmm/workflows:create-epics-and-stories

Bob (Scrum Master): "Time to break down your dashboard PRD into actionable stories! I've reviewed your PRD and architecture.

📋 EPIC BREAKDOWN STRATEGY:
Based on user value and technical architecture, I see 4 main epics:

Epic 1: Dashboard Foundation (authentication, layout, navigation)
Epic 2: Analytics Display (charts, metrics, data visualization)  
Epic 3: Real-time Updates (SSE integration, live data)
Epic 4: User Customization (dashboard layout, preferences)

Let's start with Epic 1 - Dashboard Foundation:

🎯 USER STORIES (Epic 1):
Story 1.1: As a user, I can log into the dashboard securely
- AC: Login form, JWT authentication, redirect to dashboard
- Tasks: Login component, auth service, route protection

Story 1.2: As a user, I see a responsive dashboard layout
- AC: Header, sidebar, main content area, mobile responsive
- Tasks: Layout components, CSS Grid, responsive breakpoints

Story 1.3: As a user, I can navigate between dashboard sections
- AC: Navigation menu, active states, breadcrumbs
- Tasks: Navigation component, routing, state management

Each story is sized for 1-2 days of work. Ready to continue with Epic 2?"
```

#### check-implementation-readiness
**Description:** Adversarial validation that PRD, Architecture, and Stories are complete before implementation
**When to use:** Before starting Phase 4, quality gate validation
**Agent:** Architect (Winston) or PM (John)
**Tips:** Catches gaps early, prevents rework during implementation

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:check-implementation-readiness

Winston (Architect): "Let me validate your project is ready for implementation. I'll be thorough and adversarial to catch issues now rather than during development.

🔍 READINESS ASSESSMENT:

✅ PRD ANALYSIS:
- Functional requirements: Complete (15 FRs defined)
- Non-functional requirements: Complete (8 NFRs with metrics)
- User stories: Well-defined acceptance criteria

⚠️ ARCHITECTURE GAPS FOUND:
1. Missing error handling strategy for API failures
2. No authentication refresh token flow specified
3. Database migration strategy not documented
4. Monitoring and logging approach undefined

❌ EPIC/STORY ISSUES:
1. Story 2.3 lacks specific chart library decision
2. Performance testing acceptance criteria missing
3. No rollback plan for real-time feature

🚨 IMPLEMENTATION BLOCKERS:
- Need to choose chart library (Chart.js vs D3 vs Recharts)
- Define error boundary strategy for React components
- Specify database indexing for analytics queries

RECOMMENDATION: Address these 6 issues before implementation. Should take 2-3 hours to resolve.

Ready to fix these gaps, or do you want to proceed with known risks?"
```

### Phase 4: Implementation

#### sprint-planning
**Description:** Generate and manage sprint status tracking for implementation phase
**When to use:** Start of Phase 4, managing development progress
**Agent:** Scrum Master (Bob)
**Tips:** Creates sprint-status.yaml file for tracking all epics and stories

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:sprint-planning

Bob (Scrum Master): "Let's set up your sprint tracking! I've scanned your epics and stories.

📊 PROJECT OVERVIEW:
- 4 Epics identified
- 23 Total stories
- Estimated: 6-8 weeks (assuming 1 developer)

🎯 SPRINT 1 RECOMMENDATION (2 weeks):
Epic 1: Dashboard Foundation (Complete)
- Story 1.1: User authentication (3 days)
- Story 1.2: Dashboard layout (2 days) 
- Story 1.3: Navigation system (2 days)
- Story 1.4: Basic routing (1 day)

📋 SPRINT STATUS CREATED:
I've created sprint-status.yaml tracking:
- Epic progress (not-started → in-progress → done)
- Story status (ready-for-dev → in-progress → review → done)
- Sprint assignments
- Risk tracking

NEXT STEPS:
1. Review sprint 1 scope - does 8 days of work in 2 weeks sound right?
2. Run 'create-story' workflow to start first story
3. Use 'sprint-status' workflow to check progress anytime

Ready to start development?"
```

#### create-story
**Description:** Create the next user story from epics with enhanced context analysis
**When to use:** Starting each new story during implementation
**Agent:** Scrum Master (Bob)
**Tips:** Automatically marks stories as ready-for-dev, includes full context

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:create-story

Bob (Scrum Master): "Time to create your next story! Let me check the sprint status...

📋 NEXT STORY: Story 1.1 - User Authentication
Epic: Dashboard Foundation
Status: ready-for-dev → in-progress

🎯 STORY DETAILS:
As a user, I can log into the dashboard securely
So that I can access my personalized analytics

ACCEPTANCE CRITERIA:
- AC1: Login form with email/password fields
- AC2: JWT token authentication with backend
- AC3: Successful login redirects to dashboard
- AC4: Failed login shows error message
- AC5: Form validation for required fields

🔧 TECHNICAL CONTEXT:
- Use existing auth API endpoints
- Implement JWT storage in localStorage
- Add route protection for dashboard pages
- Follow established error handling patterns

📁 IMPLEMENTATION TASKS:
1. Create LoginForm component
2. Add auth service methods
3. Implement route protection
4. Add error handling
5. Write unit tests

STORY FILE CREATED: stories/story-1-1-user-authentication.md

Ready to implement? Run 'dev-story' workflow to start development!"
```

#### dev-story
**Description:** Execute a story by implementing tasks, writing tests, and validating acceptance criteria
**When to use:** Implementing each story during development
**Agent:** Developer (Amelia)
**Tips:** Follows red-green-refactor cycle, updates story file with progress

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:dev-story

Amelia (Dev): "Let's implement Story 1.1 - User Authentication. I've loaded the story file.

🔍 STORY ANALYSIS:
- 5 acceptance criteria defined
- 5 implementation tasks identified
- Auth patterns established in codebase

⚡ IMPLEMENTATION APPROACH:
Following TDD red-green-refactor cycle:

1. WRITE FAILING TESTS:
```javascript
// auth.test.js
describe('LoginForm', () => {
  test('submits valid credentials', async () => {
    // Test implementation
  });
  test('shows error for invalid credentials', async () => {
    // Test implementation  
  });
});
```

2. IMPLEMENT LOGINFORM COMPONENT:
```jsx
// LoginForm.jsx
export const LoginForm = () => {
  const [credentials, setCredentials] = useState({});
  const [error, setError] = useState('');
  
  const handleSubmit = async (e) => {
    // Implementation
  };
  
  return (
    // JSX implementation
  );
};
```

3. ADD AUTH SERVICE:
```javascript
// authService.js
export const login = async (email, password) => {
  // API call implementation
};
```

All tests passing ✅
Story 1.1 marked as DONE
Ready for code review!"
```

#### code-review
**Description:** Adversarial senior developer code review that finds 3-10 specific issues
**When to use:** After completing each story, quality assurance
**Agent:** Developer (Amelia) or Test Architect (Murat)
**Tips:** Never accepts "looks good" - always finds improvements, can auto-fix issues

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:code-review

Murat (Test Architect): "Time for adversarial code review! I WILL find issues - that's my job.

🔍 REVIEWING: Story 1.1 - User Authentication

❌ ISSUES FOUND (7 total):

1. SECURITY ISSUE (High):
   - JWT stored in localStorage (XSS vulnerable)
   - FIX: Use httpOnly cookies instead

2. ERROR HANDLING (Medium):
   - Generic error messages leak system info
   - FIX: Sanitize error responses

3. VALIDATION (Medium):
   - Client-side only validation
   - FIX: Add server-side validation

4. TESTING (Medium):
   - Missing edge case tests (network failures)
   - FIX: Add error scenario tests

5. ACCESSIBILITY (Low):
   - Login form missing ARIA labels
   - FIX: Add proper accessibility attributes

6. PERFORMANCE (Low):
   - Unnecessary re-renders on input change
   - FIX: Debounce input handlers

7. CODE STYLE (Low):
   - Inconsistent error state naming
   - FIX: Standardize error/loading state names

🔧 AUTO-FIX AVAILABLE:
I can automatically fix issues 5, 6, and 7. 
Issues 1-4 need your review for security/architecture decisions.

Shall I auto-fix the low-priority issues and create tasks for the others?"
```

#### sprint-status
**Description:** Summarize sprint progress, surface risks, and route to next workflow
**When to use:** Regular check-ins during implementation, daily standups
**Agent:** Scrum Master (Bob)
**Tips:** Provides clear next actions, identifies blockers early

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:sprint-status

Bob (Scrum Master): "Sprint status check! Let me analyze your progress...

📊 SPRINT 1 STATUS (Week 1 of 2):

✅ COMPLETED:
- Story 1.1: User Authentication (DONE)
- Story 1.2: Dashboard Layout (DONE)

🔄 IN PROGRESS:
- Story 1.3: Navigation System (50% complete)

📋 READY FOR DEV:
- Story 1.4: Basic Routing

⚠️ RISKS IDENTIFIED:
1. Story 1.3 taking longer than estimated (3 days vs 2 planned)
2. Code review finding security issues causing rework
3. Sprint 1 may slip by 1-2 days

🎯 RECOMMENDATIONS:
1. Focus on completing Story 1.3 today
2. Consider moving Story 1.4 to Sprint 2 if needed
3. Schedule architecture review for security patterns

📈 VELOCITY TRACKING:
- Planned: 8 story points
- Completed: 5 story points  
- Projected: 7 story points (87% of plan)

NEXT ACTION: Continue with Story 1.3 or address security issues from code review?

What's your priority?"
```

#### retrospective
**Description:** Review epic completion, extract lessons learned, identify improvements
**When to use:** After completing each epic, continuous improvement
**Agent:** Scrum Master (Bob)
**Tips:** Focuses on process improvements, feeds into next epic planning

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:retrospective

Bob (Scrum Master): "Epic 1 retrospective time! Let's extract lessons learned.

📊 EPIC 1: Dashboard Foundation - COMPLETED

✅ WHAT WENT WELL:
- Authentication implementation was solid
- Code review process caught security issues early
- TDD approach prevented major bugs
- Team velocity was consistent

⚠️ WHAT COULD IMPROVE:
- Story estimation was optimistic (3 stories took 20% longer)
- Security patterns should be defined upfront
- Code review feedback loop caused some rework

🔍 ROOT CAUSE ANALYSIS:
- Estimation: New authentication patterns took learning time
- Security: Architecture phase missed auth security details
- Rework: Code review standards not clear initially

💡 LESSONS LEARNED:
1. Add 20% buffer for stories with new patterns
2. Include security review in architecture phase
3. Define code review checklist upfront
4. Consider pair programming for complex security features

🎯 ACTIONS FOR EPIC 2:
- Update story estimation with learning buffer
- Add security architect review to planning
- Create code review checklist
- Plan pair programming sessions for complex features

Ready to apply these lessons to Epic 2: Analytics Display?"
```

### Quick Flow Workflows

#### quick-dev
**Description:** Flexible rapid development - execute tech-specs or direct instructions
**When to use:** Quick Flow track, rapid prototyping, simple implementations
**Agent:** Quick Flow Solo Dev (Barry)
**Tips:** Can work with or without tech-spec, optimized for speed

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:quick-dev

Barry (Quick Flow Solo Dev): "Let's ship something fast! What are we building?"

User: "Add a 'Mark as Read' button to notification items"

Barry: "Simple feature, let's knock it out! No tech-spec needed for this.

⚡ QUICK IMPLEMENTATION:

1. FRONTEND CHANGES:
```jsx
// NotificationItem.jsx
const NotificationItem = ({ notification, onMarkRead }) => (
  <div className={`notification ${notification.read ? 'read' : 'unread'}`}>
    {notification.message}
    {!notification.read && (
      <button onClick={() => onMarkRead(notification.id)}>
        Mark as Read
      </button>
    )}
  </div>
);
```

2. API ENDPOINT:
```javascript
// notifications.js
app.patch('/api/notifications/:id/read', async (req, res) => {
  await Notification.update(
    { read: true, readAt: new Date() },
    { where: { id: req.params.id } }
  );
  res.json({ success: true });
});
```

3. STATE MANAGEMENT:
```javascript
// useNotifications.js
const markAsRead = async (id) => {
  await api.patch(`/notifications/${id}/read`);
  setNotifications(prev => 
    prev.map(n => n.id === id ? {...n, read: true} : n)
  );
};
```

✅ DONE! 15 minutes of work. Want me to add tests or ship it?"
```

---

## 🧙 BMB Builder Workflows

### create-agent
**Description:** Interactive workflow to build BMAD-compliant agents with persona development
**When to use:** Creating custom agents for your domain or company needs
**Agent:** BMad Builder
**Tips:** 11-step guided process, includes validation and testing

**Sample Chat Transcript:**
```
User: /bmad:bmb:workflows:create-agent

BMad Builder: "Let's build an amazing agent! What kind of agent do you want to create?"

User: "A security review agent for our company's coding standards"

BMad Builder: "Excellent choice! Security agents are crucial. Let me guide you through the process:

🎯 STEP 1: AGENT CONCEPT
- Name: Security Review Agent
- Purpose: Enforce company security standards
- Domain: Application security, code review

🤖 STEP 2: PERSONA DEVELOPMENT
Let's define the personality:
- Role: Senior Security Engineer
- Communication style: Direct but educational
- Expertise: OWASP Top 10, secure coding, threat modeling

📋 STEP 3: COMMAND STRUCTURE
What workflows should this agent have?
1. security-review (code analysis)
2. threat-assessment (architecture review)  
3. compliance-check (standards validation)

🧠 STEP 4: KNOWLEDGE BASE
What company-specific knowledge should it have?
- Security standards document
- Approved libraries list
- Threat model templates
- Incident response procedures

Shall we continue building this agent?"
```

### create-workflow
**Description:** Create structured standalone workflows using step-file architecture
**When to use:** Building custom workflows for your processes
**Agent:** BMad Builder
**Tips:** Uses step-file architecture, includes templates and validation

**Sample Chat Transcript:**
```
User: /bmad:bmb:workflows:create-workflow

BMad Builder: "Time to create a powerful workflow! What process do you want to automate?"

User: "A deployment checklist workflow for our production releases"

BMad Builder: "Perfect! Deployment workflows are critical. Let me structure this:

📋 WORKFLOW DESIGN:
- Name: production-deployment
- Purpose: Ensure safe production deployments
- Type: Checklist-driven validation workflow

🔄 STEP STRUCTURE:
Step 1: Pre-deployment validation
Step 2: Security scan results
Step 3: Test coverage verification  
Step 4: Database migration review
Step 5: Rollback plan confirmation
Step 6: Deployment execution
Step 7: Post-deployment verification

⚙️ WORKFLOW FEATURES:
- Mandatory validation gates
- Rollback triggers
- Stakeholder notifications
- Audit trail logging

🎯 STEP 1 TEMPLATE:
```yaml
---
step: 1
name: "Pre-deployment Validation"
required_inputs:
  - branch_name
  - version_number
  - change_summary
validation_rules:
  - "All tests must pass"
  - "Code review approved"
  - "Security scan clean"
---
```

Ready to build the complete workflow?"
```

### edit-agent
**Description:** Modify existing BMAD agents while following best practices
**When to use:** Updating agent capabilities, fixing issues, adding features
**Agent:** BMad Builder
**Tips:** Preserves agent structure, validates changes, maintains compatibility

**Sample Chat Transcript:**
```
User: /bmad:bmb:workflows:edit-agent

BMad Builder: "Let's improve an existing agent! Which agent needs updates?"

User: "I want to add a new workflow to my security review agent"

BMad Builder: "Great! Let me load your security review agent...

🔍 CURRENT AGENT ANALYSIS:
- Name: Security Review Agent
- Current workflows: security-review, threat-assessment, compliance-check
- Knowledge base: 4 documents loaded
- Last modified: 2 weeks ago

➕ ADDING NEW WORKFLOW:
What workflow do you want to add?

User: "A vulnerability scanning workflow"

BMad Builder: "Perfect addition! Let me integrate this:

📋 NEW WORKFLOW: vulnerability-scan
- Purpose: Automated security vulnerability detection
- Integration: Links with existing security-review workflow
- Dependencies: Requires security scanner tool access

🔧 AGENT UPDATES NEEDED:
1. Add vulnerability-scan to menu
2. Create workflow file structure
3. Update knowledge base with scanner docs
4. Add validation rules
5. Test integration with existing workflows

⚠️ COMPATIBILITY CHECK:
- Menu structure: ✅ Compatible
- Knowledge base: ✅ No conflicts
- Workflow dependencies: ✅ Clean integration

Ready to implement these changes?"
```

### workflow-compliance-check
**Description:** Systematic validation of workflows against BMAD standards
**When to use:** Quality assurance for custom workflows, before sharing
**Agent:** BMad Builder
**Tips:** Adversarial analysis approach, detailed compliance reporting

**Sample Chat Transcript:**
```
User: /bmad:bmb:workflows:workflow-compliance-check

BMad Builder: "Time for rigorous workflow validation! Which workflow should I analyze?"

User: "My production-deployment workflow"

BMad Builder: "I'll be thorough and adversarial - finding issues now prevents problems later.

🔍 COMPLIANCE ANALYSIS: production-deployment

✅ STRUCTURE COMPLIANCE:
- Step-file architecture: ✅ Correct
- YAML frontmatter: ✅ Valid
- Sequential numbering: ✅ Proper

⚠️ CONTENT ISSUES FOUND:
1. Step 3 missing error handling instructions
2. No timeout specifications for validation steps
3. Rollback triggers not clearly defined
4. Missing user permission requirements

❌ CRITICAL GAPS:
1. No failure recovery procedures
2. Audit logging not implemented
3. Stakeholder notification system undefined

📊 COMPLIANCE SCORE: 72/100

🔧 REQUIRED FIXES:
- Add error handling to all validation steps
- Define timeout values (recommend 5-10 minutes)
- Specify rollback trigger conditions
- Add audit logging requirements
- Define notification workflows

RECOMMENDATION: Fix these 8 issues before production use. Estimated fix time: 2-3 hours.

Want me to help fix these issues?"
```

---

## 🛠️ Utility & Support Workflows

### document-project
**Description:** Analyze and document brownfield projects for AI-assisted development
**When to use:** Before working on existing codebases, understanding legacy systems
**Agent:** Technical Writer (Paige) or Analyst (Mary)
**Tips:** Essential for brownfield projects, creates project-context.md for AI agents

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:document-project

Paige (Tech Writer): "Let's document your existing project! This creates essential context for AI agents working on your codebase.

🔍 PROJECT ANALYSIS STARTING...

📁 CODEBASE SCAN:
- Language: JavaScript/TypeScript (React + Node.js)
- Structure: Monorepo with frontend/backend separation
- Dependencies: 247 packages identified
- Architecture: REST API with PostgreSQL database

🏗️ ARCHITECTURE PATTERNS DETECTED:
- Frontend: Component-based React with hooks
- State: Redux Toolkit for global state
- API: Express.js with middleware pattern
- Database: Sequelize ORM with migrations
- Testing: Jest + React Testing Library

📋 KEY FINDINGS:
- Authentication: JWT-based with refresh tokens
- Error handling: Centralized error middleware
- Logging: Winston with structured logging
- Deployment: Docker containers with CI/CD

⚠️ TECHNICAL DEBT IDENTIFIED:
- 23 TODO comments in critical paths
- 5 deprecated dependencies
- Missing TypeScript in 30% of components
- Test coverage at 67% (below 80% target)

📄 GENERATING project-context.md:
This file will help AI agents understand:
- Coding standards and patterns
- Architecture decisions
- Common pitfalls to avoid
- Preferred libraries and approaches

Documentation complete! AI agents now have full project context."
```

### generate-project-context
**Description:** Create concise project-context.md with critical rules for AI agents
**When to use:** Optimizing AI agent performance, establishing coding standards
**Agent:** Technical Writer (Paige)
**Tips:** LLM-optimized format, focuses on critical patterns and rules

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:generate-project-context

Paige (Tech Writer): "Let's create an optimized project-context.md file! This gives AI agents critical context in minimal tokens.

🎯 CONTEXT OPTIMIZATION:
I'll analyze your codebase and extract the most important patterns:

📋 CRITICAL RULES IDENTIFIED:
1. Always use TypeScript for new components
2. Follow React hooks patterns (no class components)
3. Use Tailwind CSS classes (no custom CSS)
4. API calls through centralized service layer
5. Error boundaries for all route components

🏗️ ARCHITECTURE CONSTRAINTS:
- Database: Use Sequelize models, no raw SQL
- Authentication: JWT middleware required for protected routes
- State: Redux Toolkit for global, useState for local
- Testing: Jest + RTL, minimum 80% coverage

⚠️ ANTI-PATTERNS TO AVOID:
- Direct DOM manipulation (use React refs)
- Inline styles (use Tailwind classes)
- Hardcoded API URLs (use environment config)
- Synchronous database calls (always async/await)

📄 GENERATED project-context.md:
```markdown
# Project Context for AI Agents

## Critical Rules
1. TypeScript required for all new code
2. Tailwind CSS only (no custom styles)
3. Async/await for all database operations
4. 80% test coverage minimum

## Architecture Patterns
- React functional components with hooks
- Redux Toolkit for global state
- Sequelize ORM for database access
- Express middleware for API routes

## Forbidden Patterns
- Class components (use hooks)
- Direct DOM manipulation
- Inline styles
- Raw SQL queries
```

File optimized for LLM efficiency: 90% token reduction achieved!"
```

### Excalidraw Diagram Workflows

#### create-excalidraw-diagram
**Description:** Create system architecture diagrams, ERDs, UML diagrams in Excalidraw format
**When to use:** Technical documentation, architecture visualization, system design
**Agent:** Architect (Winston)
**Tips:** Generates editable Excalidraw JSON, perfect for technical documentation

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:create-excalidraw-diagram

Winston (Architect): "Let's create a technical diagram! What system do you want to visualize?"

User: "Database schema for our e-commerce platform"

Winston: "Perfect! ERD coming up. Let me design this:

🗄️ DATABASE ENTITIES IDENTIFIED:
- Users (authentication, profiles)
- Products (catalog, inventory)
- Orders (transactions, fulfillment)
- Payments (billing, refunds)
- Reviews (ratings, comments)

🔗 RELATIONSHIPS:
- Users → Orders (one-to-many)
- Orders → Products (many-to-many via OrderItems)
- Users → Reviews (one-to-many)
- Products → Reviews (one-to-many)
- Orders → Payments (one-to-one)

📊 EXCALIDRAW DIAGRAM GENERATED:
```json
{
  "type": "excalidraw",
  "version": 2,
  "elements": [
    {
      "type": "rectangle",
      "id": "users-table",
      "x": 100,
      "y": 100,
      "width": 200,
      "height": 150,
      "label": "Users\n- id (PK)\n- email\n- password_hash\n- created_at"
    },
    // ... more entities
  ]
}
```

Diagram saved as: diagrams/ecommerce-erd.excalidraw
You can edit this in Excalidraw.com or VS Code with the Excalidraw extension!"
```

### Testing Workflows (TestArch)

#### testarch-framework
**Description:** Initialize production-ready test framework with Playwright or Cypress
**When to use:** Setting up testing infrastructure, new projects
**Agent:** Test Architect (Murat)
**Tips:** Includes fixtures, helpers, and configuration for enterprise testing

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:testarch-framework

Murat (Test Architect): "Let's build a bulletproof test framework! What's your testing approach?"

User: "We need end-to-end testing for our React web app"

Murat: "Excellent! I recommend Playwright for modern web testing. Here's what I'll set up:

🧪 TEST FRAMEWORK ARCHITECTURE:
- Framework: Playwright (better than Cypress for modern apps)
- Structure: Page Object Model + fixtures
- Utilities: @seontechnologies/playwright-utils integration
- Configuration: Multi-browser, parallel execution

📁 DIRECTORY STRUCTURE:
```
tests/
├── fixtures/           # Test data and setup
├── pages/             # Page Object Models
├── utils/             # Helper functions
├── specs/             # Test specifications
└── config/            # Playwright configuration
```

⚙️ CONFIGURATION FEATURES:
- Multi-browser testing (Chrome, Firefox, Safari)
- Parallel test execution
- Screenshot on failure
- Video recording for CI
- Custom fixtures for auth/data setup

🔧 PLAYWRIGHT UTILS INTEGRATION:
```javascript
// fixtures/auth.fixture.js
import { createAuthFixture } from '@seontechnologies/playwright-utils';

export const authFixture = createAuthFixture({
  loginUrl: '/login',
  credentials: { email: 'test@example.com', password: 'test123' }
});
```

Framework setup complete! Ready to write your first test?"
```

#### testarch-atdd
**Description:** Generate failing acceptance tests before implementation using TDD
**When to use:** Before implementing features, test-driven development
**Agent:** Test Architect (Murat)
**Tips:** Red-green-refactor cycle, creates failing tests first

**Sample Chat Transcript:**
```
User: /bmad:bmm:workflows:testarch-atdd

Murat (Test Architect): "Let's do proper ATDD! What feature are we testing first?"

User: "User login functionality"

Murat: "Perfect! I'll create failing acceptance tests first - that's the RED in red-green-refactor.

🔴 FAILING TESTS (RED PHASE):

```javascript
// tests/specs/auth.spec.js
import { test, expect } from '@playwright/test';
import { authFixture } from '../fixtures/auth.fixture';

test.describe('User Authentication', () => {
  test('should login with valid credentials', async ({ page }) => {
    await page.goto('/login');
    
    await page.fill('[data-testid=email]', 'user@example.com');
    await page.fill('[data-testid=password]', 'validpassword');
    await page.click('[data-testid=login-button]');
    
    // This will FAIL until login is implemented
    await expect(page).toHaveURL('/dashboard');
    await expect(page.locator('[data-testid=user-menu]')).toBeVisible();
  });

  test('should show error for invalid credentials', async ({ page }) => {
    await page.goto('/login');
    
    await page.fill('[data-testid=email]', 'user@example.com');
    await page.fill('[data-testid=password]', 'wrongpassword');
    await page.click('[data-testid=login-button]');
    
    // This will FAIL until error handling is implemented
    await expect(page.locator('[data-testid=error-message]')).toBeVisible();
    await expect(page.locator('[data-testid=error-message]')).toContainText('Invalid credentials');
  });
});
```

🧪 TEST EXECUTION:
```bash
npx playwright test auth.spec.js
# Expected: 2 failing tests (RED phase)
```

✅ NEXT STEPS:
1. Run tests (they should FAIL - that's correct!)
2. Implement login functionality (GREEN phase)
3. Refactor code while keeping tests passing (REFACTOR phase)

Tests are failing as expected! Ready to implement the login feature?"
```

---

## 🎯 Workflow Selection Guide

### By Project Type
- **New Project:** workflow-init → PRD → Architecture → Implementation
- **Bug Fix:** workflow-init → tech-spec → quick-dev
- **Existing Codebase:** document-project → workflow-init → PRD
- **Custom Domain:** create-agent → create-workflow → create-module

### By Phase
- **Phase 1 (Analysis):** brainstorming, research, product-brief
- **Phase 2 (Planning):** workflow-init, PRD, tech-spec, UX design
- **Phase 3 (Solutioning):** architecture, epics-and-stories, implementation-readiness
- **Phase 4 (Implementation):** sprint-planning, create-story, dev-story, code-review

### By Agent Specialty
- **PM (John):** workflow-init, PRD, tech-spec, correct-course
- **Analyst (Mary):** research, product-brief, brainstorming
- **Architect (Winston):** architecture, implementation-readiness, diagrams
- **Developer (Amelia):** dev-story, code-review
- **UX Designer (Sally):** create-ux-design, wireframes
- **Test Architect (Murat):** All testarch workflows, code-review
- **Scrum Master (Bob):** epics-and-stories, sprint-planning, retrospective
- **Quick Flow Dev (Barry):** tech-spec, quick-dev
- **BMad Builder:** create-agent, create-workflow, edit-agent
- **Tech Writer (Paige):** document-project, generate-project-context

---

## 💡 Pro Tips

1. **Always start with workflow-init** - Let the system guide you to the right track
2. **Use party-mode for complex decisions** - Multiple expert perspectives are invaluable
3. **Document brownfield projects first** - AI agents need context about existing code
4. **Follow the TDD cycle** - Red-green-refactor prevents technical debt
5. **Validate before implementing** - Use implementation-readiness to catch gaps early
6. **Create custom agents for your domain** - Generic agents can't know your business rules
7. **Use Quick Flow for simple changes** - Don't over-engineer bug fixes
8. **Leverage code review adversarially** - Always find improvements, never accept "looks good"

---

*This overview covers all major BMAD workflows. Each workflow includes detailed step-by-step guidance when executed. Use workflow-init as your starting point for any new project!*