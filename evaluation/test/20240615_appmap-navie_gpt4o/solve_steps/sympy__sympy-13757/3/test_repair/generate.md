```xml
<change>
<file change-number-for-this-file="1">sympy/core/function.py</file>
<original line-count="6" no-ellipsis="true"><![CDATA[
if isinstance(v, (collections.Iterable, Tuple, MatrixCommon, NDimArray)):
]]></original>
<modified no-ellipsis="true"><![CDATA[
if isinstance(v, (collections.abc.Iterable, Tuple, MatrixCommon, NDimArray)):
]]></modified>
</change>
<change>
<file change-number-for-this-file="2">sympy/core/basic.py</file>
<original line-count="6" no-ellipsis="true"><![CDATA[
from collections import Mapping, defaultdict
]]></original>
<modified no-ellipsis="true"><![CDATA[
from collections.abc import Mapping
from collections import defaultdict
]]></modified>
</change>
<change>
<file change-number-for-this-file="3">sympy/core/containers.py</file>
<original line-count="6" no-ellipsis="true"><![CDATA[
class OrderedSet(collections.MutableSet):
]]></original>
<modified no-ellipsis="true"><![CDATA[
class OrderedSet(collections.abc.MutableSet):
]]></modified>
</change>
<change>
<file change-number-for-this-file="4">sympy/plotting/plot.py</file>
<original line-count="6" no-ellipsis="true"><![CDATA[
from collections import Callable
]]></original>
<modified no-ellipsis="true"><![CDATA[
from collections.abc import Callable
]]></modified>
</change>
```