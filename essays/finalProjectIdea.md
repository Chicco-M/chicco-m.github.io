---
layout: essay
type: essay
title: "Final Project Idea"
# All dates must be YYYY-MM-DD format!
date: 2026-11-04
published: true
labels:
  - Software Engineering
  - Nextjs
  - AI Assistant
  - Campus Community
  - ICS 314
---

## Project: Even Better ICS Advising (EBICSA)

**Proposers:**

- Chicco Ray Marquez (chicco@hawaii.edu)
- Rocky Acasio (rocky99@hawaii.edu)
- Rodemar Cadiz (rcadiz24@hawaii.edu)

## Overview

**The Problem:** ICS students have common advising questions, such as which courses satisfy a BS or BA requirement, what the prerequisites for a course are, and what to take next semester to have a minimum or max of X credits, but the answers are scattered across the UH catalog, the ICS department site, STAR, and the advising office. The existing UH site search returns pages rather than direct answers, and booking an appointment with advisors is usually too much work for the average student to undergo if they just want straightforward answers.

**The Solution:** A UHM web application/widget with a searchable directory of ICS courses and degree requirements, plus an AI chat assistant that answers advising, scheduling tips, and course credit questions using only that directory as its source of knowledge. Students log in, share their completed courses, intended track, and scheduling preferences, and ask questions such as "What can I take next semester?" or "Give me 12 credits, mostly online, nothing before 10 a.m." Every answer cites the course or requirement entry it came from, and schedule answers are shown on a weekly grid.

## Approach

The site will use Next.js, React, Bootstrap 5, Prisma with PostgreSQL, and GitHub. Unauthenticated visitors can browse the course directory and FAQ and use the chat assistant. After logging in, students set up a profile with their completed ICS courses and intended track (BS or BA). The assistant then uses that profile to personalize answers. Future milestones could have students save chat history, bookmark answers, and rate each answer thumbs up or down to help improve the quality of answers given by the AI Assistant.

The knowledge base will contain every ICS course (number, title, credits, prerequisites, semesters offered, and which requirement it satisfies), the BS and BA requirement sheets, and FAQ entries written from the ICS advising pages. When a student asks a question, the site searches this data for the most relevant courses and FAQ entries, sends them to an LLM API (Gemini or Groq) as context, and displays the reply with links to the entries it used. If nothing relevant is found, the assistant says so and directs the student to the ICS advising office rather than hallucinating answers.

Admins maintain the knowledge base through a portal, where they add and edit courses, requirements, and FAQ entries, and possibly review questions that received low ratings or no answer so the content can be improved in the last milestone.

## Roles

- **Users:** Browse the course directory and FAQ, ask the assistant questions, maintain a profile of completed courses, track, credit target, and scheduling preferences, generate and save candidate schedules, bookmark answers, and rate or flag answers.
- **Admins:** Have all user privileges and add, edit, or retire courses, requirements, sections, and FAQ entries; review low-rated and unanswered questions; and grant the admin role to other users.

## Mockup Page Ideas

- **Landing Page:** Introduces the site with a sample question and answer, a course search bar, and options to log in or register.
- **Course Directory Page:** Provides a searchable, filterable list of ICS courses by level, semester offered, and requirement satisfied.
- **Course Detail Page:** Shows credits, prerequisites, semesters offered, the requirement it satisfies, and related FAQ entries.
- **Chat Assistant Widget:** A pop-up available on every page that returns cited answers, suggested follow-up questions, and a thumbs up/down control.
- **Schedule Builder Page:** A form for credit target, modality, and free times that produces ranked, conflict-free schedules displayed on a weekly grid; the assistant uses this same page to show its results.
- **User Home Page:** Displays the logged-in user's completed courses, intended track, saved chats, and bookmarked answers.
- **Admin Home Page:** Serves as a maintenance portal where admins manage courses, requirements, and FAQ entries and review low-rated or unanswered questions.
- **Help Page:** Explains how to use the site and what the assistant can and cannot answer.

## Use Case Ideas

- New user goes to landing page and browses the course directory without logging in.
- New user goes to landing page, logs in, gets home page, sets up profile with completed courses and intended track.
- Admin goes to landing page, logs in, gets home page, and edits courses, requirements, and FAQ entries.
- User logs in and tells the assistant "I want 12 credits, mostly online, nothing before 10 a.m."; the assistant returns three conflict-free schedules on a weekly grid with links to each course, and the user saves one.
- User goes to landing page, logs in, asks the assistant what they can take next semester, and receives a cited list of eligible courses.
- User rates an answer thumbs down; admin sees the flagged question on the admin home page, corrects the FAQ entry, and the next user receives the corrected answer.

## Beyond the Basics

After implementing the basic functionality, here are ideas for more advanced features:

- Instructor reviews written by logged-in students and moderated by admins, so the assistant can factor in instructor ratings when ranking schedules (with a link-out to external review sites rather than scraping them).
- Multi-semester plan generator that drafts a path to graduation from the student's profile and the requirement sheet.
- Requirement checker that reports which BS or BA requirements a student's completed courses already satisfy.
- "Email my advisor" button that pre-fills a message with a saved schedule and the student's open questions.
- Trending-questions page showing what students are asking most each week.
- Extending the section data to a second department once the ICS version is stable.
