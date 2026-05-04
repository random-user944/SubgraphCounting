# Hypergraph Enumeration with Filters

This repository contains Python notebooks for enumerating hypergraphs and filtering them using structural constraints.

## Overview
Each script generates candidate hypergraphs and applies a sequence of validation steps to keep only those satisfying irreducibility and filtering conditions. The goal is to identify patterns that are **not eliminated** by the filters.

## Validation Steps
For each generated hypergraph:
- Ensure every vertex has sufficient degree  
- Remove cases where one hyperedge is a subset of another  
- Remove cases where one vertex’s incident edge set is contained in another’s  

## Filters
The following filters are applied:
- **Lemma 3.1 Single-Uncovered-Vertex Filter** (`main_filter`)  
- **Lemma 3.2 Double-Uncovered-Vertex Filter** (`two_vertex_filter`)  
- **Case 2 of Lemma 3.3** (`validate_no_full_union`)  

These filters eliminate configurations that can be handled by the lemma.

## Isomorphism Handling
Hypergraphs are converted into a canonical form so that structurally identical cases (under vertex relabeling) are counted only once.

## Output
The scripts:
- Iterate through all candidates  
- Print any valid (unfiltered) patterns  
- Report the total number of unique surviving hypergraphs  

## Purpose
Any patterns that survive all filters correspond to cases requiring separate (ad-hoc) handling.
