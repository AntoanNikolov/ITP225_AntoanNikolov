## Generic Views  
- Concept uses inheritance  
- class ExampleView(generic.ListView) inherits its logic from the ListView class in the generic module
    - you must only tell the class which model you wish to use, using model="modelname"
    - the template and the variables inside it will use generic names such as "model_list"