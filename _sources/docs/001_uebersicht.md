---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3.9
  language: python
  name: python3
---

# Übersicht über die Unterrichtsinhalte

```{code-cell} ipython3
:tags: ["remove-input"]
# Set CSS properties for th elements in dataframe
th_props = [
  ('font-size', '11px'),
  ('text-align', 'center'),
  ('font-weight', 'bold'),
  ('color', '#6d6d6d'),
  ('background-color', '#f7f7f9')
  ]


# Set CSS properties for td elements in dataframe
td_props = [
  ('font-size', '11px')
  ]

# Set table styles
styles = [
  dict(selector="th", props=th_props),
  dict(selector="td", props=td_props)
  ]

import pandas as px
bio_g9_05 = px.read_excel("bio_g9_05.xlsx", dtype=object, sheet_name='bio_g9_05')
(bio_g9_05.style
    .applymap(color_negative_red, subset=['total_amt_usd_diff','total_amt_usd_pct_diff'])
    .format({'total_amt_usd_pct_diff': "{:.2%}"})
    .set_table_styles(styles))
bio_g9_05.head()
```
