<change>
<file change-number-for-this-file="1">sphinx/ext/autodoc/type_comment.py</file>
<original line-count="7" no-ellipsis="true"><![CDATA[
def setup(app: Sphinx) -> Dict[str, Any]:
    app.add_config_value('autodoc_type_aliases', {}, 'env')
    app.connect('autodoc-before-process-signature', update_annotations_using_type_comments)

    return {'version': sphinx.__display_version__, 'parallel_read_safe': True}
]]></original>
<modified no-ellipsis="true"><![CDATA[
def setup(app: Sphinx) -> Dict[str, Any]:
    if 'autodoc_type_aliases' not in app.config.values:
        app.add_config_value('autodoc_type_aliases', {}, 'env')
    app.connect('autodoc-before-process-signature', update_annotations_using_type_comments)

    return {'version': sphinx.__display_version__, 'parallel_read_safe': True}
]]></modified>
</change>