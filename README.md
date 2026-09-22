# Antifr

Antifr is an AI platform designed for educational environments.

Instead of simply blocking AI in schools, Antifr aims to provide a controlled, transparent, and education-focused way to use AI responsibly.

The project is currently under active development.

---

## Why Antifr?

AI tools are increasingly used by students, but in many schools they are either unrestricted or completely blocked.

Antifr was created around a simple idea:

AI should not be completely banned from education.
It should be used responsibly, with clear rules and educational goals.

Antifr is designed to help schools use AI in a way that supports learning instead of replacing thinking.

---

## Core Goals

- Provide a school-friendly AI environment
- Reduce overdependence on AI-generated answers
- Support students without completing assignments for them
- Allow teachers and administrators to control AI behavior
- Provide school-specific information through RAG
- Protect student privacy and sensitive school data
- Make AI usage transparent and manageable

---

## Key Features

### AI Chat

Students and teachers can interact with an AI assistant through a simple chat interface.

The AI model will be based on an open-weight model, with Qwen currently planned as the main foundation.

### Debate Mode

Debate Mode is designed for classes where students must think, argue, and respond independently.

When Debate Mode is active:

- Students receive questions, counterarguments, and hints
- The AI avoids generating complete debate answers
- The AI encourages students to explain their own reasoning
- Responses may pass through an additional review stage before being shown
- Teachers and administrators are not restricted by Debate Mode

Debate Mode is a global school policy mode for students.

To avoid unexpected changes during class, Debate Mode must be scheduled at least 24 hours in advance.

When activated, it applies to all student accounts, regardless of which Chromebook or device they use.

### Role-Based Access

Antifr uses different roles for different users.

STUDENT
TEACHER
ADMIN

Different roles can have different permissions, AI behavior, and access levels.

For example:

Student  -> Debate Mode restrictions apply
Teacher  -> Normal AI access
Admin    -> Normal AI access + management tools

### School RAG

Antifr can use school-specific documents to answer questions.

Examples include:

- School rules
- Announcements
- Student handbooks
- Library information
- Class documents
- Internal educational resources

The basic RAG flow is:

School Documents
      ↓
Text Extraction
      ↓
Chunking
      ↓
Embeddings
      ↓
Vector Database
      ↓
Relevant Document Search
      ↓
LLM Response

The goal is to provide answers based on real school information instead of guessing.

### Source-Aware Answers

When possible, Antifr should show where information came from.

Example:

Answer:
The school library is open until 4:30 PM.

Source:
2026 Student Handbook, Page 23

### Privacy and Safety

Antifr is designed with school environments in mind.

The system should avoid storing or exposing:

- Student passwords
- API keys
- Personal phone numbers
- Sensitive student information
- Internal administrator credentials
- Private school documents without proper permissions

Sensitive values must never be committed to GitHub.

---

## Planned Technology Stack

Frontend:
- React
- Vite
- JavaScript / TypeScript

Backend:
- FastAPI
- Python

AI:
- Qwen
- Open-weight LLM
- LoRA / SFT customization

RAG:
- Qdrant or Chroma
- Multilingual embedding model
- FastAPI

Database:
- PostgreSQL
- SQLite for local development

---

## Project Structure

``` txt
Antifr/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── hooks/
│   │   ├── services/
│   │   ├── contexts/
│   │   └── utils/
│   └── public/
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── core/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   └── db/
│   └── tests/
│
├── docs/
├── scripts/
├── data/
├── .github/
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

---

## Development Workflow

Antifr uses a Fork + Pull Request workflow.

Original Repository
        ↓
Fork
        ↓
Create Branch
        ↓
Develop
        ↓
Commit
        ↓
Push
        ↓
Pull Request
        ↓
Review
        ↓
Merge

Direct development on main is discouraged.

For more information, see CONTRIBUTING.md.

---

## Branch Strategy

Main branches:

main
develop

Feature branches:

feature/*
fix/*
docs/*
design/*

Examples:

feature/chat-ui
feature/llm-api
feature/debate-mode
feature/rag
docs/model-research
design/chat-layout

---

## Development Roadmap

Phase 1
- Basic repository structure
- Chat UI
- Mock API
- Basic frontend/backend communication

Phase 2
- Qwen integration
- Real AI responses
- Error handling
- Conversation history

Phase 3
- Authentication
- User roles
- Student / Teacher / Admin permissions

Phase 4
- Debate Mode
- Response review pipeline
- Global student policy enforcement
- Scheduled activation

Phase 5
- RAG
- School document upload
- Source-aware answers
- Permission-based document access

Phase 6
- Administrator dashboard
- School configuration
- Usage statistics
- School-wide policies

---

## Plans

Antifr may eventually support multiple service plans.

Free
Student
Pro Teacher
Edu
Pro School

Student access is planned to remain free for verified students.

Pro School is intended for school-wide administration and advanced educational features.

---

## Founding School

Antifr was originally created for use in an educational environment at Daegu Keisung Elementary School.

The founding school is planned to receive Pro School access without a recurring license fee while the service remains operational.

---

## Security

Never commit:

.env
API keys
Database passwords
OAuth secrets
Student personal information
Administrator credentials
Private school data

Use environment variables and .env.example instead.
