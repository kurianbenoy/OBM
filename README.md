README
======

"Operation Blue Moon" contains Org files for managing project tasks.

Motivation
==========

* Getting Things Done
* Time management
* Better estimation of work
* Self-improvement
* Statistics

Workflow
========

If you are interested in participating in these sprints, define your
long-term (3-5 years) and short-term goals (3-6 months), and ping
"mbuf" on irc.freenode.net.

### Why

Long-term goals could be your passion or job roles that you want to
pursue such as (but not limited to):

* DevSecOps Engineer
* Security Engineer
* Kernel Engineer
* Systems Programmer
* Web developer
* UI/UX Designer
* Writer
* Document Translator
* Data Engineer
* Data Scientist
* Packager
* Application Developer
* QA Tester

### What

The short-term goals may include the technology and skills that you
need to learn to achieve your long-term goals. The short-term goals are
further sub-divided into tasks which are aligned to sprints.

The plan/ directory has sub-directories for the long-term goals. You
should create an Org file for your name, and place it under the
respective long-term goal that you plan to work towards. A
user-example.org is available in the plan/ directory for reference.

The tasks can be any one of the following categories: READ, WRITE,
DEV, OPS, EVENT, MEETING.

You can insert a new task into your Org file by invoking "M-x
insert-org-entry" after adding the following function to your Emacs
init configuration:

    (define-skeleton insert-org-entry
      "Prompt for task, estimate and category"
      nil
      '(setq task  (skeleton-read "Task: "))
      '(setq estimate  (skeleton-read "Estimate: "))
      '(setq category (skeleton-read "Category: "))
      '(setq timestamp (format-time-string "%s"))
      "** " task \n
      ":PROPERTIES:" \n
      ":ESTIMATED: " estimate \n
      ":ACTUAL:" \n
      ":OWNER: shaks" \n
      ":ID: " category "." timestamp \n
      ":TASKID: " category "." timestamp \n
      ":END:")

A task that spans across multiple sprints should have the same ID and
TASKID, but, you can add a suffix to the task name as "Part I", "Part
II", "Part III" etc. across sprints. This helps to track the total
time spent on a task.

### When

For each sprint, you list the tasks that you want to work under the
PLAN heading in your Org file.

You should also decide on the hours you can spend per day and create a
work-per-day entry for each sprint in the PROPERTIES drawer as shown
below:

    ** October   10, 2018 - October  23, 2018 (14 days)
       :PROPERTIES:
       :wpd-mbuf: 2
       :END:

You should not clock anything in your Org file. All clocked timings
will be in sprints/.

### How

You need to break the tasks and sub-tasks in detail with checkboxes
and links to documentation or references.

During the sprint, you can send PR with your clocked timings. You need
to ensure that ACTUALS in the PROPERTIES drawer get updated. You can
add the following to your Emacs configuration:

    (defun org-update-actuals ()
      (interactive)
      (org-entry-put (point) "ACTUAL"
                     (format "%0.2f" (/ (org-clock-sum-current-item) 60.0))))

    (global-set-key (kbd "C-c s c") 'org-update-actuals)

At the end of a sprint, a retrospection meeting will be held to review
the same.

It is recommended for participants to wear a heavy watch so that they
have the notion of time.

Upcoming Sprints
================

* July      16, 2019 - August     1, 2019 (17 days)
* August     2, 2019 - August    14, 2019 (13 days)
* August    15, 2019 - August    30, 2019 (16 days)
* August    31, 2019 - September 12, 2019 (13 days)
* September 13, 2019 - September 29, 2019 (17 days)
* Spetember 30, 2019 - October   12, 2019 (13 days)
* October   13, 2019 - October   28, 2019 (16 days)
* October   29, 2019 - November  11, 2019 (14 days)
* November  12, 2019 - November  27, 2019 (16 days)
* November  28, 2019 - December  11, 2019 (14 days)
* December  12, 2019 - December  26, 2019 (15 days)
* December  27, 2019 - January    9, 2020 (14 days)
* January   10, 2020 - January   25, 2020 (16 days)
* January   26, 2020 - February   8, 2020 (14 days)
* February   9, 2020 - February  24, 2020 (16 days)
* February  25, 2020 - March      8, 2020 (13 days)

Contact
=======

Shakthi Kannan ("mbuf")

author AT shakthimaan dot com
