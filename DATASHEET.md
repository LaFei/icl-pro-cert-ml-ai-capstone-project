Datasheet: BBO Capstone Query  Dataset


# Motivation

This dataset was created to record and audit my Black-Box Optimisation (BBO) capstone work. It supports:

Tracking weekly query inputs and returned outputs for 8 unknown functions

Comparing how different heuristics (centroid baseline, local tuning, direction changes) affected outcomes

# Composition

### What it contains

For each week and each function (1–8):

Input vector 

x in [0,1] ,submitted with 6 decimals

Scalar output y returned by the portal



### Dimensions

F1–F2: 2D

F3: 3D

F4–F5: 4D

F6: 5D

F7: 6D

F8: 8D

### Size

~10 rounds × 8 functions = ~80 evaluations

### Gaps / biases

Sampling is not uniform (later weeks focus on promising regions)

Large areas of the search space remain unexplored due to weekly query limits

# Collection process

### How queries were generated

Week 1 baseline: centroid-style “safe” query near mid-range values

Weeks 2–10: adaptive local search using:

Step-size tuning: smaller steps for stable, high-performing functions

Directional changes/reversals: when a function dropped

Plateau handling: conservative refinement when diminishing returns appeared

### Time frame

Collected weekly from Week 1 to Week 10 (continuing)


# Preprocessing & Uses

Preprocessing

Minimal: store portal outputs “as-is”

Standardisation:

Inputs kept in consistent order



Intended uses

Analyse exploration vs exploitation trends

Visualise plateaus, improvements, and instability per function

Support transparent reporting in coursework + GitHub documentation



# Distribution & Maintenance

### Where available

In this GitHub repo under /data and /notebooks

Terms of use

Note: the underlying black-box functions are available on the course portal; this dataset records my inputs and the corresponding outputs.



Key assumptions & limitations

Assumes local smoothness: small input changes often lead to predictable output changes.

Main limitation: sampling bias / path dependence due to limited queries and a focus on local refinement.
