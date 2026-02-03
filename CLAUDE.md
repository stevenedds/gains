# Fitness Dashboard - Claude Code Instructions

## Project Overview
This is Steven's personal fitness tracking dashboard. It displays workout data, tracks PRs, and provides analytics on lifting progress.

## Tech Stack
- Pure HTML/CSS/JavaScript (no build tools)
- Chart.js for visualizations
- Single page app (index.html)
- Data stored in workouts.json

## Design System

### Colors (Dark Theme)
```css
--bg-primary: #0d1117;      /* Main background */
--bg-secondary: #161b22;    /* Cards, sections */
--bg-tertiary: #21262d;     /* Nested elements */
--border: #30363d;          /* Borders */
--text-primary: #c9d1d9;    /* Main text */
--text-secondary: #8b949e;  /* Muted text */
--accent-blue: #58a6ff;     /* Primary accent */
--accent-green: #3fb950;    /* Positive/PR */
--accent-orange: #f0883e;   /* Warning */
--accent-purple: #8957e5;   /* Secondary accent */
--accent-red: #f85149;      /* Danger/negative */
```

### Typography
- Font: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif
- Large headers: 2.5rem, bold
- Section headers: 1.3rem, semibold
- Body text: 1rem
- Small/labels: 0.85rem, uppercase for labels

### Components
- Cards: bg-secondary, 1px border, 12px border-radius, 20-25px padding
- Badges: Pill-shaped, colored backgrounds, white text
- Charts: Dark grid lines (#21262d), colored data lines with fill
- Tables: Minimal, alternating row hints
- Stats: Large number, small label above, optional sub-text below

### Spacing
- Section margins: 25-30px
- Card padding: 20-25px
- Grid gaps: 15-20px
- Element spacing: 8-15px

### Interactions
- Cards: subtle hover lift (translateY -2px) + border color change
- Smooth transitions (0.2s)
- Charts: tooltips on hover

## Data Structure (workouts.json)

The JSON contains:
- `profile`: name, start date, split info
- `exercises`: exercise definitions with categories
- `workouts`: array of workout sessions with date, day, and exercises performed
- `prs`: current personal records for each tracked lift

### Categories for exercises:
- back, chest, shoulders, legs, triceps, biceps, neck

### Volume Calculation
- Volume = sets × reps × weight
- Tonnage = sum of (reps × weight) across all sets

### Estimated 1RM (Epley Formula)
- e1RM = weight × (1 + reps/30)

## Muscle Group Mapping

For push/pull ratio and muscle group volume:
- **Push**: chest, shoulders, triceps
- **Pull**: back, biceps
- **Legs**: legs (quads, hamstrings, glutes)
- **Other**: neck, core

## Current Features (keep these)
- Stats cards with key metrics
- PR board
- Training split overview
- Progress charts (pull-ups, lat pull, BSS, neck)
- Recent workouts log
- Insights section

## New Features to Add

### Volume Metrics
1. **Total Weekly Volume** - sum of sets × reps × weight for the week
2. **Volume by Muscle Group** - pie or bar chart showing distribution
3. **Volume Trend** - line chart of weekly volume over time
4. **Tonnage per Workout** - total weight moved each session

### Intensity Metrics
5. **Estimated 1RM Trends** - for main lifts, show e1RM over time
6. **Relative Intensity** - what % of e1RM are working sets at
7. **Average Working Weight** - per exercise trending

### Progression Metrics
8. **Days Since Last PR** - for each tracked lift
9. **Plateau Detection** - flag lifts stuck 3+ weeks
10. **PR Velocity** - PRs per month rate

### Balance Metrics
11. **Push/Pull Ratio** - volume comparison
12. **Upper/Lower Split** - volume comparison
13. **Muscle Group Pie Chart** - where volume goes

### Fatigue & Recovery
14. **Week-over-Week Volume Change** - % change
15. **Deload Detection** - auto-detect rest weeks
16. **Performance Trend** - are you progressing or fatigued?

### Benchmarks
17. **Strength Standards** - compare to novice/intermediate/advanced
18. **Bodyweight Ratios** - weighted pull-up as % of BW, etc.

## Design Guidelines

1. **Mobile-first** - must look great on phone
2. **Information hierarchy** - most important metrics prominent
3. **Progressive disclosure** - summary first, details on demand
4. **Visual consistency** - same patterns throughout
5. **Performance** - fast load, smooth animations
6. **Accessibility** - good contrast, readable fonts

## File Structure
```
/fitness
  index.html      # Main dashboard
  workouts.json   # Data file
  CLAUDE.md       # This file
```

When done, commit and push to deploy:
```bash
git add . && git commit -m "v2: Added comprehensive analytics" && git push
```
