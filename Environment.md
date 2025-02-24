# Key Parameter Formulas

Below are the key formulas integrating variables from the Agents and Actions files.

---

## 1. Production

Production is determined by the resources allocated to production and enhanced by technology level:

$$
\text{Production}_i = \Lambda_i \times T_i \times (M - a_i-TI_i)
$$

- $ \Lambda_i $: Production efficiency of country $i$.
- $ T_i $: Technology level of country $i$.
- $ M $: Total resource endowment available per period.
- $ a_i $: Abatement spending decision.
- $ TI_i $: Technology Investment.

---

## 2. Emissions

Emissions arise from production according to carbon intensity, offset by the benefits of abatement spending, modulated by technology level:

$$
\text{Emissions}_i = CI_i \times \Lambda_i \times T_i \times (M - a_i-TI_i)- \Gamma_i \times T_i \times a_i
$$

- $ CI_i $: Carbon intensity of economic activity.
- $ \Gamma_i $: Abatement efficiency of country $i$.

---

## 3. Global Emissions

Global emissions are the sum of individual country emissions:

$$
\text{Global Emissions} = \sum_{i} \text{Emissions}_i
$$

---

## 4. Climate Damage

Assuming a quadratic damage function, global climate damage is modeled as:

$$
\text{Global Climate Damage} = \kappa \times \left( \text{Global Emissions} \right)^2
$$

- $ \kappa $: Scaling parameter converting emissions into economic damage.

---

## 5. Damage Allocation

Each country bears a fraction of the global damage based on its damage share:

$$
\text{Damage}_i = \Theta_i \times \text{Global Climate Damage}
$$

- $ \Theta_i $: The fraction of global damage allocated to country $i$.

---

## 6. Trade Benefits

Trade benefits are derived from the country’s trade balance:

$$
\text{Trade Benefits}_i = \tau \times BT_i
$$

- $ BT_i $: Trade balance of country $i$.
- $ \tau $: Conversion factor translating the trade balance into economic gains.

---

## 7. Net Payoff (Net GDP)

The net economic payoff (or Net GDP) for each country combines production and trade benefits—adjusted by social acceptance—and subtracts the allocated climate damage:

$$
\text{Net GDP}_i = S_i \times \left[ \Lambda_i \times T_i \times (M - a_i-TI_i) + \tau \times BT_i \right] - \Theta_i \times \kappa \times \left( \sum_{i} \text{Emissions}_i \right)^2
$$

- $ S_i $: Social acceptance of country $i$, influencing overall economic performance.
- A low $ S_i $ may trigger adverse outcomes, such as a country exiting the model.

---

## 8. Dynamic State Updates

### Technology Level Update

$$
T_i(t+1) = T_i(t) + \delta \times TI_i
$$

- $ \delta $: Rate of technological progress.
- $ TI_i $: Investment in technology R&D by country $i$.

### Social Acceptance Update

$$
S_i(t+1) = S_i(t) + \alpha \times \left(\frac{\text{Production}_i}{\text{Production}_i^{\text{ref}}} - 1\right) - \beta \times \left(\frac{\text{Damage}_i}{\text{Damage}_i^{\text{ref}}} - 1\right)
$$

- $ \alpha $ and $ \beta $: Coefficients determining the influence of production and damage on social acceptance.
- $ \text{Production}_i^{\text{ref}} $ and $ \text{Damage}_i^{\text{ref}} $: Reference levels for production and damage.
  

