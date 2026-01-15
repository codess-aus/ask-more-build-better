# Agent Mode: Build at Scale

<div class="hero" role="banner">
  <div class="hero-content">
    <h1>Agent Mode</h1>
    <p>Accelerate delivery, refactor legacy code, surface security flaws</p>
    <p>Power tools for senior developers</p>
  </div>
</div>

## Beyond Autocomplete

Agent Mode isn't just about completing your code—it's about augmenting your capabilities as a senior developer. It handles the heavy lifting while you focus on architecture, design decisions, and strategic thinking.

## What is Agent Mode?

Agent Mode in GitHub Copilot is your autonomous development partner. It can:

- Execute multi-step tasks independently
- Refactor entire codebases with context
- Identify security vulnerabilities proactively
- Generate comprehensive test suites
- Migrate code across frameworks or languages
- Optimize performance bottlenecks

<div class="feature-card">

### 🚀 **Key Capabilities**

- **Autonomous Execution**: Completes complex tasks with minimal supervision
- **Context-Aware**: Understands your entire codebase, not just a single file
- **Security-First**: Proactively identifies and suggests fixes for vulnerabilities
- **Refactoring at Scale**: Modernizes legacy code while maintaining functionality
- **Test Generation**: Creates comprehensive test coverage automatically
- **Performance Optimization**: Identifies and resolves bottlenecks

</div>

## Core Use Cases

### 1. Accelerate Delivery

#### Sprint Work at Speed

Agent Mode helps you deliver features faster without compromising quality:

```javascript
// Instead of manually implementing:
// - API endpoint
// - Data validation
// - Error handling
// - Logging
// - Tests

// Agent Mode can scaffold the entire feature:
/**
 * Task: Create a user registration endpoint with:
 * - Email validation
 * - Password hashing
 * - Duplicate check
 * - Error handling
 * - Unit tests
 */
```

**What Agent Mode Delivers**:
- Complete implementation following your team's patterns
- Comprehensive error handling
- Appropriate logging
- Full test coverage
- Documentation

#### Boilerplate Elimination

Focus on business logic while Agent Mode handles:

- CRUD operations
- API client implementations
- Database migrations
- Configuration setup
- Build scripts

### 2. Refactor Legacy Code

#### The Legacy Code Challenge

You inherited a 10-year-old codebase with:
- Outdated dependencies
- No tests
- Inconsistent patterns
- Technical debt everywhere

**Before Agent Mode**:
- Months of careful, manual refactoring
- Risk of breaking changes
- Incomplete understanding of side effects
- Team burnout

**With Agent Mode**:

```python
# Example: Modernizing legacy Python 2 code to Python 3

# Legacy code
def process_data(data):
    result = {}
    for k, v in data.iteritems():  # Python 2
        result[k] = unicode(v)     # Python 2
    return result

# Agent Mode can:
# 1. Identify Python 2 patterns
# 2. Update to Python 3 equivalents
# 3. Add type hints
# 4. Improve error handling
# 5. Generate tests for both versions
```

#### Refactoring Strategies

<div class="feature-card">

**Agent Mode Excels At**:

1. **Pattern Migration**
   - Class components → Hooks in React
   - Callbacks → Promises → Async/await
   - Synchronous → Asynchronous code

2. **Dependency Updates**
   - Upgrade deprecated libraries
   - Migrate between frameworks
   - Update API integrations

3. **Code Modernization**
   - Apply modern language features
   - Improve code organization
   - Enhance readability

4. **Technical Debt Reduction**
   - Extract duplicated code
   - Simplify complex functions
   - Remove dead code

</div>

### 3. Surface Security Flaws

#### Proactive Security

Agent Mode doesn't wait for security scanners—it identifies vulnerabilities during development:

