# django
장고
from django.db import migrations

def create_initial_data(apps, schema_editor):
    NewModel = apps.get_model('newapp', 'NewModel')
    NewModel.objects.create(name='park', skill='django')
    NewModel.objects.create(name='lee', skill='react')

class Migration(migrations.Migration):
    dependencies = [
        ("newapp", "0002_auto_20230919_1554"),
    ]

    operations = [
        migrations.RunPython(create_initial_data)
    ]
