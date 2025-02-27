## CSRF Support in Django
- @csrf_exempt to stop csrf checking (bad idea)  
- use {% csrf_token %} in the form section in your template to automatically handle csrf
- to handle what happens in get and post requests in a view, create get and post methods in the class which take the request as a parameter
- if csrf validation fails, it halts execution before the post occurs
- in the get method, we simply handle rendering the html data with the proper contexts
- in thre post method, we handle what happens when there is an input in that view and where the user should be redirected afterward
## The post referesh pattern
- Refreshing after a post will do the post again, which should not happen
- We handle this with POST-REDIRECT-GET-REFRESH
## Implementing POST redirect in Django
- Return redirects after posts, not html, causing the start of a get
- Pass data to the GET - "flash message pattern"
- Session can be used to store flash messages