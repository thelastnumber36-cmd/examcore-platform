# System Context

The ExamCore platform consists of several external actors and services.
                   +----------------------+
                   |      Participant     |
                   +----------+-----------+
                              |
                              |
                              ▼
                   +----------------------+
                   |      ExamCore        |
                   |      Web App         |
                   +----------+-----------+
                              |
        +---------------------+----------------------+
        |                     |                      |
        ▼                     ▼                      ▼
+----------------+   +----------------+    +------------------+
| Supabase Auth  |   | PostgreSQL DB  |    | Supabase Storage |
+----------------+   +----------------+    +------------------+
        |
        ▼
+----------------+
| Email Provider |
+----------------+

Actors
Participant

Take exams.

Teacher

Create questions.

Reviewer

Review essay answers.

Workspace Admin

Manage users.

Super Admin

Manage platform configuration.

External Systems
Supabase Auth
PostgreSQL
Storage
Browser
Email Service