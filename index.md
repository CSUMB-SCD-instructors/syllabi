---
layout: default
title: "Course Syllabi Collection"
---

# Course Syllabi Collection

This repository contains syllabi from various courses, automatically synced from their respective repositories.

## Available Courses

{% assign syllabi = site.active | where_exp: "d", "d.basename contains 'syllabus'" %}

| Course Code | Course Name | Syllabus | Calendar |
|-------------|-------------|----------|----------|
| CST334      | OS          | pass     | pass     |

{% for doc in syllabi %}
{% assign course_code = doc.basename | replace: '-syllabus', '' %}
| {{ course_code }} | {{ doc.data.title | default: course_code }} | [Syllabus 📄]({{ doc.url | relative_url }}) | [Calendar 📅]({{ '/active/' | append: course_code | append: '-calendar.html' | relative_url }}) |
{% endfor %}