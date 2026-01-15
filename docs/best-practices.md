# Best Practices: Using GitHub Copilot Right

<div class="hero" role="banner">
  <div class="hero-content">
    <h1>Best Practices</h1>
    <p>Master the art of effective AI-assisted development</p>
    <p>Learn when to use Ask Mode, when to use Agent Mode, and how to maximize both</p>
  </div>
</div>

## The Foundation: Understanding Your Tool

GitHub Copilot is powerful, but like any tool, it's most effective when used appropriately. This guide will help you understand when to use each mode and how to get the best results.

## Choosing the Right Mode

### Use Ask Mode When:

<div class="feature-card">

**Learning & Understanding** 🎓

- You encounter unfamiliar code or concepts
- You need to understand "why" something works
- You want to explore alternatives
- You're debugging and need to understand the issue
- You want to verify your understanding

**Examples:**
- "What does this regular expression match?"
- "Why use async/await instead of promises?"
- "Explain how this algorithm works"
- "What's causing this error message?"

</div>

### Use Agent Mode When:

<div class="feature-card">

**Building & Scaling** 🚀

- You need to implement a well-defined feature
- You're refactoring existing code
- You want to generate tests
- You're performing security audits
- You need to modernize legacy code
- You're optimizing performance

**Examples:**
- "Implement user authentication with JWT"
- "Refactor this class to use composition"
- "Generate unit tests for this module"
- "Find and fix SQL injection vulnerabilities"
- "Migrate this code from Python 2 to Python 3"

</div>

## Writing Effective Prompts

### The Anatomy of a Good Prompt

```
[Context] + [Task] + [Requirements] + [Constraints]
```

#### 1. Context

Provide relevant background information:

```
❌ Bad: "Add validation"

✅ Good: "In our Express.js REST API, we're receiving user registration 
data and need validation before saving to MongoDB."
```

#### 2. Task

Be specific about what you want:

```
❌ Bad: "Make it better"

✅ Good: "Refactor this function to be more readable by:
- Extracting nested logic into separate functions
- Adding descriptive variable names
- Removing duplicate code"
```

#### 3. Requirements

List specific requirements:

```
✅ Good prompt includes:
- "Must support email and phone authentication"
- "Password must be hashed with bcrypt"
- "Include rate limiting"
- "Return JWT token on success"
- "Provide clear error messages"
```

#### 4. Constraints

Specify what NOT to do:

```
✅ Good constraints:
- "Don't modify the database schema"
- "Maintain backwards compatibility with v1 API"
- "Keep response time under 100ms"
- "Don't introduce new dependencies"
```

### Examples: Bad vs. Good Prompts

#### Example 1: Feature Implementation

```
❌ Bad Prompt:
"Add login"

✅ Good Prompt:
"Implement user login endpoint for our Express.js API:

Context:
- MongoDB database with User collection
- Existing registration endpoint
- JWT-based authentication

Requirements:
- POST /api/auth/login
- Accept email and password
- Verify credentials against database
- Return JWT token (15 min expiry) and refresh token (7 days)
- Include user profile in response
- Rate limit: 5 attempts per 15 minutes per IP

Security:
- Use bcrypt for password verification
- Sanitize inputs
- Log failed attempts
- Return generic error messages (don't reveal if user exists)

Error handling:
- 400 for invalid input
- 401 for invalid credentials
- 429 for rate limit exceeded
- 500 for server errors"
```

#### Example 2: Refactoring

```
❌ Bad Prompt:
"Fix this code"

✅ Good Prompt:
"Refactor this legacy data processing function:

Current issues:
- 200+ lines long
- Nested if statements 5 levels deep
- Mixes business logic and data access
- No error handling
- Difficult to test

Goals:
- Break into smaller, focused functions
- Separate concerns (data access, validation, transformation)
- Add error handling with meaningful messages
- Make it testable
- Maintain exact same output format

Constraints:
- Don't change the function signature (called by 15 other files)
- Don't modify database queries (optimized for performance)
- Keep the same validation rules"
```

#### Example 3: Security Audit

