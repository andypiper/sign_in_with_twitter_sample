# Sign in with Twitter - Ruby sample

[![license](https://img.shields.io/badge/License-Apache%202.0-green.svg)](https://github.com/andypiper/TwitterDotNetCore/blob/master/LICENSE) [![Standard](https://img.shields.io/static/v1?label=Twitter%20API&message=v1.1&color=794BC4&style=flat&logo=Twitter)](https://developer.twitter.com/en/docs/api-reference-index)

This is a minimal, Ruby standalone web app to help you understand how to implement Sign in with Twitter.

* built as a Sinatra web app
* simple to install and run
* no dependency with external databases
* uses simple_oauth gem to enable free choice of HTTP client
* code comments linked to official Twitter docs

## Setup

The base requirement is to have Ruby and Bundler installed.

1. Create an app at [developer.twitter.com/apps](https://developer.twitter.com/apps) with:
    * read and write permission
    * callback set to http://dev.yoursite.com:4567/callback
      * note that this must be the correct URL for your app, as this is validated as part of the authentication process
    * Sign in with Twitter option checked
2. Clone this repo
3. Run `bundle install` to install dependencies
4. Rename `config/twitter_oauth.yml.sample` to `config/twitter_oauth.yml`
5. Fill `twitter_oauth.yml` with your consumer key and consumer secret from step 1
6. Optionally, change the var ACCOUNT_TO_FOLLOW in `app.rb` to set what account will be followed
7. Run the `sign_in_start` script
8. Open http://dev.yoursite.com:4567 in your browser

## The web app

This web app simply requires the user to Sign in with Twitter to be able to access "awesome" features. The features provided are the ability to follow an account (see step 6 above) or to display the logged-in user info, which is only available if users authorize your app to have access to it.

*This sample web app is intended for educational purposes, not for production.*

## The code

The Ruby code contains comments explaining what is happening at each step, with links to the official developer docs. The sign-in implementation is primarily in the `lib/twitter_sign_in.rb` file, with the `app.rb` file implementing the high level flow of authentication.

Data persistence is achieved using the [Daybreak](http://propublica.github.io/daybreak/) gem, and a default `db/signin.db` is used to store tokens and user info.

The front-end is built with Bootstrap, and all views and layouts are in the `views` folder.

## References

* Twitter Developer documentation: https://developer.twitter.com/en/docs/basics/authentication/guides/log-in-with-twitter
* Sinatra: http://www.sinatrarb.com/
* Daybreak: http://propublica.github.io/daybreak
* Simple oauth gem: https://github.com/laserlemon/simple_oauth

### Credits

Original version by Luis Cipriani
https://twitter.com/lfcipriani
https://github.com/lfcipriani/sign_in_with_twitter_sample
