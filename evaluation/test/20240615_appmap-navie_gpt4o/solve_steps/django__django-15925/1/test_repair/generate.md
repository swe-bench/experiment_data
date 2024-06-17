<change>
<file change-number-for-this-file="1">django/db/migrations/operations/fields.py</file>
<original line-count="14" no-ellipsis="true"><![CDATA[
        from_model = from_state.apps.get_model(app_label, self.model_name)
        if self.allow_migrate_model(schema_editor.connection.alias, from_model):
            field = from_model._meta.get_field(self.name)
            if schema_editor.connection.vendor == 'sqlite' and field.db_index:
                schema_editor.execute(f'DROP INDEX IF EXISTS {field.name}_idx')
            schema_editor.remove_field(from_model, field)
]]></original>
<modified no-ellipsis="true"><![CDATA[
        from_model = from_state.apps.get_model(app_label, self.model_name)
        if self.allow_migrate_model(schema_editor.connection.alias, from_model):
            field = from_model._meta.get_field(self.name)
            if schema_editor.connection.vendor == 'sqlite' and field.db_index:
                with schema_editor.connection.cursor() as cursor:
                    cursor.execute(f'DROP INDEX IF EXISTS {field.name}_idx')
            schema_editor.remove_field(from_model, field)
]]></modified>
</change>

<change>
<file change-number-for-this-file="2">django/db/migrations/operations/fields.py</file>
<original line-count="14" no-ellipsis="true"><![CDATA[
        cursor.execute(f'DROP INDEX IF EXISTS {field.name}_idx')
]]></original>
<modified no-ellipsis="true"><![CDATA[
        with connection.cursor() as cursor:
            cursor.execute(f'DROP INDEX IF EXISTS {field.name}_idx')
]]></modified>
</change>

<change>
<file change-number-for-this-file="1">django/core/management/commands/migrate.py</file>
<original line-count="14" no-ellipsis="true"><![CDATA[
                        cursor.execute(f'DROP INDEX IF EXISTS {field.name}_idx')
]]></original>
<modified no-ellipsis="true"><![CDATA[
                        with connection.cursor() as cursor:
                            cursor.execute(f'DROP INDEX IF EXISTS {field.name}_idx')
]]></modified>
</change>