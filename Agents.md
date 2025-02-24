# Defining Agents

## Country Types

- **Developed Industrial Country**
  High baseline GDP, strict environmental regulations, and ambitious climate targets; medium climate damage share.
- **Emerging Economy (EE)**
  Moderate baseline GDP with high growth, relatively relaxed environmental regulations, balancing economic development with climate goals; higher climate damage share.
- **Resource-Dependent Country**
  Reliance on oil and gas, lenient environmental regulations, and vulnerability to external sanctions; variable climate damage.
- **Small Island or Climate-Vulnerable Country**
  Low GDP and limited resources, highly exposed to climate impacts (e.g., sea level rise, extreme weather); high climate damage share.

---

### Additional Parameters

- **Resource Endowment $M_i$:**
  The total resources available for the current period (per year). This pool can be split between production and abatement.
- **Production Efficiency $\Lambda_i$:**
  The economic output generated per unit of resource allocated to production.
- **Baseline Emissions $E_i$:**
  The emissions a country produces when no resources are invested in abatement, reflecting its current industrial base and energy usage.
- **Abatement Efficiency $\Gamma_i$:**
  The effectiveness with which investment in abatement reduces emissions.
- **Damage Share $\Theta_i$:**
  The fraction of global climate damage that country \(i\) bears.
- **Carbon Intensity $CI_i$:**
  The amount of carbon emissions produced per unit of economic output.
- **Trade Balance $BT_i$:**
  Reflects the state of a country's international trade, capturing net exports (i.e., export share minus import share).

---

## Additional Dynamic State Variables

### 1. Technology Level $T_i$

- Represents a country’s capability in production and abatement technology.
- Affects effective production and abatement efficiencies, for example:
  
  - Effective production efficiency: $\Lambda_i^{\text{eff}} = \Lambda_i \times T_i$
  - Effective abatement efficiency: $\Gamma_i^{\text{eff}} = \Gamma_i \times T_i$
- The technology level can be updated using a simple linear rule:
  
  $$
  T_i(t+1) = T_i(t) + \delta \times \text{TechInvestment}_i
  $$
  
  where $\delta$ is the rate of technological progress and $TechInvestment_i$ is the investment in technology R&D.

### 2. Social Acceptance $S_i$

- Reflects public support for a country’s economic and environmental policies.
- Social acceptance influences both production and environmental outcomes: low production or poor environmental quality reduces \(S_i\).
- If \(S_i\) falls below a critical threshold, the country may “exit” (i.e., face internal collapse) from the model.
- A simple update formula can be:
  
  $$
  S_i(t+1) = S_i(t) + \alpha \times \left(\frac{\text{Production}_i}{\text{Production}_i^{\text{ref}}} - 1\right) - \beta \times \left(\frac{\text{Damage}_i}{\text{Damage}_i^{\text{ref}}} - 1\right)
  $$
  
  where $\alpha$ and $\beta$ are positive coefficients, and $Production_i^{\text{ref}}$ and  $Damage_i^{\text{ref}}$ are reference levels for production and damage respectively.

---

## Random Deviations for Agent Heterogeneity

- To capture within-group differences, each country’s base parameters (e.g., $\Lambda_i$, $\Gamma_i$ will include a small random deviation (e.g., ±5% to 10%).

