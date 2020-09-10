## Django Request Processing
- Django looks for the `ROOT_URLCONF` setting to determine which root [[URLconf module]] to use
- Django loads the Python module and looks for a `urlpatterns`  variable, which should be a list of `django.urls.path()` and/or `django.urls.re_path()` instances
- Django runs through the list of patterns and stops at the first one that matches the requested URL
- Once the URL pattern matches Django imports and calls the related view, which is a Python function. The view gets passed the following arguments
	- an instance of [`HttpRequest](https://docs.djangoproject.com/en/2.0/ref/request-response/#django.http.HttpRequest)`