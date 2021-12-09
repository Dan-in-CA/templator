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
page_render = template.render("<templates folder>", globals=template_globals, <base="page_base">)
```
Then, for example, in cherrypy:
```python
class My_project(object):

    @cherrypy.expose
    def my_page(self):  
        return str(page_render.my_page()) # be sure to return a string, my_page == template file.
```
See the web.py templator documentation for details on setting up a template file.

## You can read the documentation at:
https://webpy.readthedocs.io/en/latest/templating.html
