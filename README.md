* Premessa

Nota: i commenti ('#') relativi al proxy vanno tolti se stiamo operando
dall'interno dell'Istituto Zuccante.

* Creazione 'in locale di' un progetto

	# export http_proxy="http://proxy.zuccante.it:8080/"
	# export https_proxy=$http_proxy
	mkdir hellodjango && cd hellodjango
	virtualenv venv2
	source venv2/bin/activate
	pip install django-toolbelt
	django-admin.py startproject hellodjango .
	nano Procfile
	foreman start

* Caricamento 'nel cloud' di un progetto

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

	# to push into github.com:
	# git remote add origin git@github.com:sdoro/hellodjango.git
	# git push -u origin master

* Modififica 'in locale' di un progetto gia' esistente

	cd hellodjango
	source venv2/bin/activate
	foreman start

* Modifica 'nel cloud' di un progetto gia' esistente

	cd hellodjango
	source venv2/bin/activate
	nano 'some files'
	git add 'list of edited files'
	git commit -m "Some changes ...'
	git push heroku master

