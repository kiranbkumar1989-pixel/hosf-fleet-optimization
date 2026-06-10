# HOSF Fleet Electrification Dataset

**Paper:** Development of a Hybrid Optimization-Simulation Framework for 
Prioritizing ICE-to-Electric Vehicle (EV) Fleet Replacement Decisions

**Authors:** Kiran Kumar Barnana, Adithya Umakanth Dandibuotla, Geetha Rajan

**DOI (preprint):** 10.5281/zenodo.20471685

---

## Dataset Files

### 1. D1_municipal_fleet_50vehicles.csv
- 50-vehicle municipal fleet (primary validation dataset)
- Columns: vehicle_id, vehicle_type, fuel_type, age_years,
  annual_operating_cost_usd, annual_co2_emissions_mt,
  annual_utilization_miles, replacement_capex_ev_usd,
  annual_cost_post_ev_usd, ev_annual_co2_mt, salvage_value_usd,
  criticality_score, reliability_index, mission_critical_flag,
  replacement_priority_index, tco_ice_10yr_usd, tco_ev_10yr_usd
- Key vehicle: MM_039 (RPI=29.41, Age=12.9yr, Cost=$77,880/yr)

### 2. D2_corporate_logistics_120vehicles.csv
- 120-vehicle corporate logistics fleet
- Same columns as D1
- Vehicle types: Van, Light-Truck, Heavy-Truck

### 3. D3_public_transit_200vehicles.csv
- 200-vehicle public transit fleet
- Same columns as D1
- Vehicle types: Standard-Bus, Articulated-Bus, Minibus

### 4. constraints_config.json
- Optimization constraint configurations for all three datasets
- Includes: budget, CO2 targets, service continuity thresholds,
  objective weights, Monte Carlo parameters

### 5. D1_monte_carlo_results.csv
- Monte Carlo simulation results for D1 (1,000 scenarios)
- Columns: vehicle_id, selection_frequency_pct,
  coefficient_of_variation, decision_robustness_index,
  robustness_tier, recommended_action,
  mean_cost_saving_usd, mean_co2_reduction_mt

### 6. optimization_results_all_datasets.csv
- MILP optimization results across all three datasets
- Includes: vehicles replaced, capital investment, savings,
  payback, CO2 reduction, solver performance metrics

### 7. mc_iteration_sensitivity.csv
- Monte Carlo iteration sensitivity study
- Shows accuracy vs computation time trade-off
- Justifies N=1,000 as recommended default

---

## Key Results (D1 Municipal Fleet)

| Metric | Value |
|--------|-------|
| Vehicles replaced | 8 (Phase 2) / 11 (Phase 2B) |
| Capital investment | $259,084 / $389,423 |
| Annual savings | $397,447 / $348,192 |
| Payback period | 40.9 / 13.4 months |
| CO2 reduction | 486.32 / 612.8 MT/year |
| Decision confidence | 97.3% |
| MILP solve time | 1.24 seconds |
| MIP gap | 0% (proven optimal) |

---

## Usage

These datasets are intended for:
1. Reproducing the results in the paper
2. Benchmarking alternative optimization methods
3. Extending HOSF to other fleet types

---

## License
CC BY 4.0 - Free to use with attribution

## Citation
Barnana, K.K., Dandibuotla, A.U., Rajan, G. (2026). 
Development of a Hybrid Optimization-Simulation Framework 
for Prioritizing ICE-to-EV Fleet Replacement Decisions.
DOI: 10.5281/zenodo.20471685
