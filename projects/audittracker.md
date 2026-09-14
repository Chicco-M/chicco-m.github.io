---
layout: project
type: project
image: img/hdot/05_red_poster.png
title: "Construction Management Audit Tracker"
date: 2026
published: true
labels:
  - Python
  - AI Automation
  - SharePoint
summary: "An AI-assisted pipeline that condenses contract audits for the HDOT Harbors Division from 11 hours to about 28 minutes."
---

<img class="img-fluid" src="../img/hdot/AuditTrackerHeader.jpg">

As an AI Process Automation intern at the Hawaii Department of Transportation Harbors Division, I was handed a recurring chore: auditing construction management contracts meant opening every file attached to every contract and copying the relevant fields into a tracker by hand. Across 55 contracts and roughly 3,000 files, one pass took about 11 hours.

The tracker replaces that pass. It walks the contract folders on SharePoint, normalizes each file into text regardless of type — PDFs, scanned documents, spreadsheets, Word files, emails — and hands the text to a language model with a prompt tuned to pull out the fields auditors actually check. The extracted records land in a single reformatted tracker the team can review. The same 55 contracts now take about 28 minutes, most of it waiting on the model.

<hr>

<pre>
def extract_record(path, session):
    text = READERS[path.suffix.lower()](path)
    fields = ask_model(session, AUDIT_PROMPT, text)

    fields["source"] = path.relative_to(CONTRACT_ROOT)
    fields["confidence"] = score_fields(fields)
    return fields
</pre>

<hr>

Getting the extraction right mattered less than making it checkable. Every record keeps a pointer back to its source file and a confidence score, so an auditor spends their time on the low-confidence rows instead of re-reading everything.

Beyond the tracker, I own the AI tool integration and SharePoint data architecture for our four-person team, and built the reusable prompt libraries the team draws from. I presented this work as the Harbors Division's featured student presenter at the HDOT Intern Recognition Summit, coordinating a seven-intern project on AI-assisted construction management.

The code and contract data belong to the State of Hawaii, so there is no public repository for this one.
