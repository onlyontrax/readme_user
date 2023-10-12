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

</aside>
