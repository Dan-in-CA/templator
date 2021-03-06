# Templator
Simple, elegant Python based web templating (part of web.py).
If you are familiar with Python, there is no new syntax to learn.  
This is a stand-alone version of templator.

## Usage
Clone the templaltor package into your project and add: 
```python
from templator import template
```
Then add e.g.:
```python
template_globals = {  
    "str": str,  
    "json": json,  
    "time": time,  
    "my_function": my_function, #  you can pass your own functions to templator.  
}
```
Then add e.g.:
```python
page_render = template.render("<templates folder>", globals=template_globals, [base="page_base"])
```
Then, for example, in cherrypy:
```python
class My_project(object):
    """
    Base class for project pages
    """

    @cherrypy.expose
    def my_page(self, [param-1]): 
        [param-2 = "some text"]
        [param-3 = some_value]
        return str(page_render.my_page([param-1, param-2, param-3, other_var, etc])   
        # my_page == template file.
        # be sure to return a string. 
```
See the web.py templator documentation for details on setting up a template file.

## You can read the documentation at:
https://webpy.readthedocs.io/en/latest/templating.html
