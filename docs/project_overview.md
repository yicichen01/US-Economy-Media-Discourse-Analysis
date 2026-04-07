# Project Overview

## Background

Public discussion of the U.S. economy is shaped not only by official indicators and expert commentary, but also by how economic issues are framed in media content and interpreted by audiences. On platforms such as YouTube, economy-related news videos generate large volumes of user comments that reflect reactions to inflation, prices, jobs, recession concerns, political leadership, and broader social frustration or optimism.

This project was designed to examine that comment space as a form of public discourse. Rather than treating comments as noise, I approached them as a text corpus that can reveal recurring themes, vocabulary patterns, and shifts in tone across economy-related media content.

## Project Goal

The goal of this project is to build a multi-stage text analytics workflow that moves from raw YouTube content collection to interpretable discourse analysis.

More specifically, the project aims to:

- collect economy-related YouTube videos and comments using a reproducible API-based workflow
- transform noisy comment text into an analysis-ready dataset
- examine dominant vocabulary, lexical signals, and sentiment patterns
- use topic modeling to identify recurring themes in public discussion of the U.S. economy

## Why This Project Matters

This project matters for two reasons.

First, it demonstrates a practical end-to-end analytics workflow. The project is not limited to one notebook or one model. It covers data collection, cleaning, exploratory analysis, and topic discovery in a connected pipeline.

Second, it focuses on a substantively meaningful topic. Public reactions to the economy are not just technical responses to economic indicators. They are also shaped by political narratives, media framing, and emotionally charged interpretations. By analyzing YouTube comments, this project explores how economy-related issues are discussed in a public-facing media environment.

## Scope

The project focuses on YouTube content related to the U.S. economy. It does not attempt to measure public opinion in a statistically representative way, nor does it treat YouTube comments as a direct proxy for the full population. Instead, the project treats the comment corpus as a rich and observable space for studying recurring discourse patterns in response to economy-related media content.

The analysis is organized into three stages:

1. **Data collection**  
   Identify economy-related videos and collect video-level and comment-level data using the YouTube API.

2. **Data preparation and exploratory analysis**  
   Clean the text, inspect data quality, compare tokenization and sentiment methods, and explore early linguistic patterns.

3. **Topic discovery and text pattern analysis**  
   Represent the cleaned comments as a corpus, examine frequent terms, and use topic modeling to uncover broader themes.

## Workflow Summary

The project pipeline can be summarized as:

**YouTube API collection → structured dataset creation → text cleaning → exploratory analysis → topic modeling → interpretation**

This structure is important because it turns a set of exploratory notebooks into a coherent analytical system. Each stage produces outputs that directly support the next stage.

## Repository Components

The repository contains four main components:

- `data/processed/`  
  Structured datasets produced from YouTube content collection and preprocessing

- `notebooks/`  
  The primary analytical workflow, organized into three stages

- `assets/`  
  Visual outputs included in the README for quick interpretation

- `docs/`  
  Supporting documentation that explains the project’s design decisions, workflow, and findings in a more concise case-study format

## Overall

This project demonstrates the ability to:

- collect platform data using an API-based workflow
- clean and structure noisy user-generated text
- compare text processing methods rather than treating preprocessing as trivial
- apply exploratory and unsupervised text analysis methods
- communicate findings clearly through both narrative and visualization

