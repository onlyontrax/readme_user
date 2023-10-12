# readme_user
readme file draft for frontend





Clone this GitHub repository:
git clone https://github.com/onlyontrax/dApp.git


Check Node.js version (Must be >= 12.22.7)
node -v

Check that Homebrew is installed (This is not essential but will make the rest of the installation easier.)
brew -v

Install Redis 
brew install redis

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

