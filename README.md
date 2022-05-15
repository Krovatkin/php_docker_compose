
### Customizing php.ini 

One can set custom options in `extra-php.ini`. The file is mounted in `/usr/local/etc/php/conf.d/`. The dir is scanned by php for additional configuration files in the seemingly alphabetical order.
`extra-php.ini` is loaded one of the last files and overrides options set by other files loaded earlier.

### Using XDebug

* Note, we are using `xdebug.client_host=localhost` since VSCode runs **inside** the container 
* Create a launch configuration with the debug port 9003 (or change `xdebug.client_port` in `Dockerfile` to use a different port)
    * One can double check the port w/ phpinfo in the XDebug section
    * `xdebug.start_with_request=yes` makes php check for the xdebug server (vscode) on every request
    * One may need to start a debug session in VSCode (clicking "Run") or PHP may error out
    * Alternatively remove `xdebug.start_with_request=yes` from `Dockerfile` and use `xdebug_break();` to start a debug session.
    * `xdebug_break();` still needs one to click "Run"