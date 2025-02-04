## Using the Django Template Language (DTL) (11:00)  
- use `{{ variable|safe }}` to avoid automatic escaping of data  


## Django Template Inheritance (6:06)  
- Inheritance is using code we have already written without writing it all over again (Do Not Repeat Yourself)  
- `{% extends "appname/base.html %}  `

## Reversing Django URLs (12:52)  
- `path('second', views.SecondView.as_view(), name='second-view')` - the name parameter is used to look up this specific path, we are not using the first value, because it may change
- example: `<a href="{% url 'appname:viewname' %}">`
- example of hardcoding: `<a href="/appname/viewname">`
- with parameter (like pk): ` {% url 'gview:cat' 42 %} `
- In the project's urls.py:
    - `path('route/', include('route.urls', namespace = 'CustomizedAppName'))`
    - `{% url 'CustomizedAppName:second-view' %}` instead of `{% url 'route:second-view' %}`
- use `reverse_lazy('appname:viewname)` to do this in views.py, the value can be assigned to a variable and passed to the template as context
    - `reverse('gview:dog', args=['42'])` to pass an argument