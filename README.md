# Django React Boilerplate


This repository contains a boilerplate project setup for Django and React. The project contains backend user authentication with the Django Rest Framework and rest-auth. The frontend has react redux setup for user authentication by storing the token in localstorage.

## Backend development workflow

```json
virtualenv env
source env/bin/activate
pip install -r requirements.txt
python manage.py runserver
```

## Frontend development workflow

```json
npm i
npm start
```

## For deploying

```json
npm run build
```

## Semantic UI

Clone the react boilerplate

```
git clone https://github.com/justdjango/django-react-boilerplate.git
pip install -r requirements.txt

python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Then go to `home/urls.py` and comment out:

```python
# re_path(r'^.*', TemplateView.as_view(template_name='index.html')),
```

until we got a front-end.

Set react-semantic-ui ([Source](https://react.semantic-ui.com/usage))

```bash
npm i --save semantic-ui-react
npm i --save semantic-ui-css
npm i
npm start
```

An error occured (Similar to [this](https://github.com/gatsbyjs/gatsby/issues/11406), then I increased watchers limit:

```
echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

Add a layout from https://react.semantic-ui.com/layouts, creating a new file `src/containers/LandingPage.js` and copying an homepage layout within.

Add Landing Page to `src/routes.js`

```js
import HomepageLayout from "./containers/Home";
...
    <Route exact path="/" component={LandingPage} />

```