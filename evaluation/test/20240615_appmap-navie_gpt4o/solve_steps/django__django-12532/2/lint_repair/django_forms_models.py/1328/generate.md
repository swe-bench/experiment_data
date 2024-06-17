<change>
<file change-number-for-this-file="1">django/forms/models.py</file>
<original line-count="14" no-ellipsis="true"><![CDATA[
            qs = self._check_values(value)
            # Since this overrides the inherited ModelChoiceField.clean
            # we run custom validators here
            self.run_validators(value)
            return qs
    
        def _check_values(self, value):
            """
            Given a list of possible PK values, return a QuerySet of the
            corresponding objects. Raise a ValidationError if a given value is
            invalid (not a valid PK, not in the queryset, etc.)
            """
            key = self.to_field_name or 'pk'
            # deduplicate given values to avoid creating many querysets or
]]></original>
<modified no-ellipsis="true"><![CDATA[
        qs = self._check_values(value)
        # Since this overrides the inherited ModelChoiceField.clean
        # we run custom validators here
        self.run_validators(value)
        return qs

    def _check_values(self, value):
        """
        Given a list of possible PK values, return a QuerySet of the
        corresponding objects. Raise a ValidationError if a given value is
        invalid (not a valid PK, not in the queryset, etc.)
        """
        key = self.to_field_name or 'pk'
        # deduplicate given values to avoid creating many querysets or
]]></modified>
</change>