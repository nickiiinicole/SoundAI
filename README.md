# SoundAI - Database Design Project 

## Overview
**SoundAI** is a conceptual database design for a modern music streaming platform integrated with a conversational Artificial Intelligence (AI) assistant. This project was developed as part of the module "Database Management".

The database architecture is designed to prioritize technical simplicity while strictly fulfilling all advanced academic requirements, including complex entity relationships, hierarchies, and strict normalization (3NF).

## Academic Requirements Achieved 
This design successfully implements all the required structural patterns for a high-grade assessment:
- **Strong Entities**: `USERS`, `ARTISTS`, `ALBUMS`, `TRACKS`, `PLAYLISTS`, `CHAT_SESSIONS`.
- **Weak Entities (by Identification)**: `PLAYLIST_ITEMS`, `CHAT_MESSAGES`, `TRACKS_CREDIT`. Implemented correctly using composite Primary Keys (PK, FK) without artificial IDs.
- **Hierarchies (Subtyping)**:
  - Disjoint and Total (d, t) hierarchy for Users (`FREE_USERS`, `PREMIUM_USERS`).
  - Disjoint and Total (d, t) hierarchy for Artists (`SOLO_ARTISTS`, `BANDS`).
- **Reflexive Relationship**: 1:N relationship within `TRACKS` to handle original songs and their remixes (`remixed_from_id`).
- **N:M Relationships Resolved**: Handled via intermediate tables/weak entities (`CHATS_RECOMMENDS` for AI song recommendations, and `TRACKS_CREDIT` for artist collaborations).

## Database Schema Highlights 

### 1. Users Management
Handles the platform's user base with inheritance to separate free tier limitations (ads, skips) from premium tier features (renewal dates, payments).

### 2. Music Catalog
Organizes the core music data. Artists are subtyped into Solo Artists and Bands. Albums contain Tracks, and Tracks can reference other Tracks to represent remixes or covers.

### 3. Playlists System
Users can create multiple Playlists. The `PLAYLIST_ITEMS` weak entity ensures that tracks maintain a specific order (`order_position`) and can be duplicated within the same playlist (e.g., repeating a favorite song).

### 4. AI Chat Assistant
Users can start `CHAT_SESSIONS`. Each session identifies multiple `CHAT_MESSAGES` (ordered sequentially). The AI can recommend tracks directly in the chat, resolved through the `CHATS_RECOMMENDS` association table.

## Project Deliverables 
- **Conceptual Model (ER Diagram)**: Modeled using standard Barker/Oracle notation (`#`, `*`, `º`).
- **Relational Model (Tables)**: Fully normalized schema (3NF) clearly defining Primary Keys (PK), Foreign Keys (FK), and data types.
- **Textual Summary**: Relational schema written in standard textual notation (`WHERE ... REFERENCES`).

---