```
❌ Bad Prompt:
"Check for bugs"

✅ Good Prompt:
"Perform security audit on user data handling:

Files to analyze:
- src/controllers/userController.js
- src/models/User.js
- src/middleware/auth.js

Focus areas:
1. Input validation and sanitization
2. SQL/NoSQL injection vulnerabilities
3. XSS prevention
4. Authentication/authorization checks
5. Sensitive data exposure (logs, errors, responses)
6. Password handling
7. Session management

For each issue found:
- Describe the vulnerability
- Show affected code
- Explain the risk
- Provide secure implementation
- Reference OWASP guidelines"
```

## Progressive Enhancement Strategy

### Start Small, Scale Up

Don't try to do everything at once. Use this progression:

#### Phase 1: Low-Risk Tasks (Week 1)

```
✅ Safe starting points:
- Generate tests for existing code
- Add documentation
- Create code comments
- Format and lint code
- Generate boilerplate
```

#### Phase 2: Isolated Features (Weeks 2-3)

```
✅ Next level:
- Implement new utility functions
- Add validation to existing endpoints
- Create new standalone components
- Refactor small modules
```

#### Phase 3: Complex Refactoring (Month 2+)

```
✅ Advanced usage:
- Large-scale refactoring
- Legacy code migration
- Security audits
- Performance optimization
- Architecture changes
```

## Code Review Checklist

Always review Copilot-generated code for:

### Functionality ✅

- [ ] Does it solve the intended problem?
- [ ] Are edge cases handled?
- [ ] Does it work with existing code?
- [ ] Are there any logical errors?

### Security 🔒

- [ ] No SQL/NoSQL injection vulnerabilities
- [ ] Input validation present
- [ ] No hardcoded secrets
- [ ] Sensitive data properly handled
- [ ] Authentication/authorization checks present
- [ ] No XSS vulnerabilities

### Performance ⚡

- [ ] No N+1 query problems
- [ ] Appropriate data structures used
- [ ] No memory leaks
- [ ] Efficient algorithms
- [ ] Proper caching where needed

### Maintainability 🔧

- [ ] Follows team coding standards
- [ ] Appropriate naming conventions
- [ ] Adequate comments (but not excessive)
- [ ] Proper error handling
- [ ] Testable code structure

### Testing 🧪

- [ ] Unit tests included (if applicable)
- [ ] Tests cover edge cases
- [ ] Tests are maintainable
- [ ] Good test coverage percentage

## Common Pitfalls and How to Avoid Them

### Pitfall 1: Blind Trust

**Problem**: Accepting generated code without review

**Solution**:
```
✅ Always review generated code
✅ Run tests
✅ Understand what the code does
✅ Verify security implications
✅ Check performance impacts
```

### Pitfall 2: Vague Prompts

**Problem**: "Make it work" or "Fix the bug"

**Solution**:
```
✅ Provide specific context
✅ Define success criteria
✅ List requirements
✅ Specify constraints
✅ Include examples
```

### Pitfall 3: Over-Reliance

**Problem**: Using Agent Mode when you should use Ask Mode

**Solution**:
```
✅ Use Ask Mode to learn
✅ Understand before building
✅ Don't skip learning fundamentals
✅ Review and learn from generated code
```

### Pitfall 4: Ignoring Context

**Problem**: Giving Copilot insufficient information

**Solution**:
```
✅ Provide relevant file paths
✅ Mention related components
✅ Explain the broader system
✅ Reference existing patterns
✅ Note dependencies and constraints
```

### Pitfall 5: No Validation

**Problem**: Deploying without testing

**Solution**:
```
✅ Run all tests
✅ Manual testing for UI changes
✅ Security scanning
✅ Performance testing
✅ Code review process
```

## Team Adoption Strategy

### Getting Your Team on Board

#### 1. Start with Champions

- Identify early adopters
- Let them experiment and share learnings
- Document success stories
- Create internal guidelines

#### 2. Provide Training

- Workshop sessions (like this one!)
- Pair programming with Copilot
- Code review sessions
- Best practices documentation

#### 3. Set Standards

- Prompt templates for common tasks
- Code review checklist specific to AI-generated code
- Security review process
- Testing requirements

#### 4. Measure and Iterate

- Track velocity improvements
- Monitor code quality metrics
- Gather team feedback
- Adjust practices based on learnings

## Ethical Considerations

### Code Ownership and Attribution

- Understand your organization's policy on AI-generated code
- Review licensing implications
- Ensure compliance with open-source licenses
- Document use of AI assistance where required

### Privacy and Confidentiality

