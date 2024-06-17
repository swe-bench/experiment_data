<change>
<file change-number-for-this-file="1">sklearn/utils/estimator_checks.py</file>
<original line-count="14" no-ellipsis="true"><![CDATA[
from sklearn.externals.six.moves import zip
from sklearn.externals.joblib import hash, Memory
from sklearn.utils.testing import assert_raises, _get_args
from sklearn.utils.testing import assert_raises_regex
from sklearn.utils.testing import assert_raise_message
from sklearn.utils.testing import assert_equal
from sklearn.utils.testing import assert_not_equal
from sklearn.utils.testing import assert_almost_equal
from sklearn.utils.testing import assert_true
from sklearn.utils.testing import assert_false
from sklearn.utils.testing import assert_in
from sklearn.utils.testing import assert_array_equal
from sklearn.utils.testing import assert_allclose
from sklearn.utils.testing import assert_allclose_dense_sparse
from sklearn.utils.testing import assert_warns_message
from sklearn.utils.testing import META_ESTIMATORS
]]></original>
<modified no-ellipsis="true"><![CDATA[
from six.moves import zip
from joblib import hash, Memory
from sklearn.utils._testing import assert_raises, _get_args
from sklearn.utils._testing import assert_raises_regex
from sklearn.utils._testing import assert_raise_message
from sklearn.utils._testing import assert_equal
from sklearn.utils._testing import assert_not_equal
from sklearn.utils._testing import assert_almost_equal
from sklearn.utils._testing import assert_true
from sklearn.utils._testing import assert_false
from sklearn.utils._testing import assert_in
from sklearn.utils._testing import assert_array_equal
from sklearn.utils._testing import assert_allclose
from sklearn.utils._testing import assert_allclose_dense_sparse
from sklearn.utils._testing import assert_warns_message
from sklearn.utils._testing import META_ESTIMATORS
]]></modified>
</change>

<change>
<file change-number-for-this-file="2">sklearn/base.py</file>
<original line-count="8" no-ellipsis="true"><![CDATA[
from .externals import six
from .utils.fixes import signature
from . import __version__

def is_classifier(estimator):
    """Returns True if the given estimator is (probably) a classifier.

    Parameters
    ----------
    estimator : object
]]></original>
<modified no-ellipsis="true"><![CDATA[
import six
from sklearn.utils.fixes import signature
from . import __version__

def is_classifier(estimator):
    """Returns True if the given estimator is (probably) a classifier.

    Parameters
    ----------
    estimator : object
]]></modified>
</change>