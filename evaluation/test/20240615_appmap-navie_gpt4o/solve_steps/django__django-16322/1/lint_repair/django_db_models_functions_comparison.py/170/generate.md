<change>
<file change-number-for-this-file="1">django/db/models/functions/comparison.py</file>
<original line-count="7" no-ellipsis="true"><![CDATA[
            # Handle potential nested subqueries
            sql, params = super().as_sql(compiler, connection, **extra_context)
            if "subquery" in sql:
                sql = f"SELECT * FROM ({sql}) AS subquery_wrapper"
            return sql, params
    
        def as_postgresql(self, compiler, connection, **extra_context):
        return self.as_sql(
            compiler,
            connection,
            function="JSONB_BUILD_OBJECT",
            **extra_context,
        )
]]></original>
<modified no-ellipsis="true"><![CDATA[
            # Handle potential nested subqueries
            sql, params = super().as_sql(compiler, connection, **extra_context)
            if "subquery" in sql:
                sql = f"SELECT * FROM ({sql}) AS subquery_wrapper"
            return sql, params

    def as_postgresql(self, compiler, connection, **extra_context):
        return self.as_sql(
            compiler,
            connection,
            function="JSONB_BUILD_OBJECT",
            **extra_context,
        )
]]></modified>
</change>