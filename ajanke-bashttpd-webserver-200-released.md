Ajanke BasHTTPd Webserver 2.0.0. Released

## Greetings! ##
----------
Hello World! The Ajanke Foundation is proud to announce that after a rewrite of the code base and implementation of basic testing with Travis-CI & bashtest, BasHTTPd is now 2.0.0!

https://github.com/AjankeFoundation/bashttpd/releases/tag/2.0.0

## Where Ajanke's BasHTTPd is Headed ##
----------
You might be wondering how the software was changed from the avleen/bashttpd original version, and why it was forked instead of contributed to.  Well, first and foremost, the platform has been simplified and given some sensible defaults.  Avleen's release included a configuration file that would allow you to somewhat emulate the "Alias" feature of other web servers.  This, and others, were great features, but were removed in favor of simplicity.  Since BasHTTPd is not recommended for large-scale production environments, it's primary use case is sharing files quickly over a private network with minimal tools and setup. This makes it a great choice for small devices like Raspberry Pis, or for easily sharing files from your laptop between your friends on the same private network.  Having a configuration file and URI matching features falls outside of the scope of that use case.  The main goal of this project is to make BasHTTPd easy to install, intuitive to use, and a go-to private network web server solution for anyone with a bash shell.

## What is new to the 2.0.0. Release? ##
----------
The 2.0.0. release adds in some notable developer features including: bebug logging, more verbose output in general, and additional comments in the script.  This version replaces some of the configuration options of the server in exchange for sensible defaults that make it more usable for file sharing. This release also improves some preexisting features of the previous release.  For example, BasHTTPd is now able to serve binary data in addition to textual file formats like HTML.  It also has a reduced amount of dependencies, and the ones that it did keep require less flags.  This will help it run more reliably across different versions of Linux and other Unices.

## What is coming next? ##
----------
The next major release will likely completely eliminate support for `netcat` and `socat` and replace those with `tcpserver` as the default TCP connection engine.  As mentioned in the documentation, `netcat` has a serious limitation: it can only handle one connection before closing. `socat` on the other hand, does not ship with reliable switches/options that are uniform across operating systems.  While these long-standing GNU utilities are usually the best option at maintaining compatibility across Unices, that is just not the case with these particular utilities.  As a result, one of two approaches must be taken. A) I need to write a small CLI to accompany `bashttpd.sh` that would detect the type of TCP engines installed, and select the best one, with the right flags. B) I have the script install check for `tcpserver`, and if it isn't present, download and install it the first time `bashttpd.sh` runs on a box. Option A requires numerous more dependencies and multiplies the complexity of BasHTTPd. As a result, Option B is much more likely to happen.

## What About Minor Improvements? ##
----------
Minor releases are going to be focused on improving the current features, and adding in the ability to upload files as well as download.

## Contributing ##
----------
Contributions via pull requests are always welcome. If you have an idea for a feature or use case, please make your voice heard on the Github.

Thanks for your time, and stay janky, Bash hackers!

