---
title: Piecewise error metrics for CLV prediction
---
Customer lifetime value models often use metrics such as MAE, RAE, or MSE to measure predictive performance. However, one result of these models is predictions that never really output a churned, or $0, value. One might see a model that predicts a slew of $0.03 lifetime value scores for many customers where it's never fully confident in customer churn.

One potential idea is to use a piecewise metric that calculates a different loss formula based on the churn labels. This has been used in the field of computer vision, in the form of WHDR/WKDR.

> We report WKDR, the weighted disagreement rate between the predicted ordinal relations and ground-truth ordinal relations 3. We also report WKDR= (disagreement rate on pairs whose ground-truth relations are =) and WKDR= (disagreement rate on pairs whose ground-truth relations are < or >)
> [1]

For CLV, this could be a piecewise loss that penalizes an incorrect dead/alive prediction by using a different loss function for that situation.

This could be more efficient than including a separate churn module within a predictive system that is trained separately. Additionally, it might make it possible to include churn in the evaluation for models that don't have a specific churn module.

---
Sources:
[1]: https://arxiv.org/pdf/1604.03901.pdf
[2]: http://persci.mit.edu/pub_pdfs/learning-ordinal-relationships.pdf