Description
========================================

This is a simple nginx configuration setup that does nothing more
than run nginx listening for HTTP on port 80 and HTTPS on port 443, and proxy
all requests to localhost port 3000.

It is not setup to serve static files via nginx, perform any caching, etc. It
is really meant as a quick and easy way to let you run whatever local server
process you want on localhost:3000 and be able to hit it at
http://localhost and https://localhost.

This has really only been tested on Max OS X 10.6 (Snow Leopard).


Installation
========================================

    git clone git://github.com/scottwb/simple-nginx-reverse-proxy.git
    cd simple-nginx-reverse-proxy
    rake nginx:install

This `nginx:install` task is Mac OS X-specific. It checks to see if nginx is
installed via MacPorts, and if it is not, then it installs it via MacPorts.
This will ask you for the `sudo` password.

It will also create a self-signed PEM certificate for SSL and prompt you to
enter the certificate information. This information is not really important.
Enter whatever you like.


Operation
========================================

From inside the `simple-nginx-reverse-proxy` directory, you can run the
following commands:

    rake nginx:start    # Starts nginx.
    rake nginx:stop     # Stops nginx.
    rake nginx -T       # Shows all available tasks.

The `nginx:start` and `nginx:stop` tasks run as `sudo` and will prompt for
the `sudo` password.


License
========================================
Scripts and config files created by Scott W. Bradley (scottwb). Do whatever
you want with it.

