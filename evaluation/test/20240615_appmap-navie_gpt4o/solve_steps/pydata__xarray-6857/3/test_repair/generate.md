<change>
<file change-number-for-this-file="1">xarray/core/merge.py</file>
<original line-count="12" no-ellipsis="true"><![CDATA[
        result = {}
        dropped_keys = set()
        for attrs in variable_attrs:
            result.update(
                {
                    key: value
                    for key, value in attrs.items()
                    if key not in dropped_keys
                    and (key not in result or result[key] == value)
                    or dropped_keys.add(key)
                }
            )
]]></original>
<modified no-ellipsis="true"><![CDATA[
        result = {}
        dropped_keys = set()
        for attrs in variable_attrs:
            for key, value in attrs.items():
                if key not in dropped_keys:
                    if key not in result:
                        result[key] = value
                    elif result[key] != value:
                        dropped_keys.add(key)
                        result.pop(key)
]]></modified>
</change>