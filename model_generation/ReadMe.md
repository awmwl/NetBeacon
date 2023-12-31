#### models

trained model, includes models in different phases, per-packet model, long and short flow prediction model.

RandomForest model trained using scikit-learn(0.24.2) package in python
saved as dot file by

```
from sklearn.ensemble import RandomForestClassifier
from sklearn.tree import export_graphviz

rfc = RandomForestClassifier(...)
rfc.fit(...)
for i in range(len(rfc.estimators_)):
    export_graphviz(rfc.estimators_[i], out_file='rf_tree_{}.dot'.format(i),
                feature_names = xx,
                class_names = [xx,xx,...],
                rounded = True, proportion = False, 
                precision = 4, filled = True)
```

XGBoost model trained using xgboost(1.6.0) package in python
saved as txt file by
  
```
from xgboost import XGBClassifier
rfc = XGBClassifier(...)
rfc.fit(...)
rfc.get_booster().dump_model("xxx")
```

#### tree_to_table
transform model to flow table on the data plane

#### model_representation
transform models under the models folder into flow tables and put them under switch/control_plane
