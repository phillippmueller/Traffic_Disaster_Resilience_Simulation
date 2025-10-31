### Project Summary

This project builds a single, end-to-end, data-driven workflow to assess the resilience of Bangladesh’s transport network and to inform policy on where to reinforce, maintain, or monitor roads and bridges. We begin by diagnosing and repairing critical inconsistencies in the national road and bridge datasets (RMMS/BMMS)—notably coordinate errors, chainage/LRP mismatches, and misaligned bridge locations—then regenerate the canonical road and bridge files used by the modelling stack ( _roads.tcv, BMMS_Overview.xlsx). This establishes a trustworthy data foundation for all downstream analysis.      

On that foundation, we implement a modular agent-based simulation in MESA that represents sources/sinks, links, and bridges with failure-/maintenance-driven delays parameterized by bridge quality (A–D). Scenario experiments inject trucks every five minutes over a five-day horizon to quantify corridor travel-time impacts under escalating bridge-outage percentages, producing reproducible CSV outputs.      

We then scale from a single corridor to a connected network: N1, N2, and >25 km N-side roads are auto-generated, and NetworkX provides shortest-path routing between two-way SourceSink nodes; discovered paths are cached to accelerate replications. The same experiment design measures network-wide travel times under progressive degradation.      

Finally, we integrate RMMS traffic (AADT) with bridge location/quality to operationalize criticality (economic importance via truck volumes) and vulnerability (likelihood/impact of becoming impassable), producing ranked road/bridge hotspots and Python visualizations for decision support; analyses can rely on AADT alone or be coupled to simulation for N1/N2.      

Deliverables: a cleaned, reusable dataset; a modular ABM; a network generator with routing; and a vulnerability-criticality analytics layer—together forming a replicable pipeline for infrastructure resilience planning.  
