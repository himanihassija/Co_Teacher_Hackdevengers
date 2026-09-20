# Athena EchoSphere

**An AI co teacher that joins the classroom, teaches alongside the teacher, and always answers to them.**

Athena EchoSphere is a real time, voice driven AI co teacher for live virtual classrooms. She listens, speaks, explains, visualizes, checks understanding, identifies learning gaps, and supports students while keeping the teacher in complete control.

Athena is not a chatbot attached to a video call. She is designed as an active classroom participant with real time voice interaction, shared visual learning, live quizzes, learning gap detection, personalized support, interactive 3D learning, and post class intelligence.

Built end to end on Agora's real time infrastructure.

---

# Table of Contents

* Core Concept
* Features

  * Live Voice Co Teaching
  * Turn Taking and Restraint Model
  * Shared Whiteboard
  * Interactive 3D Learning
  * Live Quizzes and Gap Detection
  * Nobody Left Behind
  * Teacher Controls
  * Athena AI Assistant
  * Post Class Report
  * Multilingual Support
  * Screen Sharing
  * Avatar and Visual Presence
* Technology Stack
* Architecture
* Implementation Flow
* Getting Started
* Environment Variables
* Project Structure

---

# Core Concept

A teacher creates a classroom session and students join using a share code. The teacher can bring Athena into the classroom whenever additional support is needed.

From there, Athena behaves like a real co teacher.

* She **listens** to the classroom while remaining aware of the ongoing conversation.
* She **speaks** when addressed, invited, or when intervention is appropriate.
* She **explains** concepts using the lesson material provided by the teacher.
* She **draws** explanations on a shared whiteboard.
* She **visualizes** complex concepts through interactive 3D learning experiences and educational models.
* She **checks understanding** through live quizzes.
* She **detects learning gaps** while the class is still happening.
* She **supports struggling and absent students** through personalized follow up experiences.
* She **adapts explanations** according to student proficiency.
* She **never overrides the teacher**.

The central principle behind Athena is simple:

> **An AI co teacher should know not only what to say, but when to speak and when to stay silent.**

---

# Features

## 1. Live Voice Co Teaching

Athena joins the classroom's real time audio channel as a live participant.

Students and teachers can address Athena naturally, such as:

> “Athena, can you explain photosynthesis?”

She processes the classroom interaction and responds through natural voice.

### Key capabilities

* Real time speech recognition
* Language model reasoning
* Natural text to speech
* Teacher controlled invocation
* Lesson grounded responses
* Adjustable response verbosity
* Classroom aware conversation

Lesson material uploaded by the teacher is incorporated into Athena's context so explanations can use the terminology and content of the actual lesson instead of generic textbook responses.

---

# 2. Turn Taking and Restraint Model

The hardest part of an AI co teacher is not generating an answer.

It is knowing when **not** to answer.

Athena therefore uses a dedicated floor state machine on top of voice activity detection.

### Athena can exist in three primary states

**Listening**

Athena is monitoring the classroom and waiting for an appropriate reason to respond.

**Held Back**

Athena identifies something relevant but deliberately chooses not to interrupt the teacher.

**Speaking**

Athena has been given the floor and is actively responding.

### Teacher priority

If the teacher begins speaking while Athena is talking, Athena's current response is immediately interrupted.

The teacher always has the floor.

Athena also maintains a record of held back doubts so useful observations are not lost simply because she chose not to interrupt.

---

# 3. Shared Whiteboard

Athena includes a live collaborative whiteboard powered by Excalidraw.

The entire classroom can see the same board in real time.

### Capabilities

* Teacher annotations
* Athena generated diagrams
* Live collaborative drawing
* Shared classroom state
* Visual explanations during voice interaction

Athena can turn a spoken explanation into a visual representation directly in front of the class.

---

# 4. Interactive 3D Learning

Athena extends classroom learning beyond voice, slides, and static diagrams through interactive 3D educational experiences.

### 3D Books

Teachers can use interactive 3D learning content to make complex concepts more visual and engaging.

Students can explore concepts spatially while Athena explains what they are seeing.

### 3D Educational Models

Athena can integrate relevant educational 3D models through **Sketchfab**, allowing students to explore objects and structures interactively.

This can be particularly useful for topics where spatial understanding matters.

Examples include:

* Biology
* Human anatomy
* Chemistry
* Physics
* Geography
* Engineering
* Scientific structures

Instead of only saying:

> “This is how the structure works.”

Athena can explain the concept while students **see and explore the structure themselves**.

### Classroom integration

3D learning works alongside Athena's existing classroom capabilities.

**Voice explanation → 3D visualization → Whiteboard explanation → Quiz → Understanding check**

This turns Athena from a conversational AI into a more complete interactive learning environment.

