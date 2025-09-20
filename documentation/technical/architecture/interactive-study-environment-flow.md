# Interactive Study Environment - Learning Flow Architecture

## Overview

This document outlines the two distinct learning approaches within the Interactive Study Environment: Course-Driven Learning and As-You-Go Learning.

## Learning Flow Diagram

```mermaid
graph TD
    A[Interactive Study Environment] --> B[Course-Driven Learning]
    A --> C[As-You-Go Learning]
    
    %% Course-Driven Learning Branch
    B --> D[AI Course Generation]
    B --> E[Multi-Source Integration]
    
    D --> F[Specify Topic]
    F --> G[AI Generates Course Outline]
    G --> H[Preview Course Structure]
    H --> I[Generate Full Course Content]
    
    E --> J[Upload Multiple Sources]
    J --> K[AI Analyzes & Extracts Concepts]
    K --> L[Formulate Unified Topic]
    
    I --> M[Topic Customization]
    L --> M
    M --> N[Exclude Topics]
    M --> O[Set Focus Levels]
    N --> P[Generate Customized Course]
    O --> P
    
    %% As-You-Go Learning Branch
    C --> Q[AI-First Approach]
    C --> R[Post-Consumption Approach]
    
    Q --> S[Add Content Link]
    S --> T[AI Generates Summarized Points]
    T --> U[Consume Summarized Content]
    U --> V[Generate Cards from Summary]
    
    R --> W[Consume Original Content]
    W --> X[Add Content to System]
    X --> Y[Interactive Questioning]
    X --> Z[Direct Card Generation]
    
    Y --> AA[Ask Questions About Content]
    AA --> BB[AI Suggests Related Questions]
    BB --> CC[Select Questions for Cards]
    CC --> DD[Generate Cards from Questions]
    
    Z --> EE[AI Analyzes Content]
    EE --> FF[Generate Cards Automatically]
    FF --> GG[Review & Edit Cards]
    
    %% Content Processing Options
    V --> LL[Content Processing Settings]
    DD --> LL
    GG --> LL
    P --> LL
    
    LL --> MM[Option 1: Immediate Flashcard Generation]
    LL --> NN[Option 2: Question-Based Processing]
    LL --> OO[Option 3: Inbox Accumulation]
    
    MM --> PP[AI Generates Cards Automatically]
    PP --> QQ[User Reviews Generated Cards]
    QQ --> HH[Study Deck Integration]
    
    NN --> RR[System Generates Comprehension Questions]
    RR --> SS[User Answers Questions]
    SS --> TT[AI Creates Targeted Cards Based on Answers]
    TT --> QQ
    
    OO --> UU[Content Stored in Inbox]
    UU --> VV[User Processes Inbox When Ready]
    VV --> WW[Choose Processing Method]
    WW --> MM
    WW --> NN
    
    %% Integration Points
    HH --> JJ[Spaced Repetition Study]
    P --> II[Course Study Mode]
    II --> KK[Structured Course Study]
    
    %% Styling
    classDef courseDriven fill:#1e40af,stroke:#60a5fa,stroke-width:3px,color:#ffffff,font-size:14px,font-weight:bold
    classDef asYouGo fill:#dc2626,stroke:#f87171,stroke-width:3px,color:#ffffff,font-size:14px,font-weight:bold
    classDef aiProcess fill:#059669,stroke:#34d399,stroke-width:3px,color:#ffffff,font-size:14px,font-weight:bold
    classDef study fill:#d97706,stroke:#fbbf24,stroke-width:3px,color:#ffffff,font-size:14px,font-weight:bold
    classDef settings fill:#7c2d12,stroke:#f59e0b,stroke-width:3px,color:#ffffff,font-size:14px,font-weight:bold
    classDef processing fill:#1e40af,stroke:#3b82f6,stroke-width:3px,color:#ffffff,font-size:14px,font-weight:bold
    
    class B,D,E,F,G,H,I,J,K,L,M,N,O,P courseDriven
    class C,Q,R,S,T,U,V,W,X,Y,Z,AA,BB,CC,DD,EE,FF,GG asYouGo
    class G,K,T,BB,EE,PP,RR,TT aiProcess
    class HH,II,JJ,KK study
    class LL,MM,NN,OO,UU,VV,WW settings
    class QQ,SS processing
```

## Key Components

### Course-Driven Learning
- **AI Course Generation**: Create complete courses from AI knowledge
- **Multi-Source Integration**: Combine materials from various sources
- **Topic Customization**: Control topic inclusion and focus levels

### As-You-Go Learning
- **AI-First Approach**: Consume summarized content directly
- **Post-Consumption Approach**: Process content after consumption
  - Interactive Questioning: Ask questions and generate cards
  - Direct Card Generation: Generate cards directly from content

### Content Processing Options
- **Immediate Generation**: AI creates flashcards automatically upon content arrival
- **Question-Based Processing**: System generates comprehension questions before card creation
- **Inbox Accumulation**: Content stored for batch processing when user is ready

### Integration Points
- **Study Deck Integration**: All generated cards flow into unified study system
- **Course Study Mode**: Structured progression through course content
- **Spaced Repetition**: Proven study technique for retention

## Data Flow

1. **Content Input**: Users provide topics, materials, or content links
2. **AI Processing**: Content analysis, summarization, and concept extraction
3. **User Interaction**: Customization, questioning, and curation
4. **Card Generation**: Creation of study materials from processed content
5. **Study Integration**: Seamless flow into learning and review systems
