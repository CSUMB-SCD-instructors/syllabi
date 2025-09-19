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
{% for doc in site.proposed %}| {{ doc.course_code }} | {{ doc.course_name }} | [Syllabus 📄]({{ doc.url }}) |
{% endfor %}
