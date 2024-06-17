```xml
<change>
<file change-number-for-this-file="1">django/db/models/deletion.py</file>
<original line-count="13" no-ellipsis="true"><![CDATA[
if protected_objects:
    raise ProtectedError(
        'Cannot delete some instances of model %r because they are '
        'referenced through protected foreign keys: %s.' % (
            model.__name__,
            ', '.join(protected_objects),
        ),
        chain.from_iterable(protected_objects.values()),
    )
]]></original>
<modified no-ellipsis="true"><![CDATA[
if protected_objects:
    raise ProtectedError(
        'Cannot delete some instances of model %r because they are '
        'referenced through protected foreign keys: %s.' % (
            model.__name__,
            ', '.join(sorted(protected_objects)),
        ),
        chain.from_iterable(protected_objects.values()),
    )
]]></modified>
</change>
```