# Deploy a Strapi Backend integrated with Cloudinary as an image provider and PostgreSql database

## Requirements

[Nodejs](https://nodejs.org/en/download/)

[yarn](https://classic.yarnpkg.com/)

[heroku account](https://wwww.heroku.com/)

[heroku CLI](https://wwww.heroku.com/)

[cloudinary account](https://cloudinary.com/)

download and install each of these

## 1 - Clone the repository

```bash
git clone https://github.com/Souhaib-Benbouzid/strapi-cloudinary-postgresql-heroku-example.git
```

### 2- install all the dependencies

```bash
 cd strapi-cloudinary-postgre-heroku-example && yarn
```

### 3- setup environment variables cloudinary & postgre in heroku

##### Login into your heroku account

```bash
heroku login
```

##### Create a heroku app

```bash
heroku create my-app
```

##### Create a hobby postgre database

```bash
heroku addons:create heroku-postgresql:hobby-dev
```

```bash
heroku git:remote -a your-heroku-app-name
```

##### display your database URI

```bash
heroku config
```

This should print something like this:

DATABASE_URL=postgres://username:password@host:port/database_name

i.e:

DATABASE_URL=postgres://ebitxebvixeeqd:dc59b16dedb3a1eef84d4999sb4baf@ec2-50-37-231-192.compute-2.amazonaws.com:5432/d516fp1u21ph7b.

##### split the DATABASE_URL into the following

```bash

heroku config:set DATABASE_USERNAME=ebitxebvixeeqd

heroku config:set DATABASE_PASSWORD=dc59b16dedb3a1eef84d4999sb4baf

heroku config:set DATABASE_HOST=ec2-50-37-231-192.compute-2.amazonaws.com

heroku config:set DATABASE_PORT=5432

heroku config:set DATABASE_NAME=d516fp1u21ph7b

heroku config:set CLOUDINARY_NAME=YOUR_CLOUDINARY_NAME

heroku config:set CLOUDINARY_KEY=YOUR_CLOUDINARY_KEY

heroku config:set CLOUDINARY_SECRET=YOUR_CLOUDINARY_SECRET_KEY

```

## Making changes to your project

first you need to build the strapi UI

```bash
yarn build
```

run development server

```bash
yarn develop
```

### deploy to heroku

remove origin repository and push your edits

```bash
git remote remove origin

git add .

git commit -m "initial commit"

git push heroku master
```

#### Congratulations your Strapi-API is deployed

##### Important: open your app and setup your api

```bash
heroku open
```

Created by [sohaib-benbouzid](https://wwww.sohaibbenbouzid.com)
