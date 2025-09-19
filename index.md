---
layout: default
title: "Course Syllabi Collection"
---

# Course Syllabi Collection

This repository contains syllabi from various courses, automatically synced from their respective repositories.

## Available Courses

| Course Code | Course Name | Syllabus | Calendar |
|-------------|-------------|----------|----------|
{% for doc in site.active %}{% if doc.path contains 'syllabus' %} | {{ doc.course_code }} | {{ doc.course_name }} | [Syllabus 📄]({{ doc.url }}) | [Calendar 📅](/{{ course_code }}-calendar.html) |
{% endif %}{% endfor %}