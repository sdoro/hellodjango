	mkdir hellodjango && cd hellodjango
	virtualenv venv2
	source venv2/bin/activate
	pip install django-toolbelt
	django-admin.py startproject hellodjango .
	vi Procfile
	foreman start
	pip install distribute -U
	pip freeze > requirements.txt
	vi hellodjango/settings.py
	vi hellodjango/wsgi.py
	vi .gitignore
	git init
	git add .
	git commit -m "my django app"
	heroku create
	ssh-keygen
	less /home/knoppix/.ssh/id_rsa.pub
	git push heroku master
	git push heroku master

	git remote add origin git@github.com:sdoro/hellodjango.git
	git push -u origin master
