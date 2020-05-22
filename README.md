# Mina Nginx

[Mina](https://github.com/nadarei/mina) tasks for handle with
[Nginx](http://nginx.com/).

This gem provides several mina tasks:

    mina nginx:install  # Install template config to host repo for easy overrides
    mina nginx:setup    # Install config file to the server's shared dir + symlink
    mina nginx:print    # Print the nginx config from template in local terminal
    mina nginx:print_remote   # Print the nginx config on server in local terminal

    mina nginx:reload   # Reload Nginx
    mina nginx:restart  # Restart Nginx
    mina nginx:start    # Start Nginx
    mina nginx:status   # Status Nginx
    mina nginx:stop     # Stop Nginx

## Installation

    gem install specific_install
    gem specific_install https://github.com/huobazi/mina-nginx

Consider variables used by the nginx config, particularly:

* `application_name`       - application name; defaults to 'application'
* `nginx_socket_path` - path to socket file used in nginx upstream directive
* `server_name`       - application's nginx server_name (e.g. example.com); defaults to value for `domain`
* `domain`            - fqdn you are deploying to
* `deploy_to`         - deployment path
* `current_path`      - current revision path

Edit installed template as required.

## Recommended Usage

1. Follow install steps above; and
2. Invoke `nginx:setup` in your main `setup` task
3. Run `nginx:setup` (or base `setup`) to install config changes

n.b. if the config template has not been installed locally, `mina-nginx` will
fall back to the default template gracefully.

## Contributing

1. Fork it ( http://github.com/huobazi/mina-nginx/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
