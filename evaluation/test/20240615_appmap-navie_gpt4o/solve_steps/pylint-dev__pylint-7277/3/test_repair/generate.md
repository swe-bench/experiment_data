<change>
<file change-number-for-this-file="1">pylint/config/__init__.py</file>
<original line-count="14" no-ellipsis="true"><![CDATA[
def load_results(base: str) -> LinterStats | None:
    # TODO: 3.0: Remove deprecated function
    # pylint: disable=import-outside-toplevel
    from pylint.lint.caching import load_results as _real_load_results

    warnings.warn(
        "'pylint.config.load_results' is deprecated, please use "
        "'pylint.lint.load_results' instead. This will be removed in 3.0.",
        DeprecationWarning,
    )
    return _real_load_results(base, PYLINT_HOME)


def save_results(results: LinterStats, base: str) -> None:
    # TODO: 3.0: Remove deprecated function
    # pylint: disable=import-outside-toplevel
    from pylint.lint.caching import save_results as _real_save_results

    warnings.warn(
        "'pylint.config.save_results' is deprecated, please use "
        "'pylint.lint.save_results' instead. This will be removed in 3.0.",
        DeprecationWarning,
    )
    return _real_save_results(results, base, PYLINT_HOME)
]]></original>
<modified no-ellipsis="true"><![CDATA[
def load_results(base: str) -> LinterStats | None:
    # TODO: 3.0: Remove deprecated function
    # pylint: disable=import-outside-toplevel
    from pylint.lint.caching import load_results as _real_load_results

    warnings.warn(
        "'pylint.config.load_results' is deprecated, please use "
        "'pylint.lint.caching.load_results' instead. This will be removed in 3.0.",
        DeprecationWarning,
    )
    return _real_load_results(base, PYLINT_HOME)


def save_results(results: LinterStats, base: str) -> None:
    # TODO: 3.0: Remove deprecated function
    # pylint: disable=import-outside-toplevel
    from pylint.lint.caching import save_results as _real_save_results

    warnings.warn(
        "'pylint.config.save_results' is deprecated, please use "
        "'pylint.lint.caching.save_results' instead. This will be removed in 3.0.",
        DeprecationWarning,
    )
    return _real_save_results(results, base, PYLINT_HOME)
]]></modified>
</change>


