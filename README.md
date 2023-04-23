# django-todo
A simple todo app built with django

![todo App](https://raw.githubusercontent.com/shreys7/django-todo/develop/staticfiles/todoApp.png)
### Setup
To get this repository, run the following command inside your git enabled terminal
```bash
$ git clone https://github.com/shreys7/django-todo.git
```
You will need django to be installed in you computer to run this app. Head over to https://www.djangoproject.com/download/ for the download guide

Once you have downloaded django, go to the cloned repo directory and run the following command

```bash
$ python manage.py makemigrations
```

This will create all the migrations file (database migrations) required to run this App.

Now, to apply this migrations run the following command
```bash
$ python manage.py migrate
```

One last step and then our todo App will be live. We need to create an admin user to run this App. On the terminal, type the following command and provide username, password and email for the admin user
```bash
$ python manage.py createsuperuser
```

That was pretty simple, right? Now let's make the App live. We just need to start the server now and then we can start using our simple todo App. Start the server by following command

```bash
$ python manage.py runserver
```

Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.
#
#

# CICD Deployment 

- Fork this repository
- Integrate your Jenkins and GitHub using Personal Access Token. Select Secret Text as credentials in jenkins.

# Configuring Jenkins

- Select New Item

- Add name of the item and select Freestyle project In the Configure page, add github url.

- In Source Code Management, add github url, repository branch and in credentials, Personal Access Token.

- Under "Build Trigger" select "GitHub book trigger for GITSome pulling".

- Under "Build Steps", select "Execute Shell" and add an echo statement and click "Save".

# Configuring Jenkins webhook in github

- In your git repository, go to "settings" and then "Webhooks".

- Click "Add webhook" button. The payload url will be "http://<Jenkins-url>/github-webhook/". Click on Add webhook.

- as Build the project Go to your jenkins dashboard, Configure --> Build Steps--> Execute shell.

- Add the following commands: "docker-compose down'

- docker-compose up -d' Save and build the project.

- Verify whether build is successful.

- Browse public IP address with port 8000.

Cheers and Happy Coding :)
