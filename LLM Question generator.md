
# New poll questions are generated automatically by a scheduled workflow that invokes a Large Language Model (LLM).


# Cadence: 

***every 15 minutes, aligned to the Europe/Amsterdam timezone***


# Context: 

***the LLM receives recent historical questions to avoid repetition and to keep questions relevant and varied.***


# Output: 

***a single, concise, neutral yes/no question on a public-sector theme, plus a short context line.***


# Discrimination filter: 

***every generated question is screened against patterns derived from Article 1 of the Dutch Constitution, which prohibits discrimination on the grounds of religion, belief, political opinion, race, sex, or on any grounds whatsoever. Questions that may discriminate are rejected before they ever reach the database.***


# Persistence: 

***valid questions are stored as Topic records with a sequential order, a government_level tag, and zero-initialized yes_count / no_count counters.***
