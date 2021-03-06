# Django docopt command

[![Build Status](https://travis-ci.org/mbraak/django-docopt-command.svg?branch=master)](https://travis-ci.org/mbraak/django-docopt-command) [![Version](https://pypip.in/version/django-docopt-command/badge.svg)](https://pypi.python.org/pypi/django-docopt-command/) [![Development Status](https://pypip.in/status/django-docopt-command/badge.svg)](https://pypi.python.org/pypi/django-docopt-command/)

[![Coverage Status](https://img.shields.io/coveralls/mbraak/django-docopt-command.svg)](https://coveralls.io/r/mbraak/django-docopt-command) [![Downloads](https://pypip.in/download/django-docopt-command/badge.svg)](https://pypi.python.org/pypi/django-docopt-command/) [![Format](https://pypip.in/format/django-docopt-command/badge.svg)](https://pypi.python.org/pypi/django-docopt-command/) [![Requirements Status](https://requires.io/github/mbraak/django-docopt-command/requirements.png?branch=master)](https://requires.io/github/mbraak/django-docopt-command/requirements/?branch=master)

[![License](https://pypip.in/license/django-docopt-command/badge.svg)](https://pypi.python.org/pypi/django-docopt-command/) [![Supported Python versions](https://pypip.in/py_versions/django-docopt-command/badge.svg)](https://pypi.python.org/pypi/django-docopt-command/) [![Supported Python implementations](https://pypip.in/implementation/django-docopt-command/badge.svg)](https://pypi.python.org/pypi/django-docopt-command/)

Django-docopt-command allows you to write [Django](https://www.djangoproject.com) [manage.py](https://docs.djangoproject.com/en/dev/howto/custom-management-commands/) commands using the [docopt](http://www.docopt.org) library. This means that you can define commands using usage strings.

References:

* [Django](https://www.djangoproject.com): The Web framework for perfectionists with deadlines
* [The docopt library](http://www.docopt.org): Command-line interface description language
* [Writing custom django-admin commands](https://docs.djangoproject.com/en/dev/howto/custom-management-commands/)

```python
class Command(DocOptCommand):
	# This usage string defines the command options:
	docs = "Usage: command <option1> <option2> [--flag1]"

	def handle_docopt(self, arguments):
		# arguments contains a dictionary with the options
		pass
```

Django-docopt-command is tested with Django 1.4-1.8 and Python 2.6, 2.7, 3.3 and 3.4 and is hosted on [github](https://github.com/mbraak/django-docopt-command).

### Example

See the *testproject/docopt_example* in the django-docopt-command github repository.

## Usage

Install django-docopt-command.

```
pip install django-docopt-command
```

**Step 1 - management command**

Write a Django custom management command, as described in [Writing custom django-admin commands](https://docs.djangoproject.com/en/dev/howto/custom-management-commands/).

**Step 2 - inherit from DocOptCommand**

```python
class Command(DocOptCommand):
	pass
```

**Step 3 - add a docs string**

```python
class Command(DocOptCommand):
	docs = "Usage: command <option1> <option2> [--flag1]"
```

**Step 4 - override handle_docopt**

```python
class Command(DocOptCommand):
	docs = "Usage: command <option1> <option2> [--flag1]"

	def handle_docopt(self, arguments):
		option1 = arguments['option1']
		option2 = arguments['option2']
```

## License

Django-docopt-command is licensed under the Apache 2.0 License.
