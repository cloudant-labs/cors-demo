# CORS demonstration

This is a barebones demonstration of using jQuery to list your account's databases by making CORS requests of Cloudant.

To use it, first we'll edit out local hosts file to point `local.dev` at `localhost`:

    sudo vi /etc/hosts # add a line like "127.0.0.1 local.dev" to the end of the file

Now we'll configure CORS support on Cloudant. Swap `USERNAME` for your account name:

    curl -i -u USERNAME -X PUT https://USERNAME.cloudant.com/_api/v2/user/config/cors -H "Content-Type: application/json" -d '{"enable_cors":true,"allow_credentials":true,"allow_methods":["GET","PUT","POST","DELETE","OPTIONS"],"origins":["http://local.dev:8000"]}'

Then, download this repo:

    git clone git@github.com:cloudant-labs/cors-demo.git
    cd cors-demo
    python -m SimpleHTTPServer
    # visit http://local.dev:8000

That's it!

If you have any questions or run into any problems, post an issue to the repository or email <support@cloudant.com>. Thanks, and enjoy!

## License

[Apache](http://choosealicense.com/licenses/apache/), yo.
