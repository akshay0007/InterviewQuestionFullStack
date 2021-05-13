Python --
install python with all features

create a virtual env--
in project dir-- use below commands--
	python -m venv venv

	then go to venv/Scripts/ folder
	and then command prompt --> activate + enter
 
in command prompt --> it will show (venv) in command line




create project back from ../../
	pip install django
	pip install djangorestframework
	
	for mysql --
	pip install mysqlclient

	then install django and djangorestframwork

	then you will in project dir --	 django-admin startproject employee 
	
	now copy paste content of employee into project dir
	
then run command python manage.py runserver	
 
then use command --
	python manage.py makemigrations
	python manage.py migrate
	
now create super user for admin access-
	python manage.py createsuperuser

now migrate folder of users--
	python manage.py makemigrations app_name
	python manage.py makemigrations app_name

important file--
	python manage.py migrate app_name


now create new project inside proj dir--
	python manage.py startapp hrm
	
now we have file for db orm --
	models.py
	by default django use sqllite
	go to settings.py inside employee project 
	now we have section DATABASES={} WHERE we configure sqllite
	now add models into admin.py
	
	
now create db class files --
	
register your app inside setting.py inside employee
	INSTALLED_APPS
    	

Django--

	in setting.py


	'rest_framework'



	INSTALLED_APPS = [
		'hrm',
		'rest_framework',
		'django.contrib.admin',
		'django.contrib.auth',
		'django.contrib.contenttypes',
		'django.contrib.sessions',
		'django.contrib.messages',
		'django.contrib.staticfiles',
	]


now create to file api.py and serializers.py

