username:admin
password:password



python manage.py runserver


python manage.py createsuperuser

python manage.py makemigrations 
python manage.py migrate        





TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, "templates")        --------------->added templates path
                 ],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]


Added static files manually
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, "static")
]



How to create a database 

1. Created models at home.models your models here.
2.Added this to home.admin
    from home.models import Contact
    # Register your models here.
    admin.site.register(Contact)

3. added "ome.apps.HomeConfig" from home.apps to mysite settings
INSTALLED_APPS = [

    'home.apps.HomeConfig', ----------------> added this from home.apps to mysite settings
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
4.
python manage.py makemigrations
5.
python manage.py migrate  

6. we are doing this in home.models to show name of the person in the admin panel 
    def __str__(self):
        return self.name
