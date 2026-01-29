# NJ Redistricting and Gerrymandering Project

This project implements algorithmic redistricting for New Jersey’s 12 congressional districts using precinct-level geographic, demographic, and electoral data.

Two maps are generated under real legal constraints:
1. **Fair Map** – designed to maximize representational fairness and competitiveness.
2. **Unfair Map** – intentionally introduces partisan advantage using gerrymandering techniques while still satisfying legal requirements.

Both maps satisfy:
- Contiguous districts  
- Balanced population (within the allowed deviation)

## Goals

- Demonstrate how algorithmic choices affect political representation
- Compare a fairness-oriented map against a strategically biased map
- Evaluate tradeoffs using standard redistricting metrics

## Data

The project uses:
- Precinct shapefiles for New Jersey
- Precinct demographic and election data
- Precomputed precinct contiguity information

Each precinct is assigned to one of 12 districts.

## Method Overview

The maps are built algorithmically rather than by manual drawing.

Typical steps include:
1. Selecting seed precincts for each district
2. Expanding districts using adjacency (contiguity) constraints
3. Controlling district population to remain balanced
4. Optimizing according to different objectives:
   - Fair map: compactness, competitiveness, balanced vote share
   - Unfair map: packing and cracking to favor a target party/community

The unfair map is constructed to be biased but not blatantly illegal, aiming to resemble plausible real-world gerrymanders.

## Files

- `NJ_Redistricting.ipynb`  
  Main notebook containing the redistricting algorithms and map generation code.

- `fair_map_GG.csv`  
  Precinct-to-district assignments for the fairness-oriented map.

- `unfair_map_GG.csv`  
  Precinct-to-district assignments for the gerrymandered map.

Each CSV has one row per precinct (6361 total) and can be directly uploaded to Dave’s Redistricting App (DRA) for visualization and metric computation.

## Evaluation

Maps are analyzed in DRA using metrics such as:
- Population deviation
- Compactness
- Partisan fairness measures (e.g., efficiency gap, seat share)
- Competitiveness of districts

The report compares:
- Fair vs. unfair maps
- Both maps vs. the current NJ congressional map

## How to Use

1. Open `NJ_Redistricting.ipynb` and run all cells to generate maps.
2. Export the produced CSV files.
3. Upload the CSVs to DRA to visualize districts and compute metrics.
4. Compare results and analyze fairness and bias.

## Key Takeaways

- Small algorithmic changes can significantly shift political outcomes.
- Fairness and partisan advantage are often competing objectives.
- Legal constraints alone do not prevent subtle gerrymandering.
- Transparent, data-driven methods are essential for evaluating maps.

This project highlights how computational techniques can both expose and create bias in electoral districting.

