<change>
<file change-number-for-this-file="1">sphinx/cmd/quickstart.py</file>
<original line-count="9" no-ellipsis="true"><![CDATA[
        for variable in d.get('variables', []):
            try:
                name, value = variable.split('=')
                d[name] = value
            except ValueError:
                print(__('Invalid template variable: %s') % variable)

        generate(d, overwrite=False, templatedir=args.templatedir)
        return 0


        )     
]]></original>
<modified no-ellipsis="true"><![CDATA[
        for variable in d.get('variables', []):
            try:
                name, value = variable.split('=')
                d[name] = value
            except ValueError:
                print(__('Invalid template variable: %s') % variable)

        generate(d, overwrite=False, templatedir=args.templatedir)
        return 0
]]></modified>
</change>