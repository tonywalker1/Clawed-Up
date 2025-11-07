# Collaboration Reflection Workflow

A structured approach to capturing insights and improving collaboration with Claude Code after completing substantial work.

## Purpose

The `/reflect` command provides a framework for retrospective feedback after working through a project or problem
with Claude Code. This is not about blame or criticism—it's about systematic reflection to:

- Identify patterns in successful collaboration (both what works in your workflow and what Claude Code does well)
- Surface misunderstandings or gaps in context before they compound
- Capture technical and architectural patterns worth remembering
- Continuously refine your `CLAUDE.md` files to represent how you actually work

## When to Use It

Invoke `/reflect` when:

- You've completed a substantial feature, project, or problem-solving session
- You've encountered situations where collaboration could have been smoother
- You've discovered new patterns in how you approach problems
- You want to update your `CLAUDE.md` files with fresh insights
- Your approach or constraints have evolved since your last update

You don't need to use this after every interaction—save it for moments of real learning or significant work.

## What the Command Does

The command presents four reflection prompts:

### 1. **What Went Well**
Focus on moments where collaboration was smooth and effective:
- Specific instances where Claude Code identified problems or provided clear guidance
- Communication patterns that worked particularly well
- Architectural or technical decisions that proved sound
- Times when you felt well-understood and supported

### 2. **What Didn't Work**
Be direct about friction points:
- Where Claude Code gave bad advice, missed architectural issues, or went down wrong paths
- Misunderstandings about your requirements or constraints
- Suggestions that contradicted your stated preferences or infrastructure decisions
- Mistakes and the underlying lessons (focus on wisdom, not blame)

### 3. **Patterns Worth Capturing**
Identify recurring themes:
- Technical or architectural patterns you frequently use
- Communication or collaboration patterns that were effective
- Process patterns (how you approached the problem, your testing/iteration style)
- Gaps between Claude Code's current understanding and how you actually work

### 4. **Suggested CLAUDE.md Updates**
Translate insights into actionable context updates:
- Specify which `CLAUDE.md` file(s) to update (global `~/.claude/CLAUDE.md` or project-level)
- Provide both the conceptual idea and exact text to add
- Format suggestions as they would appear in the file

## Using Reflection Feedback

After completing the reflection:

1. **Review the suggestions** - Decide which updates are worth capturing in your `CLAUDE.md` files
2. **Update your context** - Use Claude Code to help integrate changes into `~/.claude/CLAUDE.md` or project-level
   `CLAUDE.md`
3. **Keep it pragmatic** - Prioritize the 3-5 most important observations; don't aim for comprehensive updates

Claude Code can help you refine and integrate these changes directly—just ask.

## Example Use Cases

### Case 1: Architectural Clarity
After building a complex feature, you realize Claude Code could have pushed back harder on your initial design.
You reflect to capture what signs you should have noticed, then add a note to your `CLAUDE.md` about architectural
decision-making patterns.

### Case 2: Context Gap
You find yourself explaining a constraint multiple times. Reflection helps you identify what wasn't clear in your
existing `CLAUDE.md`, so you update it to prevent future confusion.

### Case 3: Communication Pattern
You discover a way of asking questions or framing problems that leads to much better solutions. You document this
pattern in your `CLAUDE.md` so it becomes the default approach.

## Integration with Workflow

The reflection workflow is independent but pairs well with:

- **After `/git-finish-feature`**: Once a feature is shipped, reflect on how the collaboration went
- **After learning something new**: Capture insights about your own process or preferences
- **Periodic reviews**: Schedule regular reflections (monthly, quarterly) to evolve your context

## Tips for Effective Reflection

- **Be specific**: Vague feedback ("it went well") is less useful than concrete examples
- **Focus on patterns**: Individual mistakes matter less than recurring patterns
- **Think systemically**: Consider how constraints, priorities, and context affected collaboration
- **Update incrementally**: You don't need to capture everything at once—small, frequent updates to `CLAUDE.md`
  are more maintainable than major rewrites
- **Honor your time**: If context is tight (reflected in the token budget), focus on the 3-5 most important
  observations rather than exhaustively documenting everything
