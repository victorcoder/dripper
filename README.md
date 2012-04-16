Dripper
=======

Dripper is a collection of scripts (drips) to install software packages
with [stow], the GNU package manager.


Install
-------

Clone the repository and run the install script:

    git clone git://github.com/fesplugas/dripper.git
    cd dripper
    ./install.sh

If you install `drip` in single user mode add the following lines to
your `.bashrc`:

    if [ -d $HOME/.packages ]; then
      export PATH="$HOME/.packages/bin:$PATH"
    fi

Now you can instal `stow` using drip:

    drip install stow-1.3.3


Uninstall
---------

If you need to uninstall `dripper`:

    drip unlink --all
    rm -rf $HOME/.packages/stow


Usage
-----

Install a `drip`:

    drip install redis-2.4.10

Uninstall a `drip`:

    drip uninstall redis-2.4.10

Disable a `drip`:

    drip unlink redis-2.4.10

Enable a `drip`:

    drip link redis-2.4.10

Update the system:

    drip update

You can get a list of all available commands by running `drip`.


Requirements
------------

You'll need `git` to be able to update drips:

    drip install git-1.7.1.0

Some `stows` require `hg`. At this moment the best thing you can do
to install Mercurial is by using `pip`:

    sudo easy_install pip
    sudo pip install mercurial


Conventions
-----------

- Sources are downloaded into `/usr/local/src` or `$HOME/.packages/src`.
- Packages are compiled into `/usr/local/stow` or `$HOME/.packages/stow`.


TODO and Whishlist
------------------

- Package and install from url.
- Do not download a drip if already in `$SRC_PATH`.
- Uninstaller.
- Detect already installed `drips`.


Acknowledgements
----------------

Thanks to [Homebrew], it's an awesome tool. As and [stow] user I
always wanted to do something similar and [Homebrew] has inspired
many of the commands used by `drip`.

Thanks to [ruby-build] and [rbenv], project organization has been
heavily inspired by them. Also some "helpers" used in [drip-helper]
have been copied from [rbenv].


[stow]: http://www.gnu.org/s/stow/
[ubuntu]: http://www.ubuntu.com/
[redhat]: http://www.redhat.com/
[Homebrew]: https://github.com/mxcl/homebrew
[ruby-build]: https://github.com/sstephenson/ruby-build
[rbenv]: https://github.com/sstephenson/rbenv
[drip-helper]: https://github.com/fesplugas/dripper/blob/master/libexec/drip-helper
