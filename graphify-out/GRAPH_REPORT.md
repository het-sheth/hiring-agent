# Graph Report - .  (2026-06-22)

## Corpus Check
- Corpus is ~14,604 words - fits in a single context window. You may not need a graph.

## Summary
- 214 nodes · 363 edges · 14 communities detected
- Extraction: 83% EXTRACTED · 17% INFERRED · 0% AMBIGUOUS · INFERRED: 63 edges (avg confidence: 0.52)
- Token cost: 2,800 input · 1,950 output

## God Nodes (most connected - your core abstractions)
1. `PDFHandler` - 33 edges
2. `Initialize the appropriate LLM provider based on the model.` - 15 edges
3. `JSONResume` - 13 edges
4. `ResumeEvaluator` - 11 edges
5. `TemplateManager` - 10 edges
6. `transform_parsed_data()` - 8 edges
7. `ModelProvider` - 7 edges
8. `EvaluationData` - 7 edges
9. `OllamaProvider` - 7 edges
10. `GeminiProvider` - 7 edges

## Surprising Connections (you probably didn't know these)
- `Parse date range and return both start and end dates.     For format like "Jan-M` --uses--> `JSONResume`  [INFERRED]
  transform.py → models.py
- `Helper function to extract profile information for a given network.` --uses--> `JSONResume`  [INFERRED]
  transform.py → models.py
- `Transform the three inputs (resume_data, github_data, evaluation) into the most` --uses--> `JSONResume`  [INFERRED]
  transform.py → models.py
- `Prompts for Resume Evaluation System  This module contains all the prompts used` --uses--> `ModelProvider`  [INFERRED]
  prompt.py → models.py
- `PDFHandler` --uses--> `Basics`  [INFERRED]
  pdf.py → models.py

## Hyperedges (group relationships)
- **PDF to JSONResume Extraction Pipeline** — readme_pymupdf_rag_py, readme_pdf_py, readme_jinja_templates, readme_json_resume [EXTRACTED 0.95]
- **LLM Provider Abstraction Layer** — readme_models_py, readme_ollama_provider, readme_gemini_provider, readme_llm_utils_py [EXTRACTED 0.92]
- **End-to-End Resume Scoring Orchestration** — readme_score_py, readme_github_py, readme_evaluator_py, readme_development_mode [EXTRACTED 0.90]

## Communities

### Community 0 - "Pydantic Data Models (JSONResume)"
Cohesion: 0.07
Nodes (48): BaseModel, Award, AwardsSection, Basics, BasicsSection, BonusPoints, CategoryScore, Certificate (+40 more)

### Community 1 - "Architecture & Dependencies Overview"
Cohesion: 0.09
Nodes (26): Provider-Agnostic Prompts Principle, config.py, Development Mode (Caching & CSV Export), evaluator.py, Fairness-Constrained Evaluation, GeminiProvider, GitHub Enrichment, github.py (+18 more)

### Community 2 - "LLM Provider Layer"
Cohesion: 0.13
Nodes (15): Enum, extract_json_from_response(), initialize_llm_provider(), Utility functions for LLM providers., Extract JSON content from markdown code blocks.      Args:         response_text, Initialize the appropriate LLM provider based on the model name.      Args:, GeminiProvider, ModelProvider (+7 more)

### Community 3 - "Resume/GitHub Data Transformation"
Cohesion: 0.15
Nodes (19): extract_domain_from_url(), extract_username_from_url(), fetch_profile(), get_network_name(), parse_date_range(), Parse date range and return both start and end dates.     For format like "Jan-M, Helper function to extract profile information for a given network., Transform the three inputs (resume_data, github_data, evaluation) into the most (+11 more)

### Community 4 - "PDF-to-Markdown Extraction (PyMuPDF)"
Cohesion: 0.1
Nodes (16): IdentifyHeaders, is_significant(), Parameters, This script accepts a PDF document filename and converts it to a text file in Ma, Return appropriate markdown header prefix.          Given a text span from a "di, Compute data for identifying header text.      This is an alternative to Identif, Read and store the TOC of the document., Return appropriate markdown header prefix.          Given a text span from a "di (+8 more)

