# Data Collection

## Objective

The purpose of the data collection stage was to build a structured YouTube comment dataset centered on U.S. economy-related media content.

Rather than scraping broad, unfiltered platform data, I designed a targeted collection workflow that focused on identifying economy-relevant videos first and then retrieving their associated comments. This made the dataset more suitable for downstream discourse analysis and reduced noise from unrelated uploads.

## Collection Strategy

The workflow began with topic definition. Because YouTube news channels publish content across many domains, the first challenge was identifying which videos were genuinely related to the U.S. economy.

To address this, I developed a keyword-based filtering strategy using terms that are strongly associated with economy-focused news coverage. These included both broad terms and issue-specific terms, such as:

- U.S. economy / U.S. economic
- economy / economic
- inflation
- recession
- price / prices
- job market

The keyword list was designed to capture both explicitly economy-labeled videos and videos framed around everyday economic concerns.

## YouTube Video Retrieval

Using the YouTube API, I retrieved uploaded videos from selected YouTube news channels and examined video titles for keyword matches. Matching was handled in a case-insensitive way, and simple wording variations were treated as equivalent when appropriate.

The goal of this step was not to collect every video from a channel, but to create a topic-focused subset of content that could support meaningful analysis of economy-related discourse.

For each matched video, I retained relevant metadata such as:

- channel name
- video ID
- video title
- video creation time
- video view count

These fields were useful not only for documentation, but also for connecting comments back to the media context in which they appeared.

## Comment Extraction

After identifying relevant videos, I used the YouTube API to collect comments for each one.

The extraction focused on comment-level records rather than only video-level metadata because the project’s core analytical interest lies in audience discourse. Comments provide the text corpus that later stages of the project analyze through cleaning, tokenization, sentiment-oriented inspection, and topic modeling.

For each comment, I retained fields such as:

- comment ID
- comment text
- comment creation time
- comment like count
- associated video metadata

This made the final dataset comment-centric while preserving enough video context to support richer interpretation later.

## Building the Structured Dataset

Once the video and comment data were collected, I assembled them into a Pandas data frame where each row represented one comment.

This row-level structure was important because it allowed the dataset to function both as:

- a text corpus for NLP and topic modeling
- a structured data table that preserves contextual information such as channel, title, timestamp, and engagement metrics

The final dataset was exported as a CSV file for use in the later stages of the project.

## Design Decisions

A few collection design choices were especially important:

### 1. Topic filtering before analysis
Instead of collecting comments from all videos and trying to filter later, I filtered videos by topic first. This made the dataset more coherent and reduced downstream cleaning burden.

### 2. Comment-level structure
Each row in the dataset corresponds to a comment, not a video. This design supports text analysis directly while still allowing comments to be grouped back to videos and channels.

### 3. Metadata retention
I kept video-level metadata alongside comment data so that later analyses could connect discourse patterns back to content framing and media context.

## Output of This Stage

The output of the data collection stage is a structured comment-level dataset stored in `data/processed/`.

This dataset serves as the foundation for the rest of the project. The following stages rely on it for:

- text cleaning
- exploratory analysis
- lexical inspection
- topic modeling
- visualization and interpretation

