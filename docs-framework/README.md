# Product Planning & Management Framework

Simple framework for solo developers to plan and manage SaaS products with AI agents.

## Starting a New Project

1. **Tell me your idea:** "I want to build [describe in 1-2 sentences]"
2. **I'll ask questions** and fill out `templates/product-planning.md`
3. **Complete reality check** using `templates/reality-check.md`
4. **Update** `progress/project-tracker.md` with your new project

## Daily Development Work

1. **Start your day:** Read `progress/project-tracker.md` 
2. **Update dev log:** Add 1-2 sentence status to "Daily Dev Log"
3. **Log decisions:** Important choices go in `progress/decision-log.md`

## Weekly Maintenance (5 minutes)

1. **Fill out** `templates/weekly-review.md`
2. **Update** milestone progress in tracker
3. **Clean up** completed tasks

## Returning After Time Away

1. **Read** `progress/project-tracker.md` - see current status
2. **Check** latest weekly review 
3. **Tell me:** "Continue working on [project name]"
4. **I'll pick up** where we left off

## Framework Structure

```
docs-framework/
├── agents/
│   ├── product-strategist.md    # Market analysis questions
│   └── architect.md             # Technical planning questions
├── templates/
│   ├── product-planning.md      # Main planning template
│   ├── reality-check.md         # Time/skill/motivation check
│   ├── weekly-review.md         # Weekly progress review
│   └── project-knowledge-base.md # Project context (optional)
└── progress/
    ├── project-tracker.md       # Current status and dev log
    └── decision-log.md          # Important decisions made
```

## When to Use What

**Planning a project:** Use product-strategist → architect → product-planning template  
**Starting development:** Update tracker "Development Status" section  
**Daily work:** Add 1 line to dev log  
**Making big decisions:** Log in decision-log.md  
**Weekly:** Fill out weekly-review.md  
**Stuck or confused:** Fill out reality-check.md

## That's It

Keep it simple. Update when you remember. The framework works even if you skip days.

Focus is **planning** and **tracking progress**, not complex project management.