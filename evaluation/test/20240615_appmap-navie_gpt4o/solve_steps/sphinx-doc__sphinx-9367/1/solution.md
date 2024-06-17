<change>
<file change-number-for-this-file="1">sphinx/pycode/ast.py</file>
<original line-count="14" no-ellipsis="true"><![CDATA[
    def visit_Tuple(self, node: ast.Tuple) -> str:
        if node.elts:
            return "(" + ", ".join(self.visit(e) for e in node.elts) + ")"
        else:
            return "()"
]]></original>
<modified no-ellipsis="true"><![CDATA[
    def visit_Tuple(self, node: ast.Tuple) -> str:
        if node.elts:
            if len(node.elts) == 1:
                return "(" + self.visit(node.elts[0]) + ",)"
            else:
                return "(" + ", ".join(self.visit(e) for e in node.elts) + ")"
        else:
            return "()"
]]></modified>
</change>