---

# 5. Live Quizzes and Gap Detection

Athena does not wait until the end of a lesson to discover whether students understood the material.

She can conduct live quizzes during the classroom session.

### Quiz capabilities

* Timed multiple choice questions
* Teacher initiated quizzes
* Athena initiated quizzes
* Real time scoring
* Student level results
* Topic based assessment

Athena monitors quiz responses and identifies patterns.

If multiple students struggle with the same concept, Athena flags it as a **class wide learning gap**.

The teacher can then launch a targeted quiz or revisit that specific concept immediately.

---

# 6. Nobody Left Behind

Athena is designed to support students who may otherwise be overlooked in a classroom.

### Shared Workspace

Students can submit doubts and questions through a shared workspace.

Questions, teacher insights, key takeaways, and held back doubts can be organized and surfaced without interrupting the lesson.

### Targeted Reading

Athena can recommend supplementary material for struggling students.

The teacher retains approval before the material reaches the student.

### One on One Catch Up

Students can book individual catch up sessions with the teacher and Athena.

They can select:

* Available time
* Focus topic
* Preferred language

### Absent Student Dispatcher

Students who miss an entire class can receive a generated catch up package based on the actual classroom session.

The package can include:

* Session summary
* Key concepts
* Important takeaways
* Identified misconceptions
* Diagnostic quiz
* Relevant learning gaps

The package can also be dispatched through email using Resend.

---

# 7. Teacher Controls

Athena never becomes the authority inside the classroom.

The teacher remains in complete control.

### Available controls

| Control              | Effect                                                 |
| -------------------- | ------------------------------------------------------ |
| Bring Athena in      | Starts Athena's live agent session                     |
| Mute Athena          | Immediately silences Athena                            |
| Unmute Athena        | Restores her ability to speak                          |
| Send Athena out      | Removes Athena from the classroom                      |
| Cut off current turn | Immediately ends her current response                  |
| Force speak          | Makes Athena address a specific topic                  |
| Disable topic        | Prevents Athena from discussing a selected subject     |
| Student invocation   | Controls whether students can directly address Athena  |
| Student proficiency  | Sets the learning level used to calibrate explanations |

Every important Athena action can be overridden by the teacher.

---

# 8. Athena AI Assistant

Athena also includes a private teacher copilot.

This instance is visible only to the teacher and does not interrupt the classroom.

It can:

* Suggest check in questions
* Generate real world analogies
* Summarize how the class is progressing
* Draft challenge problems
* Help the teacher respond to classroom situations

The teacher can consult Athena privately while the main classroom interaction continues uninterrupted.

---

# 9. Post Class Report

When the session ends, Athena transforms the classroom activity into a structured report.

### Class insights

* Overall concept understanding
* Topics covered
* Questions asked
* Learning gaps
* Common misconceptions
* Quiz performance

### Student insights

* Proficiency level
* Questions asked
* Quiz performance
* Concept mastery
* Individual learning notes

The purpose is to give the teacher actionable information instead of leaving them with only a raw classroom transcript.

---

# 10. Multilingual Support

Athena supports multilingual classroom experiences through transcript translation and configurable participant language preferences.

This allows students with different language preferences to participate more comfortably in the same classroom.

Indian language support can also be enabled through Sarvam AI.

---

# 11. Screen Sharing

Permitted participants can share their screens with the classroom.

The teacher can control screen sharing permissions for individual students.

An active screen share can automatically become the main classroom view.

---

# 12. Avatar and Visual Presence

Athena has a visual presence inside the classroom rather than appearing only as an audio stream.

### Visual states

* Animated entrance when Athena joins
* Idle animation during the session
* Speaking animation when Athena is actively talking
* Visual indication of Athena's active state

This creates a recognizable classroom presence while keeping the interface focused on learning.

---

# Technology Stack

| Layer                   | Technology                                       |
| ----------------------- | ------------------------------------------------ |
| Frontend                | Next.js, React, TypeScript, Tailwind CSS         |
| Real Time Communication | Agora RTC, Agora RTM                             |
| AI Voice Agent          | Agora Conversational AI Engine, Agora Agents SDK |
| Speech To Text          | Deepgram, Sarvam AI                              |
| Language Models         | Agora resold OpenAI compatible models            |
| Text To Speech          | MiniMax TTS, Sarvam TTS                          |
| Backend                 | Node.js, Fastify, TypeScript                     |
| Shared Whiteboard       | Excalidraw                                       |
| 3D Learning             | Sketchfab                                        |
| Avatar Animation        | Lottie, HTML5 video                              |
| Email                   | Resend                                           |
| Database                | PostgreSQL                                       |
| Monorepo                | pnpm workspaces                                  |
| Shared Types            | @echosphere/shared types                         |

