# twitter-login

## Setup

```
$ git clone https://github.com/franmomu/twitter-login.git
$ cd twitter-login
$ composer install
$ TWITTER_CONSUMER_KEY=xxxx TWITTER_CONSUMER_SECRET=yyy TWITTER_OAUTH_CALLBACK=zzz php -S localhost:8000
```
Then you can access to: 

```
http://localhost:8000/twitter/login
http://localhost:8000/twitter/id
http://localhost:8000/twitter/callback
http://localhost:8000/twitter/logout
```

#### /twitter/login

This url redirects to the Twitter authorize page or in case the user is already logged in, it redirects to `/twitter/id`. 

#### /twitter/callback

This retrieve the tokens from the request and stores the user information, then it redirects to `/twitter/id`.

#### /twitter/id

It returns a JSON file like `{"id": "user_id"}` or redirects to `/twitter/login` if the user is not logged in.

#### /twitter/logout

This removes the user from the session