- Don't share proprietary code in prompts (if using cloud services)
- Be careful with sensitive data
- Review your organization's data policies
- Use on-premises solutions for sensitive projects

### Bias and Fairness

- Review generated code for potential biases
- Test with diverse data sets
- Be aware of training data limitations
- Validate accessibility compliance

## Advanced Techniques

### Chain of Thought Prompting

Break complex tasks into steps:

```
Task: Implement user dashboard

Step 1: "Create database query to fetch user statistics"
Step 2: "Create API endpoint to serve user statistics"
Step 3: "Create React component to display statistics"
Step 4: "Add error handling and loading states"
Step 5: "Generate unit tests for each component"
```

### Iterative Refinement

Use a feedback loop:

```
Round 1: Generate initial implementation
Review: "This works but could be more efficient"

Round 2: "Optimize the database query using indexes"
Review: "Better, but error handling is minimal"

Round 3: "Add comprehensive error handling with logging"
Review: "Perfect, now add tests"

Round 4: "Generate unit tests with 90% coverage"
```

### Context Building

Provide examples of your coding style:

```
"Here's how we structure services in our codebase:
[paste example service]

Now create a product service following the same pattern."
```

## Combining Ask and Agent Modes

### The Learning-Building Cycle

```
1. Ask Mode: "How does Redis caching work?"
   └→ Learn the concepts

2. Ask Mode: "What's the best caching strategy for user sessions?"
   └→ Understand approaches

3. Agent Mode: "Implement Redis-based session caching"
   └→ Build the feature

4. Ask Mode: "Why did you use this specific Redis configuration?"
   └→ Learn from the implementation

5. Agent Mode: "Optimize cache invalidation strategy"
   └→ Iterate and improve
```

## Measuring Success

### Individual Metrics

Track your progress:

- **Velocity**: Features delivered per sprint
- **Quality**: Bugs in production
- **Learning**: New concepts mastered
- **Confidence**: Self-assessment of capabilities

### Team Metrics

Measure team impact:

- **Delivery Speed**: Sprint velocity trends
- **Code Quality**: Code review findings, test coverage
- **Developer Satisfaction**: Team surveys
- **Technical Debt**: Reduction over time

## Quick Reference Guide

<div class="feature-card">

### Decision Tree: Which Mode to Use?

**Need to understand something?** → Ask Mode  
**Need to build something?** → Agent Mode

**Debugging and confused?** → Ask Mode  
**Debugging and understand the issue?** → Agent Mode

**Learning a new technology?** → Ask Mode  
**Implementing with known technology?** → Agent Mode

**Code review and don't understand?** → Ask Mode  
**Code review and need to fix issues?** → Agent Mode

**Performance problem, unclear cause?** → Ask Mode  
**Performance problem, known solution?** → Agent Mode

</div>

## Resources and Further Learning

### Documentation

- [GitHub Copilot Official Docs](https://docs.github.com/copilot)
- [Prompt Engineering Guide](https://www.promptingguide.ai/)
- [OWASP Secure Coding Practices](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)

### Community

- GitHub Copilot Discussion Forums
- Developer communities (DEV.to, Stack Overflow)
- Your organization's internal channels

### Continuous Learning

- Experiment with different prompt styles
- Learn from generated code
- Share learnings with your team
- Stay updated on new features

---

<div style="text-align: center; margin: 2rem 0;">
  <p><strong>Using GitHub Copilot right means knowing when to ask and when to build.</strong></p>
  <p><em>Master both modes, and you'll transform how you develop software.</em></p>
</div>

## Workshop Summary

Congratulations! You now understand:

- ✅ When to use Ask Mode vs. Agent Mode
- ✅ How to write effective prompts
- ✅ Best practices for AI-assisted development
- ✅ Common pitfalls and how to avoid them
- ✅ How to review AI-generated code
- ✅ Strategies for team adoption

## Next Steps

- [Explore Ask Mode in depth →](ask-mode.md)
- [Master Agent Mode capabilities →](agent-mode.md)
- [Return to workshop home →](index.md)

---

<div style="text-align: center; margin: 2rem 0; padding: 1.5rem; background: var(--gradient-primary); color: white; border-radius: 8px;">
  <h3>Ready to Transform Your Development?</h3>
  <p>Start with Ask Mode to build your understanding, then accelerate with Agent Mode.</p>
  <p><strong>Ask more. Build better.</strong></p>
</div>
