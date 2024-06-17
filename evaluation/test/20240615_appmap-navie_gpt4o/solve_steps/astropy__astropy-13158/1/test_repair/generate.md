<change>
<file change-number-for-this-file="1">astropy/modeling/core.py</file>
<original line-count="14" no-ellipsis="true"><![CDATA[
param._unit = value.unit
param.value = value.value
else:
    if not isinstance(value, Quantity):
    raise UnitsError(f"The '{param.name}' parameter should be given as a"
                                  " Quantity because it was originally "
                                  "initialized as a Quantity")
param._unit = value.unit
param.value = value.value
]]></original>
<modified no-ellipsis="true"><![CDATA[
param._unit = value.unit
param.value = value.value
else:
    if not isinstance(value, Quantity):
        raise UnitsError(f"The '{param.name}' parameter should be given as a"
                         " Quantity because it was originally "
                         "initialized as a Quantity")
    param.value = value  # direct assignment without unit conversion
]]></modified>
</change>