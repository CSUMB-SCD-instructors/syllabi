---
layout: default
title: "Proposed Course Syllabi"
permalink: /proposed/
---

# Proposed Course Syllabi

This page contains proposed syllabi that are under consideration.

## Proposed Courses

| Course Code | Course Name | Syllabus |
|-------------|-------------|----------|
{% for doc in site.proposed %}
| {{ doc.name | replace: '.md', '' }} | {{ doc.title | default: doc.name | replace: '.md', '' }} | [Syllabus 📄]({{ doc.url }}) |
{% endfor %}

---
*This page is automatically generated*