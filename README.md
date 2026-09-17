# Local Sequence Alignment of DNA and Protein Sequences Using Smith-Waterman Algorithm

## About the Project

This project is a **Java-based bioinformatics application** designed to compare DNA and protein sequences and identify the most similar local regions between them.

Sequence comparison is useful in bioinformatics for studying genes, proteins, conserved regions, and mutations. When two biological sequences contain insertions, deletions, or mutations, simply comparing them character by character may not provide a meaningful result. This project addresses this problem by using the **Smith-Waterman local alignment algorithm**, which finds the best matching region instead of forcing the entire sequences to align.

The project also includes a **Suffix Array with Kasai's LCP algorithm** as a preliminary exact-matching stage. This stage quickly identifies the longest exact common substring between the input sequences. The result can then be considered as a conserved-region candidate before performing the more flexible Smith-Waterman alignment.

Therefore, the project follows a two-stage pipeline:

**Exact Matching → Local Scored Alignment**

This combination demonstrates the use of both **string algorithms and dynamic programming** for solving a practical bioinformatics problem.

---

## Problem Statement

Traditional sequence comparison methods may have difficulty identifying highly similar regions when two larger sequences contain mutations, insertions, or deletions.

For example, two sequences may have a small region that is highly similar even though the remaining parts of the sequences are different.

The objective of this project is to develop an application that:

- Accepts two DNA or protein sequences as input.
- Validates the input sequences.
- Finds exact common regions using Suffix Array and Kasai LCP.
- Finds the best local alignment using Smith-Waterman.
- Allows users to configure match, mismatch, and gap scores.
- Displays the aligned sequences and alignment statistics.
- Calculates alignment score and percentage similarity.
- Helps identify conserved regions and study sequence differences.

---

## Main Objective

The main objective is to implement sequence alignment algorithms **from first principles in Java** without depending on external sequence-alignment libraries.

The application demonstrates how algorithms and data structures can be applied to a real-world computational biology problem.

---

## How the Project Works

The project is divided into two major stages.

### Stage 1: Exact Matching — Suffix Array + Kasai LCP

The first stage searches for an exact common region between the two sequences.

The input sequences are combined using a separator:

```text
Sequence A + Separator + Sequence B
