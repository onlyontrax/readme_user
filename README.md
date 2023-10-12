# readme_user
readme file draft for frontend


## 1. Set-up and installation

1. Clone this GitHub repository:

```jsx
git clone https://github.com/onlyontrax/dApp.git
```

1. Check Node.js version 

```jsx
node -v
```

> Must have at least version 12.22.7
> 

1. Check that Homebrew is installed.  

```jsx
brew -v
```

> This is not essential but will make the rest of the installation easier.
> 

1. Install Redis 

```jsx
brew install redis
```

<aside>
💡 To restart Redis after an upgrade:
`brew services restart redis`

Or, if you don't want/need a background service you can just run:
`/opt/homebrew/opt/redis/bin/redis-server /opt/homebrew/etc/redis.conf`

To check running services on system

`brew services`

To start redis:

`brew services start redis`

To run server:

`redis -server`

To stop redis:

`brew services stop redis`

</aside>

<aside>
💡 https://formulae.brew.sh/formula/redis#default

</aside>

1. Install FFMPEG 

```jsx
brew install ffmpeg
```

<aside>
💡 https://formulae.brew.sh/formula/ffmpeg#default




## 2. Configure API & server

Once all packages are installed, open codebase in root directory. Navigate to the api folder.

```jsx
cd api
```

Run yarn to install node dependencies

```jsx
yarn
```

Navigate to the api folder and create a .env file at the root 

Paste contents below into the .env file you have created:

```
NODE_ENV=localhost
HTTP_PORT=8080
# is private text. We use to generate jwt, and verify token or hash password
TOKEN_SECRET=s6u6jq3-Z5dn]H8}
MONGO_URI=mongodb+srv://olfrank:Hundorp97@atlascluster.djhaasy.mongodb.net/?retryWrites=true&w=majority
REDIS_HOST=127.0.0.1
REDIS_PORT=6379
REDIS_DB=0
REDIS_PREFIX=bee_queue

# Use for seed and some features
DOMAIN=onlyontrax.com

# api domain
BASE_URL=http://localhost:8080
USER_URL=http://localhost:8081

TEMPLATE_DIR=templates
MAILER_CONCURRENCY=1

EMAIL_VERIFIED_SUCCESS_URL=https://www.onlyontrax.com/
```

Start the Redis server

```jsx
brew services start redis
```

```jsx
redis-server
```

Run yarn migrate

```jsx
yarn migrate
```

Run yarn build

```jsx
yarn build
```

If error: error TS2688: Cannot find type definition file for 'ioredis’

```jsx
npm install --save-dev @types/ioredis@4.28.10
```

View here for more information: https://stackoverflow.com/questions/74246552/error-ts2688-cannot-find-type-definition-file-for-ioredis

```jsx
yarn start:dev
```

Visit [localhost:8080](http://localhost:8080) and you should receive a ‘Hello world!’ message if everything is working.

Navigate to the user folder and create a .env file at the root

```jsx
cd user
```

Paste contents below into the .env file you have created:

```
NODE_ENV=localhost
PORT=8081
API_ENDPOINT=http://localhost:8080
NEXT_PUBLIC_API_ENDPOINT=http://localhost:8080
NEXT_PUBLIC_SOCKET_ENDPOINT=http://localhost:8080

NEXT_PUBLIC_MAX_SIZE_IMAGE=100
NEXT_PUBLIC_MAX_SIZE_FILE=1000
NEXT_PUBLIC_MAX_SIZE_TEASER=1000
NEXT_PUBLIC_MAX_SIZE_VIDEO=5000
```

Run yarn to install node dependencies 

```jsx
yarn
```

Run yarn dev

```jsx
yarn dev
```

Visit [localhost:8081](http://localhost:8081) and you should be greeted with the **Sign in screen!**

If greeted with error:

```jsx
Module not found: Can't resolve 'react/jsx-runtime'
```

Install the following:

```jsx
yarn add @types/react@latest @types/react-dom@latest --dev
```

Navigate to the admin folder and create a .env file at the root

```jsx
cd admin
```

Paste contents below into the .env file you have created:

```
NODE_ENV=localhost
PORT=8082
# is api uri we will use in server side only. We don't share this url publicly 
API_ENDPOINT=http://localhost:8080
# is public utl where user can call api with ajax request
NEXT_PUBLIC_API_ENDPOINT=http://localhost:8080
# is base url to your front website. We use this param to show public link in some sections like Posts
NEXT_PUBLIC_SITE_URL=http://localhost:8081
# is url to paypal xclick form. It will help you yo configure sandbox or production 
NEXT_PUBLIC_PAYPAY_PAYOUT_URL=https://www.paypal.com/cgi-bin/webscr

NEXT_PUBLIC_MAX_SIZE_IMAGE=20
NEXT_PUBLIC_MAX_SIZE_FILE=1000
NEXT_PUBLIC_MAX_SIZE_TEASER=1000
NEXT_PUBLIC_MAX_SIZE_VIDEO=5000

NEXT_PUBLIC_BUILD_VERSION=1.3.0
```

Run yarn to install node dependencies 

```jsx
yarn
```

Run yarn dev

```jsx
yarn dev
```

Visit localhost:8082 and you should be greeted with the Admin panel:

`Username: admin@onlyontrax.com`

`Password: adminadmin`

**Install Studio 3T**

To download Studio3T visit https://studio3t.com/download/  and create a free account 

You can find the URI for MongoDB in the .env file of the api folder.
</aside>
