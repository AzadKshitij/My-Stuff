---
date: 22/05/2022
tag: #speedlabs #callback
---

# Call-backs
```python
id = {
	  "type": "Class_Buttons",
	  "index": 1
}
```

### Get values of triggered inputs.
```python
values = list(dash.callback_context.triggered_prop_ids.values())

print("---------------------------------------------------------")

print("dash.callback_context.triggered_prop_ids: ", values)
print(dash._utils.AttributeDict)
if len(values) > 0 and type(values[0]) == dash._utils.AttributeDict:
	print("is a dict")
print("dash.callback_context.triggered_prop_ids: ", type(values[0]))

print("---------------------------------------------------------")
```
