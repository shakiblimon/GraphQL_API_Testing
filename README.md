# GraphQL_API_Testing
#### Set Up / Installation
```
pip install django 
pip install graphene_django
pip install graphql_django
```
####Configuring Graphene Django

On the **{django_project_name}/settings.py**, add the following:
```
INSTALLED_APPS = (
    # At the end of all the default packages
    'graphene_django',
)
```
#### Schema Settings
```
GRAPHENE = {
    'SCHEMA': '{django_project_name}.schema.schema',
}
```
####Creating database table
```
python manage.py makemigrations
python manage.py migrate
```
