# `heroku-buildpack-nginx`

## About

### Why?

[Heroku][] is an amazing deployment platform for your apps.
[nginx][] is a amazing webserver.

Why not get the best of both worlds?

### How?

`heroku-buildpack-nginx` works by downloading and compiling nginx (plus
dependencies) whenever you deploy.

### Demo

Check out [this][demo] demo to see how it works,and look at the (incredibly
simple) source [here][demo-source].

## Use

First, configure your app to use `heroku-buildpack-nginx` as its buildpack:

* For new apps:

```
heroku create --buildpack git://github.com/neersighted/heroku-buildpack-nginx
```

* For existing apps:

```
heroku config:add BUILDPACK_URL=git://github.com/neersighted/heroku-buildpack-nginx
```

All HTML files go in the root of your project (lay out any folders how you
like).

`heroku-buildpack-nginx` will be used if a `index.html`, `index.html`,
`index.xhtml`, or `index.php` is found in the root of your project.

### Configure

If you want to get real fancy, you can alter some config files:

* [config][]
* [nginx.conf.erb][]

To use them, simply copy either (or both) of these files into your project,
in the `config/` directory. You can then edit them (they are very
self-explanatory), and they will automagicly be used on the next build.

## Hacking

Fork this repo, and substitute any URLs with your own.

Pull requests are welcome.

## License

[LICENSE][]


[Heroku]: http://heroku.com
[nginx]: http://nginx.org

[demo]: http://heroku-buildpack-nginx-demo.herokuapp.com
[demo-source]: https://github.com/neersighted/heroku-buildpack-nginx-demo

[config]: https://github.com/neersighted/heroku-buildpack-nginx/blob/master/config
[nginx.conf.erb]: https://github.com/neersighted/heroku-buildpack-nginx/blob/master/default/nginx.conf.erb
[php.ini]: https://github.com/neersighted/heroku-buildpack-nginx/blob/master/default/php.ini
[php-fpm.conf]: https://github.com/neersighted/heroku-buildpack-nginx/blob/master/default/php-fpm.conf



[LICENSE]: https://github.com/neersighted/heroku-buildpack-nginx/blob/master/LICENSE