### Community 5 - "Resume Evaluation Orchestration"
Cohesion: 0.22
Nodes (13): Initialize the appropriate LLM provider based on the model., ResumeEvaluator, EvaluationData, JSONResume, Complete JSON Resume format model., _evaluate_resume(), find_profile(), is_valid_resume_data() (+5 more)

### Community 6 - "PDF Section Extraction Handler"
Cohesion: 0.23
Nodes (1): PDFHandler

### Community 7 - "GitHub API Client & Config"
Cohesion: 0.29
Nodes (12): Configuration settings for the hiring agent application., _create_cache_filename(), extract_github_username(), fetch_all_github_repos(), fetch_and_display_github_info(), fetch_contributions_count(), _fetch_github_api(), fetch_github_profile() (+4 more)

### Community 8 - "Jinja Template Manager"
Cohesion: 0.2
Nodes (7): Template Manager for Section Extraction  This module provides functionality to l, Manages Jinja templates for section-specific resume extraction.      This class, Initialize the template manager.          Args:             template_dir (str):, Load all available templates., Get list of available section names.          Returns:             list: List of, Render a template for a specific section.          Args:             section_nam, TemplateManager

### Community 9 - "LLM Provider Protocol"
Cohesion: 0.4
Nodes (4): LLMProvider, Protocol for LLM providers., Send a chat request to the LLM provider., Protocol

### Community 10 - "Project Overview & Pipeline"
Cohesion: 0.67
Nodes (3): Smoke Tests (per pipeline stage), Hiring Agent, Resume-to-Score Pipeline

### Community 11 - "Black Formatting Standard"
Cohesion: 1.0
Nodes (2): Black Formatting Requirement, Black Code Formatter

### Community 12 - "Prompt Templates Directory"
Cohesion: 1.0
Nodes (1): prompts/ Templates Directory

### Community 13 - "Conventional Commits"
Cohesion: 1.0
Nodes (1): Conventional Commit Messages

## Knowledge Gaps
- **64 isolated node(s):** `Configuration settings for the hiring agent application.`, `Enum for supported model providers.`, `Protocol for LLM providers.`, `Send a chat request to the LLM provider.`, `Location information for JSON Resume format.` (+59 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **Thin community `Black Formatting Standard`** (2 nodes): `Black Formatting Requirement`, `Black Code Formatter`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Prompt Templates Directory`** (1 nodes): `prompts/ Templates Directory`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Conventional Commits`** (1 nodes): `Conventional Commit Messages`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `PDFHandler` connect `PDF Section Extraction Handler` to `Pydantic Data Models (JSONResume)`, `Jinja Template Manager`, `LLM Provider Layer`, `Resume Evaluation Orchestration`?**
  _High betweenness centrality (0.194) - this node is a cross-community bridge._
- **Why does `TemplateManager` connect `Jinja Template Manager` to `Pydantic Data Models (JSONResume)`, `Resume Evaluation Orchestration`, `PDF Section Extraction Handler`?**
  _High betweenness centrality (0.088) - this node is a cross-community bridge._
- **Why does `JSONResume` connect `Resume Evaluation Orchestration` to `Pydantic Data Models (JSONResume)`, `Resume/GitHub Data Transformation`, `PDF Section Extraction Handler`?**
  _High betweenness centrality (0.054) - this node is a cross-community bridge._
- **Are the 17 inferred relationships involving `PDFHandler` (e.g. with `JSONResume` and `Basics`) actually correct?**
  _`PDFHandler` has 17 INFERRED edges - model-reasoned connections that need verification._
- **Are the 14 inferred relationships involving `Initialize the appropriate LLM provider based on the model.` (e.g. with `JSONResume` and `Basics`) actually correct?**
  _`Initialize the appropriate LLM provider based on the model.` has 14 INFERRED edges - model-reasoned connections that need verification._
- **Are the 10 inferred relationships involving `JSONResume` (e.g. with `PDFHandler` and `Initialize the appropriate LLM provider based on the model.`) actually correct?**
  _`JSONResume` has 10 INFERRED edges - model-reasoned connections that need verification._
- **Are the 6 inferred relationships involving `ResumeEvaluator` (e.g. with `JSONResume` and `EvaluationData`) actually correct?**
  _`ResumeEvaluator` has 6 INFERRED edges - model-reasoned connections that need verification._