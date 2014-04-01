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
	ssh-keygen -f ~/.ssh/id_rsa_netkit -C "knoppix@netkit.org-$(date -I)"
	heroku keys:add /home/knoppix/.ssh/id_rsa_netkit.pub
	git push heroku master

	git remote add origin git@github.com:sdoro/hellodjango.git
	git push -u origin master
