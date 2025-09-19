---
layout: default
title: "Course Syllabi Collection"
---

# Course Syllabi Collection

This repository contains syllabi from various courses, automatically synced from their respective repositories.

## Available Courses

| Course Code | Course Name | Syllabus | Calendar |
|-------------|-------------|----------|----------|
{% for doc in site.active %}{% if doc.path contains 'syllabus' %} | {{ doc.course_code }} | {{ doc.course_name }} | [Syllabus 📄]({{ doc.url | relative_url }}) | {% if doc.course_calendar %}[Calendar 📅]({{ doc.course_calendar | relative_url }}){% else %}—{% endif %} |
{% endif %}{% endfor %}