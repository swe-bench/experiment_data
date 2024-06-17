<change>
<file change-number-for-this-file="1">src/_pytest/logging.py</file>
<original line-count="11" no-ellipsis="true"><![CDATA[
DEFAULT_LOG_FORMAT = "%(filename)-25s %(lineno)4d %(levelname)-8s %(message)s"
DEFAULT_LOG_DATE_FORMAT = "%H:%M:%S"
]]></original>
<modified no-ellipsis="true"><![CDATA[
DEFAULT_LOG_FORMAT = "%(levelname)-8s %(name)s:%(filename)s:%(lineno)d %(message)s"
DEFAULT_LOG_DATE_FORMAT = "%H:%M:%S"
]]></modified>
</change>