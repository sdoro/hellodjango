	# export http_proxy="http://proxy.zuccante.it:8080/"
	# export https_proxy=$http_proxy
	mkdir hellodjango && cd hellodjango
	virtualenv venv2
	source venv2/bin/activate
	pip install django-toolbelt
	django-admin.py startproject hellodjango .
	nano Procfile
	foreman start
	pip install distribute -U
	pip freeze > requirements.txt
	nano hellodjango/settings.py
	nano hellodjango/wsgi.py
	nano .gitignore
	git init
	git add .
	git commit -m "my django app"
	heroku create
	ssh-keygen -f ~/.ssh/id_rsa_netkit -C "knoppix@netkit.org-$(date -I)"
	heroku keys:add /home/knoppix/.ssh/id_rsa_netkit.pub
	git push heroku master

	git remote add origin git@github.com:sdoro/hellodjango.git
	git push -u origin master
