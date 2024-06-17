<change>
<file change-number-for-this-file="1">django/contrib/admin/checks.py</file>
<original line-count="10" no-ellipsis="true"><![CDATA[
from django.core.exceptions import FieldDoesNotExist

# Registering the custom uniqueness check
checks.register('models')(check_constraint_and_index_names_uniqueness)
from django.db import models
]]></original>
<modified no-ellipsis="true"><![CDATA[
from django.core.exceptions import FieldDoesNotExist
from django.contrib.admin.utils import check_constraint_and_index_names_uniqueness

# Registering the custom uniqueness check
checks.register('models')(check_constraint_and_index_names_uniqueness)
from django.db import models
]]></modified>
</change>