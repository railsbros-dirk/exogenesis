# Exogenesis

A collection of classes that help you install, update and teardown package managers and other things useful for your dotfiles. It's something like a meta package manager (package manager is the wrong word... still searching for a better one). You can use it to install/update/teardown your dotfiles or to create a single `update` command to update everything on your computer.

**Please read the source code of this gem before you use it. I give no guarantee that this will not destroy your computer entirely.**

## The Interface of the classes

Every class has the following methods (with the exception of `initialize` they all take no arguments):

* `initialize`: The arguments are arbitrary, please see the individual files for it
* `setup`: Installs the package manager itself
* `install`: Installs all packages (the list has to be provided in the initialize method)
* `update`: Updates the package manager itself and all packages
* `cleanup`: Starts a clean-up process
* `teardown`: Uninstalls all packages and the package manager itself

Not all package managers will need all of the methods. Just do not implement them.

## Contributing

Additions of new classes are more than welcome, even if they are complimentary to the ones already provided. If you want to contribute a new class, please see the interface section and inherit from `AbstractPackageManager`.
Your code has to work on Ruby 1.8.7, because the dotfile installers should work on Mac OS without installing a new Ruby version (and Mac OS still ships with 1.8.7)