---

# Architecture

```text
                    ┌─────────────────────┐
                    │       Teacher       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Athena Classroom  │
                    └──────────┬──────────┘
                               │
             ┌─────────────────┼─────────────────┐
             │                 │                 │
             ▼                 ▼                 ▼
       Voice Agent        Visual Learning    Assessment
             │                 │                 │
             │          ┌──────┴──────┐          │
             │          │             │          │
             ▼          ▼             ▼          ▼
          Agora      Whiteboard    3D Models   Live Quiz
                         │         Sketchfab      │
                         │             │          │
                         └──────┬──────┘          │
                                │                 │
                                ▼                 ▼
                         Classroom State    Learning Gaps
                                │                 │
                                └────────┬────────┘
                                         ▼
                                Post Class Intelligence
```

---

# Implementation Flow

```text
Teacher Creates Session
          ↓
Students Join Classroom
          ↓
Teacher Brings Athena In
          ↓
Athena Connects Through Agora
          ↓
Classroom Audio and Context
          ↓
Athena Listening State
          ↓
Teacher Invocation or Relevant Intervention
          ↓
AI Reasoning
          ↓
Voice Response
          ↓
Visual Explanation
          ↓
Whiteboard or 3D Learning
          ↓
Live Quiz
          ↓
Learning Gap Detection
          ↓
Targeted Support
          ↓
Session Summary
          ↓
Post Class Report
          ↓
Personalized Catch Up
```

---

# System Architecture

```text
┌──────────────────────┐
│      apps/web        │
│      Next.js         │
│                      │
│ Teacher Dashboard    │
│ Student Classroom    │
│ Whiteboard           │
│ Workspace            │
│ Quiz Interface       │
│ 3D Learning View     │
└──────────┬───────────┘
           │
           │ REST + SSE
           │
           ▼
┌────────────────────────────┐
│     apps/orchestrator      │
│      Fastify + Node.js     │
│                            │
│ Agent Lifecycle            │
│ Floor State Machine        │
│ Session State              │
│ Quiz Engine                │
│ Gap Detection              │
│ Support System             │
│ Report Generation          │
└────────────┬───────────────┘
             │
             │
             ▼
┌────────────────────────────┐
│        Agora Cloud         │
│                            │
│ RTC                        │
│ RTM                        │
│ Conversational AI Engine   │
└────────────┬───────────────┘
             │
             ▼
      Live AI Co Teacher
```

---

# Getting Started

## Prerequisites

* Node.js
* pnpm
* Agora project
* Agora App ID
* Agora App Certificate
* Agora Conversational AI credentials
* Resend API key for absent student email dispatch
* Optional Sarvam AI credentials

## Installation

```bash
pnpm install
```

## Run Frontend

```bash
pnpm --filter web dev
```

## Run Orchestrator

```bash
pnpm --filter @echosphere/orchestrator dev
```

The frontend runs on port 3000.

The orchestrator runs on port 8787.

---

# Environment Variables

```env
NEXT_PUBLIC_AGORA_APP_ID=
NEXT_AGORA_APP_CERTIFICATE=

AGORA_CUSTOMER_ID=
AGORA_CUSTOMER_SECRET=

LLM_MODEL=gpt 4o mini

SARVAM_API_KEY=
SARVAM_SPEAKER=
SARVAM_TARGET_LANGUAGE_CODE=

RESEND_API_KEY=

DATABASE_URL=

PORT=8787
CORS_ORIGINS=http://localhost:3000
```

---

# Project Structure

```text
apps/
│
├── web/
│   ├── app/
│   │   ├── join/
│   │   ├── teacher/[sessionId]/
│   │   └── classroom/[sessionId]/
│   │
│   └── components/
│       ├── classroom/
│       ├── workspace/
│       ├── support/
│       ├── learning/
│       └── meraki/
│
├── orchestrator/
│   └── src/
│       ├── agent/
│       ├── routes/
│       ├── support/
│       ├── gaps/
│       └── state/
│
└── packages/
    └── shared types/
```

---

# What Makes Athena Different

Athena is not designed to replace the teacher.

She is designed to make the teacher more capable.

She can listen to a classroom, understand what is happening, explain concepts, visualize ideas, detect confusion, support individual students, and turn classroom activity into actionable insight.

But the teacher always has the final say.

**Athena does not run the classroom.**

**The teacher does.**

Athena is the co teacher who knows exactly when to speak, when to visualize, when to intervene, and when to stay silent.

---

# Built With Agora

Athena EchoSphere is built on Agora's real time infrastructure, combining live classroom communication with conversational AI to create an AI participant that can actually exist inside the classroom.

**Athena EchoSphere**

**A teacher, with a co teacher who knows when to speak and when not to.**