```javascript
// Vulnerable code
app.get('/user/:id', (req, res) => {
  const query = `SELECT * FROM users WHERE id = ${req.params.id}`;
  db.query(query, (err, result) => {
    res.json(result);
  });
});

// Agent Mode flags:
// ⚠️ SQL Injection vulnerability
// ⚠️ No input validation
// ⚠️ Error information leakage
// ⚠️ Missing authentication check

// Suggests secure implementation:
app.get('/user/:id', authenticate, (req, res) => {
  const id = parseInt(req.params.id);
  if (!id || id <= 0) {
    return res.status(400).json({ error: 'Invalid ID' });
  }
  
  db.query('SELECT id, name, email FROM users WHERE id = ?', [id], 
    (err, result) => {
      if (err) {
        logger.error('Database query failed', { error: err });
        return res.status(500).json({ error: 'Server error' });
      }
      res.json(result);
    }
  );
});
```

#### Common Security Issues Agent Mode Catches

1. **Injection Vulnerabilities**
   - SQL injection
   - Command injection
   - XSS (Cross-Site Scripting)
   - Path traversal

2. **Authentication & Authorization**
   - Missing authentication checks
   - Broken access control
   - Insecure session management
   - Weak password policies

3. **Data Exposure**
   - Sensitive data in logs
   - Exposed API keys
   - Information leakage in errors
   - Unencrypted sensitive data

4. **Dependencies**
   - Known vulnerable packages
   - Outdated security patches
   - Insecure configurations

## Agent Mode in Practice

### Real-World Scenario: API Modernization

**The Challenge**: Modernize a legacy REST API to GraphQL

**Traditional Approach**:
1. Learn GraphQL (weeks)
2. Design schema (days)
3. Implement resolvers (weeks)
4. Write tests (weeks)
5. Update documentation (days)
6. Handle edge cases (ongoing)

**Total time**: 2-3 months

**With Agent Mode**:

```
Task: Convert REST API to GraphQL

Context:
- Existing REST endpoints in /api/v1
- PostgreSQL database
- Express.js backend
- Keep REST API for backwards compatibility

Requirements:
- GraphQL schema matching existing data model
- Resolvers for all CRUD operations
- Authentication middleware
- Comprehensive tests
- Migration guide
```

**Agent Mode Delivers**:
- Complete GraphQL schema
- Resolvers with database integration
- Authentication/authorization
- Query optimization
- Test suite
- Documentation

**Total time**: Days, not months

### Scenario: Security Audit

**Task**: Audit a web application for security issues

**Agent Mode Actions**:
1. Scans entire codebase for vulnerabilities
2. Identifies security anti-patterns
3. Checks dependency vulnerabilities
4. Reviews authentication/authorization
5. Tests input validation
6. Examines data handling
7. Generates detailed report with fixes

**Output**:
- Prioritized list of vulnerabilities
- Severity ratings (Critical, High, Medium, Low)
- Suggested fixes with code examples
- Prevention strategies
- Security best practices guide

## Working Effectively with Agent Mode

### 1. Provide Clear Context

Agent Mode works best with comprehensive context:

```
❌ Bad: "Fix the authentication"

✅ Good: "Update authentication to use JWT tokens:
- Current: Session-based with cookies
- Target: JWT with refresh tokens
- Requirements: 
  - 15-minute access token expiry
  - 7-day refresh token expiry
  - Secure HTTP-only cookies
  - Token rotation on refresh
- Maintain backwards compatibility during migration"
```

### 2. Set Boundaries

Define what Agent Mode should and shouldn't do:

```
✅ Do:
- Refactor functions longer than 50 lines
- Add type hints to Python code
- Generate unit tests for new code

❌ Don't:
- Modify database schema
- Change API contracts
- Remove existing tests
```

### 3. Review and Validate

Agent Mode is powerful but not infallible:

- Review generated code for correctness
- Run tests to verify functionality
- Check performance implications
- Validate security fixes
- Ensure code follows team standards

### 4. Iterate and Refine

Use an iterative approach:

1. **First pass**: Generate initial implementation
2. **Review**: Identify issues or improvements
3. **Refine**: Ask Agent Mode to adjust
4. **Validate**: Test and verify
5. **Repeat**: Until satisfied

## Advanced Techniques

### Multi-File Refactoring

Agent Mode can refactor across multiple files while maintaining consistency:

