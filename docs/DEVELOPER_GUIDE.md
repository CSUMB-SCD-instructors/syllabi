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
last_updated: 2025-09-19  # Optional - Date when syllabus was last updated
---
```

### Field Descriptions

- **`layout`**: Must be `default` for proper styling
- **`course_code`**: Course identifier (e.g., "CST334", "CST463")
- **`course_name`**: Full course name for display in tables
- **`title`**: Page title, typically combines course code and name
- **`course_calendar`**: Optional URL to the course calendar (can be relative or absolute)
- **`last_updated`**: Optional date (YYYY-MM-DD format) when the syllabus was last updated

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
last_updated: 2025-09-19
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
5. If `last_updated` is provided, it displays in both the table and at the top of individual syllabus pages
6. Jekyll automatically generates individual pages for each syllabus

### Last Updated Feature

When you include the `last_updated` field in your front matter:

- **Index table**: Shows formatted date (e.g., "September 19, 2025") in the "Last Updated" column
- **Individual pages**: Displays a blue information box at the top with the last updated date
- **Missing dates**: If no `last_updated` field is provided, the table shows "—" and no info box appears on the page

**Important**: Remember to update the `last_updated` field whenever you make changes to a syllabus to keep the information accurate.

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

## Setting Up on a New Computer

When pulling this repository on a fresh computer, follow these steps:

### Prerequisites
1. **Install Ruby** (version 2.7 or higher)
   - On macOS: `brew install ruby` or use the system Ruby
   - On Ubuntu/Debian: `sudo apt-get install ruby-full`
   - On Windows: Use [RubyInstaller](https://rubyinstaller.org/)

2. **Install Bundler**:
   ```bash
   gem install bundler
   ```

### Setup Steps
1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd syllabi
   ```

2. **Install Jekyll and dependencies**:
   ```bash
   bundle install
   ```

3. **Start the development server**:
   ```bash
   bundle exec jekyll serve
   ```

4. **Open your browser** to http://localhost:4000/syllabi/

### Troubleshooting
- If you get permission errors with gem installation, you may need to use `sudo` or configure Ruby to install gems in your home directory
- On macOS, if you encounter issues with system Ruby, consider using `rbenv` or `rvm` to manage Ruby versions
- If `bundle install` fails, try `bundle update` to update all gems to their latest compatible versions

## URL Structure

- Active syllabi: `https://site.com/syllabi/course-filename.html`
- Proposed syllabi: `https://site.com/syllabi/proposed/course-filename.html`
- Proposed index: `https://site.com/syllabi/proposed/`