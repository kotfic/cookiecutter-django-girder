# cookiecutter-django-girder

# Creation
* Install [`cookiecutter`](https://pypi.org/project/cookiecutter/)
* Run: `cookiecutter https://github.com/girder/cookiecutter-django-girder.git`
  * Fill variables, as documented below.
  * This will create a new directory for you.
* In the new directory, initialize Git and connect it to your upstream repository.

## Variables
* `project_name`: A human-readable name for the project.
* `project_slug`: A PyPI package name, ideally dash-delimited.
* `pkg_name`: A Python module name (which must be underscore-delimited), used for the top-level Django project.
* `first_app_name`: A Python module name, used for the initial local Django app within this project. It's suggested that you use `core`, unless you know you will be creating multiple apps.
* `site_domain`: The fully-qualified domain name of the target production deployment.

## Delete example model migration

The cookiecutter includes some initial models and an associated migration,
as an example of how models should be written.

After you have created your first models and are ready to commit your code, you should **delete**
`{{ cookiecutter.pkg_name }}/{{ cookiecutter.first_app_name }}/migrations/0002_initial_models.py`
and run `./manage.py makemigrations` to create a new initial migration for your actual models.
Otherwise, the example models will be permanently included in the migration history.
