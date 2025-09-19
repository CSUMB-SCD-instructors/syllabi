# Developer Guide: Adding Syllabi

This guide explains how to prepare syllabus files for display on the Course Syllabi Collection site.

## File Structure

The site uses Jekyll collections to organize syllabi:

- **Active syllabi**: Place in `_active/` directory - these appear on the main page
- **Proposed syllabi**: Place in `_proposed/` directory - these appear on the `/proposed/` page

## Required Front Matter

Every syllabus file must include Jekyll front matter at the top with these required fields:

```yaml
---
layout: default
course_code: "CST334"
course_name: "Introduction to Operating Systems"
title: "CST334 - Introduction to Operating Systems"
course_calendar: "https://example.com/calendar"  # Optional - URL to course calendar
---
```

### Field Descriptions

- **`layout`**: Must be `default` for proper styling
- **`course_code`**: Course identifier (e.g., "CST334", "CST463")
- **`course_name`**: Full course name for display in tables
- **`title`**: Page title, typically combines course code and name
- **`course_calendar`**: Optional URL to the course calendar (can be relative or absolute)

## File Naming

- Use descriptive filenames like `CST334-syllabus.md`
- Files should end with `.md` extension
- Use consistent naming patterns across all syllabi

## Example Syllabus File

```markdown
---
layout: default
course_code: "CST334"
course_name: "Introduction to Operating Systems"
title: "CST334 - Introduction to Operating Systems"
course_calendar: "/CST334-calendar.html"
---

# CST334 (Operating Systems) Syllabus

## Course Information

Your syllabus content goes here...
```

## How It Works

1. **Active syllabi** in `_active/` automatically appear in the main page table
2. **Proposed syllabi** in `_proposed/` automatically appear on the `/proposed/` page
3. The `course_code` and `course_name` fields populate the table columns
4. If `course_calendar` is provided, a calendar link appears in the table
5. Jekyll automatically generates individual pages for each syllabus

## Adding a New Syllabus

1. Create a new `.md` file in either `_active/` or `_proposed/`
2. Add the required front matter at the top
3. Write your syllabus content in Markdown
4. Commit and push - the site will automatically update

## Testing Locally

To test your changes locally:

```bash
# Install dependencies (first time only)
bundle install

# Serve the site locally
bundle exec jekyll serve

# View at http://localhost:4000/syllabi/
```

## URL Structure

- Active syllabi: `https://site.com/syllabi/course-filename.html`
- Proposed syllabi: `https://site.com/syllabi/proposed/course-filename.html`
- Proposed index: `https://site.com/syllabi/proposed/`