```
Task: Extract shared utilities from services

Files to analyze:
- src/services/userService.js
- src/services/productService.js
- src/services/orderService.js

Actions:
1. Identify duplicate code patterns
2. Extract to src/utils/
3. Update imports in all files
4. Ensure no functionality breaks
5. Add tests for extracted utilities
```

### Legacy Code Documentation

Generate documentation for undocumented codebases:

```
Task: Document legacy authentication module

Requirements:
- Function-level documentation
- Module overview
- Architecture diagram (Mermaid)
- Usage examples
- Security considerations
- Known limitations
```

### Performance Optimization

Identify and fix performance bottlenecks:

```
Task: Optimize database queries in user dashboard

Analysis needed:
- Identify N+1 query problems
- Suggest eager loading strategies
- Recommend caching opportunities
- Propose database indexes
- Estimate performance improvements
```

## Measuring Impact

### Velocity Improvements

Teams using Agent Mode report:

- **50-70%** faster feature implementation
- **80%** reduction in boilerplate code writing
- **60%** faster legacy code refactoring
- **90%** reduction in time spent on security audits

### Quality Improvements

- **40%** fewer bugs in production
- **3x** increase in test coverage
- **75%** faster security vulnerability remediation
- More consistent code patterns

### Developer Experience

- More time for creative problem-solving
- Less time on tedious tasks
- Reduced cognitive load
- Increased job satisfaction

## When NOT to Use Agent Mode

Agent Mode is powerful, but not appropriate for everything:

### Don't Use For:

1. **Critical Security Decisions**
   - Final security reviews
   - Cryptographic implementations
   - Compliance-critical code

2. **Strategic Architecture**
   - Major architectural decisions
   - Technology selection
   - System design choices

3. **Business Logic Definition**
   - Requirements clarification
   - Product decisions
   - User experience design

4. **Learning Fundamentals**
   - When you need to understand basics
   - Use [Ask Mode](ask-mode.md) instead

## Combining Ask and Agent Modes

The most effective developers use both modes:

- **Ask Mode**: Learn and understand
- **Agent Mode**: Build and scale

**Example Workflow**:

1. **Ask Mode**: "How does GraphQL handle pagination?"
2. **Understand**: Learn the concepts
3. **Agent Mode**: "Implement cursor-based pagination for our GraphQL API"
4. **Review**: Understand what Agent Mode built
5. **Ask Mode**: "Why did you use this approach instead of offset-based?"
6. **Iterate**: Refine based on understanding

## Best Practices

<div class="feature-card">

### ✅ Do's

- Provide comprehensive context
- Review all generated code
- Start with small, well-defined tasks
- Validate security implications
- Run tests frequently
- Document Agent Mode's work
- Learn from Agent Mode's suggestions

### ❌ Don'ts

- Blindly trust generated code
- Skip code review processes
- Use for compliance-critical systems without review
- Ignore team coding standards
- Deploy without testing
- Over-rely without understanding

</div>

## Getting Started with Agent Mode

### Prerequisites

Before diving into Agent Mode:

1. **Solid Foundation**: Understand your codebase and technology stack
2. **Clear Objectives**: Know what you want to accomplish
3. **Testing Infrastructure**: Have tests to validate changes
4. **Version Control**: Use Git to track and review changes

### First Tasks

Start with low-risk, high-value tasks:

1. **Test Generation**: Generate tests for existing code
2. **Documentation**: Document undocumented code
3. **Refactoring**: Clean up small, isolated modules
4. **Boilerplate**: Generate standard CRUD operations

### Growing Your Skills

As you become comfortable:

1. Tackle larger refactoring projects
2. Use for security audits
3. Migrate legacy codebases
4. Optimize performance
5. Automate complex workflows

---

<div style="text-align: center; margin: 2rem 0;">
  <p><strong>Agent Mode is your force multiplier—use it wisely.</strong></p>
  <p><em>With great power comes great responsibility.</em></p>
</div>

## Next Steps

- [Learn Ask Mode for understanding concepts →](ask-mode.md)
- [Review best practices for both modes →](best-practices.md)
- [Return to workshop home →](index.md)
