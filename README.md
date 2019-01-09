# GraphQL_API_Testing

### Set Up / Installation
```
pip install django 
pip install graphene_django
pip install graphql_django
```
### Configuring Graphene Django

On the **{django_project_name}/settings.py**, add the following:
```
INSTALLED_APPS = (
    # At the end of all the default packages
    'graphene_django',
)
```
### Schema Settings
```
GRAPHENE = {
    'SCHEMA': '{django_project_name}.schema.schema',
}
```
### Creating database table
```
python manage.py makemigrations
python manage.py migrate
```

#### Creating your first schema
When starting with GraphQL - one of the first question we had is how do we build our GraphQL Server? As GraphQL has been released as a specification, we can build the server with any programming language, Here I am using Django(Python Web Framework).

A schema is a collection of objects that may contain multiple fields. Each field is calculated through resolvers that returns a value. Resolvers functions for a field will access the database and returns an object.

A schema is strictly typed and describes all possible data that can be received. GraphQL query schema and the structure of your database are not connected.

**Create the file {django_project_name}/schema.py for schema.

```
import graphene
import {app_name}.schema

# Query for getting the data from the server.
class Query({app_name}.schema.Query, graphene.ObjectType):
    pass

# Create schema
schema = graphene.Schema(query=Query)
```
**Creating your first query
