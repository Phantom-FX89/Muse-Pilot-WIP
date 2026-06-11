# Muse-Pilot (Work In Progress) 🎼

**A technical music intelligence platform for AI-assisted composition, arrangement, prompt synthesis, and production workflow design.**

Muse-Pilot is a work-in-progress system that transforms creative intent, music theory constraints, audio features, and production references into structured composition and arrangement guidance.

It is not just an AI music prompt generator.

Muse-Pilot is designed as a **music intelligence layer**: a system that helps creators reason about songs before, during, and after generation or production.

---

## Table of Contents

- [Overview](#overview)
- [Core Thesis](#core-thesis)
- [What Muse-Pilot Does](#what-muse-pilot-does)
- [System Architecture](#system-architecture)
- [Core Engines](#core-engines)
- [Scientific and Technical Foundation](#scientific-and-technical-foundation)
- [MVP Scope](#mvp-scope)
- [Product Features](#product-features)
- [Research Layer](#research-layer)
- [Data Flow](#data-flow)
- [Example Workflows](#example-workflows)
- [Tech Stack](#tech-stack)
- [Suggested Project Structure](#suggested-project-structure)
- [Getting Started](#getting-started)
- [Environment Variables](#environment-variables)
- [Database Model Ideas](#database-model-ideas)
- [Evaluation Strategy](#evaluation-strategy)
- [Roadmap](#roadmap)
- [Development Philosophy](#development-philosophy)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Muse-Pilot explores the intersection of music production, music information retrieval, machine learning, music theory, prompt engineering, and creative workflow systems.

The platform is designed to help answer technical and creative questions such as:

- What musical information can be extracted from an idea, reference, or audio file?
- How can creative intent be converted into structured musical context?
- How can theory-based systems suggest useful chord progressions and arrangements?
- How can AI prompts be generated from structured musical data instead of vague text?
- How can generated outputs be evaluated, versioned, and improved over time?
- How can reusable sonic identities and song templates become part of a creator's workflow?

Muse-Pilot supports both traditional production workflows and AI-assisted music generation pipelines.

---

## Core Thesis

Most AI music tools focus on generating audio.

Muse-Pilot focuses on the intelligence layer around the music.

The system is based on a simple premise:

> Better musical context creates better musical output.

Muse-Pilot converts loose creative inputs into structured data that can drive arrangement planning, harmonic suggestions, prompt generation, production notes, and future audio intelligence workflows.

The long-term goal is to build a system that can reason across:

- Creative intent
- Genre conventions
- Mood and emotion
- Music theory
- Audio features
- Arrangement structure
- Sonic identity
- AI model behavior
- Production workflow history

---

## What Muse-Pilot Does

Muse-Pilot helps creators move from raw idea to production-ready direction.

At a high level, the system:

1. Captures creative intent.
2. Converts that intent into structured musical context.
3. Applies theory and arrangement logic.
4. Generates AI music prompts, production briefs, or song plans.
5. Stores versions, outputs, and notes.
6. Learns reusable patterns over time.

Muse-Pilot can support workflows such as:

- Song ideation
- AI music prompt generation
- Arrangement planning
- Chord progression design
- Sonic identity development
- Playlist and channel music systems
- Production brief creation
- Future audio feature analysis
- Future MIDI and DAW export

---

## System Architecture

The system is organized into several modular layers.

```text
User Input
    ↓
Creative Context Engine
    ↓
Musical Context Engine
    ↓
Theory Engine
    ↓
Arrangement Engine
    ↓
Prompt Synthesis Engine
    ↓
AI Provider Layer
    ↓
Output + Evaluation Layer
    ↓
Versioned Memory / Pattern Library
```

For future audio-aware features:

```text
Audio Input
    ↓
Audio Feature Extraction
    ├── Mel-Spectrograms
    ├── MFCCs
    ├── Chroma Features
    ├── Onsets
    ├── Tempo
    └── Harmonic / Percussive Separation
        ↓
Music Understanding Layer
    ├── Key Estimation
    ├── Chord Estimation
    ├── Energy Mapping
    ├── Timbre Analysis
    └── Structural Segmentation
        ↓
Theory + Arrangement Layer
        ↓
Prompt / MIDI / Marker / Brief Output
```

---

## Core Engines

## 1. Creative Context Engine

The Creative Context Engine captures the user's musical intent and turns it into structured metadata.

It stores information such as:

- Song title
- Project name
- Mood
- Genre
- Subgenre
- Tempo range
- Key
- Mode
- Energy level
- Vocal direction
- Instrumentation
- Reference tracks
- Lyric notes
- Audience
- Use case
- Production notes

This layer prevents prompts and music briefs from being vague. Instead of asking the AI model to infer everything, Muse-Pilot gives it structured context.

---

## 2. Musical Context Engine

The Musical Context Engine normalizes music-specific data so it can be used across the app.

It may represent:

- Tempo as BPM or BPM range
- Key as tonic + mode
- Chords as symbolic objects
- Sections as ordered song blocks
- Instruments as categorized roles
- Energy as a curve over time
- Genre as a ruleset or style profile
- References as weighted influence tags

Example normalized song context:

```json
{
  "title": "Midnight Garden",
  "genre": "lofi hip-hop",
  "mood": ["warm", "nostalgic", "dreamy"],
  "tempo_bpm": 78,
  "key": {
    "tonic": "F",
    "mode": "minor"
  },
  "sections": ["intro", "verse", "hook", "bridge", "outro"],
  "instrumentation": ["felt piano", "vinyl drums", "sub bass", "soft pad"],
  "energy_curve": [0.25, 0.45, 0.7, 0.55, 0.3]
}
```

---

## 3. Theory Engine

The Theory Engine applies deterministic music theory logic before relying on generative AI.

This is important because many musical decisions can be constrained by known relationships instead of guessed entirely by a model.

The Theory Engine may support:

- Key and mode recommendations
- Diatonic chord generation
- Common progression templates
- Borrowed chord suggestions
- Cadence detection
- Tension and release mapping
- Section contrast logic
- Bass movement suggestions
- Harmonic rhythm suggestions
- Voicing recommendations

Example chord progression object:

```json
{
  "key": "F minor",
  "progression": ["Fm", "Db", "Ab", "Eb"],
  "roman_numerals": ["i", "VI", "III", "VII"],
  "mood": "dark but uplifting",
  "recommended_use": "chorus or hook",
  "tension_level": 0.62
}
```

The Theory Engine should remain explainable. When Muse-Pilot suggests a progression, it should also be able to explain why the progression fits the user's emotional and structural target.

---

## 4. Arrangement Engine

The Arrangement Engine converts musical context into a section-by-section song plan.

It reasons about:

- Song form
- Energy curve
- Instrument entrance and exit
- Section contrast
- Dynamic development
- Repetition vs variation
- Breakdown placement
- Hook arrival
- Outro design

Example arrangement plan:

```json
{
  "sections": [
    {
      "name": "Intro",
      "bars": 8,
      "energy": 0.25,
      "elements": ["filtered piano", "vinyl texture"],
      "purpose": "establish mood and harmonic color"
    },
    {
      "name": "Verse",
      "bars": 16,
      "energy": 0.45,
      "elements": ["drums", "bass", "piano motif"],
      "purpose": "introduce groove and melodic identity"
    },
    {
      "name": "Hook",
      "bars": 16,
      "energy": 0.75,
      "elements": ["full drums", "bass", "lead melody", "pads"],
      "purpose": "deliver emotional peak"
    }
  ]
}
```

---

## 5. Prompt Synthesis Engine

The Prompt Synthesis Engine converts structured musical data into high-quality prompts for AI music tools.

Rather than generating prompts from loose text, it builds prompts from structured fields:

```text
Genre + Mood + Tempo + Key + Arrangement + Instruments + Vocal Direction + Mix Notes + Avoid List
```

This allows prompts to be:

- More consistent
- Easier to revise
- Easier to compare
- Easier to reuse
- More aligned with the intended sound

Example prompt output:

```text
Create a warm, nostalgic lofi hip-hop instrumental in F minor at 78 BPM. 
Use felt piano, soft vinyl drums, gentle sub bass, and airy background pads. 
The arrangement should start with an intimate 8-bar intro, build into a relaxed verse groove, 
and reach a fuller hook with a memorable melodic motif. 
Keep the mix warm, rounded, and slightly dusty. Avoid aggressive drums, bright EDM synths, or overly clean pop production.
```

---

## 6. AI Provider Layer

The AI Provider Layer abstracts calls to external models.

Initial providers may include:

- OpenAI
- Anthropic
- Future music generation APIs
- Future local models

The provider layer should allow the system to route tasks based on function:

- Prompt generation
- Theory explanation
- Arrangement drafting
- Lyric development
- Sonic identity refinement
- Diagnostic review

Suggested provider interface:

```ts
export interface AIProvider {
  name: string;

  generate(input: {
    task: string;
    systemPrompt?: string;
    userPrompt: string;
    model: string;
    temperature?: number;
    metadata?: Record<string, unknown>;
  }): Promise<{
    output: string;
    tokenUsage?: {
      inputTokens?: number;
      outputTokens?: number;
      totalTokens?: number;
    };
    raw?: unknown;
  }>;
}
```

---

## 7. Output + Evaluation Layer

The Output + Evaluation Layer stores generated results and user feedback.

It tracks:

- Generated prompts
- Arrangement plans
- Chord progression suggestions
- Production briefs
- User notes
- Ratings
- Version history
- Result quality
- Export history

This allows Muse-Pilot to learn which creative structures work best for specific genres, projects, and sonic identities.

---

## Scientific and Technical Foundation

Muse-Pilot combines deterministic symbolic music logic with machine learning and AI-assisted generation.

The key technical areas are:

---

## Music Information Retrieval

Music Information Retrieval, or MIR, is the process of extracting musical features from audio.

Muse-Pilot's future audio-aware layer may use MIR techniques such as:

### Mel-Spectrograms

Mel-spectrograms represent audio frequency content over time using a perceptually motivated frequency scale.

Use cases:

- Timbre analysis
- Audio similarity
- Model input features
- Generative audio experiments
- Texture comparison

### MFCCs

Mel-frequency cepstral coefficients summarize timbral characteristics.

Use cases:

- Sound classification
- Timbre clustering
- Reference matching
- Instrument texture analysis

### Chroma Features

Chroma features represent pitch class energy across the 12 notes of the octave.

Use cases:

- Key detection
- Chord estimation
- Harmonic similarity
- Progression analysis

### Onset Detection

Onset detection identifies where musical events begin.

Use cases:

- Rhythm analysis
- Beat tracking
- Groove estimation
- Section segmentation

### Tempo Estimation

Tempo estimation identifies the approximate BPM of audio.

Use cases:

- Matching references
- Suggesting tempo ranges
- Aligning generated outputs
- Arrangement planning

---

## Harmonic-Percussive Source Separation

Harmonic-Percussive Source Separation, or HPSS, decomposes audio into harmonic and percussive components.

```text
Input Audio
    ↓
Short-Time Fourier Transform
    ↓
Median Filtering
    ├── Harmonic Component
    └── Percussive Component
```

This can help Muse-Pilot analyze melodic and rhythmic information separately.

Potential uses:

- Cleaner harmonic analysis
- Drum groove extraction
- Melody-focused feature extraction
- Rhythmic pattern detection
- Independent processing of tonal and percussive content

---

## Representation Learning

Representation learning allows models to learn compressed musical feature spaces.

Muse-Pilot may use this in future research modules to study timbre, texture, and style.

### Variational Autoencoders

A VAE can learn a latent representation of audio features such as mel-spectrograms.

Potential uses:

- Timbre interpolation
- Sound similarity
- Style exploration
- Latent space navigation
- Audio texture clustering

Research direction:

```text
Mel-Spectrogram
    ↓
Encoder
    ↓
Latent Space
    ↓
Decoder
    ↓
Reconstructed Spectrogram
```

β-VAE training may be used to encourage more disentangled latent representations and reduce posterior collapse.

---

## Sequence Modeling

Muse-Pilot may use sequence models for arrangement and structure prediction.

Possible model types:

- LSTM encoder-decoder models
- Transformer models
- Markov-style symbolic systems
- Hybrid rule-based + model-based predictors

Potential inputs:

- Chord progressions
- Melody contours
- Section labels
- Genre tags
- Energy curves
- Instrumentation states

Potential outputs:

- Suggested next section
- Instrument entrance plan
- Chord variation
- Arrangement density
- Dynamic curve
- Transition ideas

---

## Prompt Synthesis

Prompt synthesis is the process of transforming structured musical context into natural language prompts.

Muse-Pilot's prompt synthesis layer should be deterministic where possible and AI-assisted where useful.

Suggested process:

```text
Structured Music Context
    ↓
Prompt Template Selection
    ↓
Field Normalization
    ↓
Constraint Injection
    ↓
Style and Genre Expansion
    ↓
AI-Assisted Refinement
    ↓
Exportable Prompt
```

This creates prompts that are consistent, reusable, and easier to evaluate.

---

## Deterministic Logic vs AI Reasoning

Muse-Pilot should not use AI for everything.

A strong architecture separates deterministic logic from generative reasoning.

### Deterministic Logic

Best for:

- Chord spelling
- Diatonic chord generation
- Tempo validation
- Section ordering
- Data normalization
- Template filling
- Export formatting
- Schema validation

### AI Reasoning

Best for:

- Creative interpretation
- Mood expansion
- Lyric direction
- Sonic description
- Arrangement explanation
- Prompt rewriting
- Reference blending
- Taste-based suggestions

This keeps the system more reliable while still allowing creative flexibility.

---

## MVP Scope

The MVP should prioritize the product layer and use deterministic music logic wherever possible.

### MVP Includes

- User authentication
- Project creation
- Song idea storage
- Creative brief builder
- Sonic identity profiles
- Key, tempo, genre, and mood fields
- Basic chord progression suggestions
- Basic arrangement planning
- AI music prompt generation
- Prompt versioning
- Exportable briefs
- Notes and ratings
- Template library

### MVP Does Not Include

- Real-time audio generation
- DAW plugin integration
- Multi-GPU inference
- Commercial audio model training
- Advanced mastering tools
- Autonomous composition agents
- Full audio-to-MIDI transcription
- Live performance synthesis

The first version should be a useful music intelligence workspace before becoming an advanced audio ML system.

---

## Product Features

## Creative Brief Builder

Create structured music briefs from creative intent.

Fields may include:

- Title
- Mood
- Genre
- Subgenre
- Tempo
- Key
- References
- Vocal direction
- Instrumentation
- Lyric direction
- Mix notes
- Arrangement notes
- Avoid list

---

## Sonic Identity Profiles

Store reusable sound profiles for artists, channels, playlists, or content brands.

A sonic identity may include:

- Core genres
- Emotional palette
- Tempo range
- Favorite instruments
- Vocal style
- Mix style
- Reference artists
- Prompt patterns
- Avoid list
- Release format

---

## Arrangement Assistant

Generate section-by-section arrangement plans.

Potential outputs:

- Song structure
- Section purpose
- Bar counts
- Energy curve
- Instrument entrances
- Transition notes
- Hook placement
- Breakdown ideas

---

## Harmonic Direction Assistant

Generate theory-aware chord and key suggestions.

Potential outputs:

- Key recommendation
- Mode suggestion
- Chord progression options
- Roman numeral analysis
- Emotional interpretation
- Section-specific progressions
- Tension and release explanation

---

## AI Music Prompt Generator

Generate prompts for AI music tools.

Prompt fields may include:

- Genre
- Mood
- Tempo
- Key
- Instrumentation
- Song structure
- Vocal direction
- Production style
- Mix notes
- Negative instructions
- Output constraints

---

## Template Library

Save reusable workflows for common production tasks.

Examples:

- Lofi instrumental prompt
- Kids song prompt
- Worship arrangement brief
- Cinematic cue structure
- Trap beat direction
- AI influencer theme song
- YouTube music channel template
- Playlist sonic identity

---

## Research Layer

The original Muse-Pilot concept included deeper ML experiments. These remain important, but they should be treated as research modules that support the product over time.

---

## Active / Future Experiments

### 1. Mel-Spectrogram Variational Autoencoder

Learns latent representations of musical timbre.

Goals:

- Learn compact timbre embeddings
- Enable interpolation between sound textures
- Explore β-VAE training
- Compare reconstruction quality using spectral metrics
- Use latent vectors for timbre exploration

---

### 2. Harmonic-Percussive Source Separation

Separates audio into harmonic and percussive components.

Goals:

- Improve harmonic analysis
- Isolate rhythmic information
- Support reference track analysis
- Enable independent processing of melodic and percussive elements

---

### 3. Sequence-to-Sequence Arrangement Model

Uses musical sequences to generate arrangement suggestions.

Inputs may include:

- Chord progression
- Melody contour
- Genre
- Section labels
- Energy curve

Outputs may include:

- Section order
- Instrumentation changes
- Chord variations
- Transition suggestions

---

### 4. Real-Time Synthesis Backend

Explores low-latency generation for future interactive workflows.

Goals:

- Investigate sub-100ms interaction targets
- Test model compression
- Explore streaming inference
- Evaluate live performance feasibility

This is not an MVP requirement.

---

## Data Flow

### MVP Data Flow

```text
User creates project
    ↓
User creates song idea
    ↓
System stores musical context
    ↓
Theory Engine generates options
    ↓
Arrangement Engine creates structure
    ↓
Prompt Synthesis Engine creates prompt
    ↓
User exports prompt or brief
    ↓
User saves notes and result feedback
```

### Future Audio Analysis Flow

```text
User uploads audio reference
    ↓
System extracts audio features
    ↓
System estimates tempo, key, and energy
    ↓
System maps sonic and structural traits
    ↓
System generates prompt or arrangement recommendations
    ↓
User saves findings to sonic identity or song idea
```

---

## Example Workflows

### AI Music Prompt Workflow

```text
Create Song Idea
    ↓
Define Mood + Genre
    ↓
Select Sonic Identity
    ↓
Generate Arrangement Plan
    ↓
Generate AI Music Prompt
    ↓
Export to Suno / Udio / Other Tool
    ↓
Save Result Notes
    ↓
Refine Prompt Version
```

### Producer Planning Workflow

```text
Create Project
    ↓
Add References
    ↓
Define Key + Tempo
    ↓
Generate Chord Options
    ↓
Build Section Map
    ↓
Add Instrumentation Notes
    ↓
Export Production Brief
```

### Audio Analysis Workflow

```text
Upload Reference Audio
    ↓
Extract Features
    ↓
Analyze Tempo / Key / Chroma / Timbre
    ↓
Generate Musical Summary
    ↓
Save to Sonic Identity
    ↓
Use as Context for Future Prompts
```

---

## Tech Stack

## Product Stack

- Next.js
- React
- TypeScript
- Tailwind CSS
- shadcn/ui
- Supabase
- PostgreSQL
- Prisma ORM
- Vercel

## AI Layer

- OpenAI API
- Anthropic API
- Future music generation APIs
- Future local model support

## Audio / Research Stack

- Python
- librosa
- scipy.signal
- PyTorch
- torchaudio
- FastAPI
- Docker
- Web Audio API
- ONNX Runtime

---

## Suggested Project Structure

```text
muse-pilot/
├── app/
│   ├── dashboard/
│   ├── projects/
│   ├── songs/
│   ├── prompts/
│   ├── identities/
│   ├── templates/
│   └── api/
├── components/
│   ├── ui/
│   ├── projects/
│   ├── songs/
│   ├── prompts/
│   ├── arrangements/
│   └── layout/
├── lib/
│   ├── ai/
│   ├── db/
│   ├── music/
│   │   ├── theory/
│   │   ├── harmony/
│   │   ├── arrangement/
│   │   └── prompts/
│   ├── supabase/
│   ├── validators/
│   └── utils/
├── services/
│   ├── project-service.ts
│   ├── song-service.ts
│   ├── theory-service.ts
│   ├── arrangement-service.ts
│   ├── prompt-service.ts
│   ├── identity-service.ts
│   └── export-service.ts
├── research/
│   ├── audio_features/
│   ├── hpss/
│   ├── vae/
│   ├── sequence_models/
│   └── notebooks/
├── prompts/
│   ├── song-briefs/
│   ├── arrangements/
│   ├── sonic-identities/
│   └── ai-music/
├── database/
│   ├── migrations/
│   └── schema.prisma
├── types/
├── hooks/
├── public/
├── .env.example
├── package.json
└── README.md
```

---

## Getting Started

### Prerequisites

Install the following before running the project:

- Node.js 20+
- npm, pnpm, or bun
- Supabase account
- OpenAI API key
- Anthropic API key, optional but recommended

For research experiments:

- Python 3.11+
- PyTorch
- librosa
- scipy
- torchaudio

---

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/muse-pilot.git
cd muse-pilot
```

Install dependencies:

```bash
npm install
```

Create an environment file:

```bash
cp .env.example .env.local
```

Run the development server:

```bash
npm run dev
```

Open the app:

```text
http://localhost:3000
```

---

## Environment Variables

Create a `.env.local` file in the project root.

```bash
# App
NEXT_PUBLIC_APP_URL=http://localhost:3000

# Supabase
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=
SUPABASE_SERVICE_ROLE_KEY=

# Database
DATABASE_URL=
DIRECT_URL=

# AI Providers
OPENAI_API_KEY=
ANTHROPIC_API_KEY=

# Optional Analytics
NEXT_PUBLIC_POSTHOG_KEY=
NEXT_PUBLIC_POSTHOG_HOST=
```

---

## Suggested Scripts

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint",
    "typecheck": "tsc --noEmit",
    "db:generate": "prisma generate",
    "db:migrate": "prisma migrate dev",
    "db:push": "prisma db push",
    "db:studio": "prisma studio"
  }
}
```

---

## Database Model Ideas

### `projects`

Stores albums, playlists, channels, artist concepts, or production campaigns.

Suggested fields:

- `id`
- `user_id`
- `name`
- `description`
- `project_type`
- `status`
- `created_at`
- `updated_at`

---

### `song_ideas`

Stores individual song concepts.

Suggested fields:

- `id`
- `project_id`
- `user_id`
- `title`
- `genre`
- `subgenre`
- `mood`
- `tempo_bpm`
- `key`
- `mode`
- `references`
- `lyrics`
- `notes`
- `status`
- `created_at`
- `updated_at`

---

### `sonic_identities`

Stores reusable sound profiles.

Suggested fields:

- `id`
- `user_id`
- `project_id`
- `name`
- `description`
- `genres`
- `moods`
- `tempo_range`
- `instrumentation`
- `vocal_style`
- `mix_style`
- `references`
- `avoid_list`
- `prompt_patterns`
- `created_at`
- `updated_at`

---

### `arrangement_plans`

Stores section-by-section structures.

Suggested fields:

- `id`
- `song_id`
- `sections`
- `chord_progressions`
- `instrumentation_notes`
- `energy_curve`
- `transition_notes`
- `created_at`
- `updated_at`

---

### `prompt_briefs`

Stores AI music prompts and versions.

Suggested fields:

- `id`
- `song_id`
- `user_id`
- `provider_target`
- `prompt`
- `negative_prompt`
- `version_number`
- `notes`
- `rating`
- `created_at`

---

### `templates`

Stores reusable music workflows and prompt structures.

Suggested fields:

- `id`
- `user_id`
- `name`
- `template_type`
- `description`
- `inputs`
- `workflow`
- `output_format`
- `created_at`
- `updated_at`

---

### `audio_analyses`

Future table for uploaded audio analysis.

Suggested fields:

- `id`
- `user_id`
- `project_id`
- `song_id`
- `file_url`
- `tempo_bpm`
- `estimated_key`
- `chroma_summary`
- `mfcc_summary`
- `energy_curve`
- `analysis_metadata`
- `created_at`

---

## Evaluation Strategy

Muse-Pilot should evaluate both technical quality and creative usefulness.

### Technical Evaluation

Possible metrics:

- Key detection confidence
- Tempo estimation confidence
- Spectral distance
- Chroma similarity
- Section consistency
- Prompt completeness
- Schema validity

### Creative Evaluation

Possible ratings:

- Mood accuracy
- Genre fit
- Arrangement usefulness
- Prompt clarity
- Production usefulness
- Output quality
- Reusability

### User Feedback

Users should be able to track:

- Which prompt worked
- Which version failed
- Which sonic identity created the best results
- Which arrangement structure produced better songs
- Which references improved consistency

---

## Roadmap

### Phase 1 — Muse Lab

- Authentication
- Project creation
- Song idea storage
- Creative brief builder
- Sonic identity profiles
- Basic chord progression suggestions
- Arrangement plan generation
- AI prompt generation
- Prompt versioning
- Exportable briefs

---

### Phase 2 — Music Intelligence Layer

- Expanded theory engine
- Key and mode recommendations
- Chord progression library
- Section-aware arrangement logic
- Template library
- Personal Bank
- Prompt comparison
- User rating history

---

### Phase 3 — Audio-Aware Assistance

- Audio upload support
- Feature extraction
- Tempo estimation
- Chroma features
- Key detection
- Energy curve extraction
- Audio summary generation
- Save audio traits to sonic identity

---

### Phase 4 — DAW and Creator Workflow Expansion

- MIDI export
- Arrangement marker export
- Prompt batch generation
- Release planning tools
- Sample and preset recommendations
- AI music platform integrations
- DAW plugin exploration

---

### Phase 5 — Advanced Research

- VAE experiments
- GAN experiments
- Transformer sequence modeling
- Differentiable DSP
- Multi-modal learning with audio, MIDI, and text
- Reinforcement learning for composition optimization
- Real-time interactive generation

---

## Development Philosophy

Muse-Pilot should be:

- Music-first
- Explainable
- Practical
- Modular
- Fast to test
- Useful before flashy
- Research-informed but product-led

The project should not chase every AI music trend at once.

The best version of Muse-Pilot starts as a reliable music intelligence workspace, then expands into deeper audio intelligence as the product earns it.

Build the cockpit first. Add the jet engine later.

---

## Contributing

Muse-Pilot is an active work-in-progress exploring AI-assisted music production and music intelligence systems.

Useful contribution areas may include:

- Music theory utilities
- Prompt generation templates
- Arrangement logic
- AI provider integrations
- Supabase schema improvements
- UI components
- Export formats
- Audio feature extraction experiments
- MIDI workflow research
- MIR experiments

Before contributing, open an issue or discussion describing the proposed change.

---

## License

MIT License.

---

## Final Thought

Muse-Pilot is built around one belief:

Great music tools should not only generate sound.

They should help creators understand, shape, refine, and finish better music.
