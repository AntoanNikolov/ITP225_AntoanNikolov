## Owned Rows in Django - Overview
- Only the owner of a row should be able to change it
- We have an ownerview which will inherit from the generic view but modify the logic to query the current user
## Owned Rows in Django - Generic Views Review
- get_queryset to change what is listed in a list view
- get_context_data to add more context to a template
## Owned Rows in Django - owner.py
- add owner column to our models
- in views.py we import OwnerListView (created in owner.py and inherit from generic), etc. Then, in each view class we inherit them
- in owner.py we overide the get_queryset. We grab the default queryset. After, we add an "AND" clause saying that apart from the primary key matching and that stuff, the owner column must also match whoever the current user is.
- we make a form_valid function to ensure the owner is automatically assigned to whatever they are creating