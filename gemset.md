## GEMSET

### CHECK les versions
    
    $ rails -v => ?
    $ ruby -v => ?


### INSTALL versions wanted
    
    $ rvm install 2.6.2
    $ gem install rails-v 5.2.1


### SET to DEFAULT as latest version
    
    $ rvm --default use 2.6.2


### CREATE the gemset for your project
    
    $ rvm --ruby-version use 2.6.2@name_of_your_project --create


### USE your gemset inside your new project folder
    
    $ rvm 2.6.2@name_of_your_project


### INSTALL GEMS needed for your project inside your gemset

You have already gem install globally on your machine but not inside your gemset.
The gemset is part aside from your local machine running under the ruby version
and differents gems specified and installed.
    
    $ gem install bundler
    $ gem bundle update --bundler --> this not work ? gem update ?
    $ ...


### Path of the gemset being used by a Rails application

    `$ rvm gemdir` in the folder app to know the path of the gemset being used by a Rails application


### WARNING RVM SETUP USING GEMSET

if you encounter some trouble with somes install like $ rails generate rspec:install, and you get:
    
    Ignoring bindex-0.7.0 because its extensions are not built.  Try: gem pristine bindex --version 0.7.0
    Ignoring bootsnap-1.4.3 because its extensions are not built.  Try: gem pristine bootsnap --version 1.4.3
    Ignoring byebug-11.0.1 because its extensions are not built.  Try: gem pristine byebug --version

try to fix with = rvm get stable --auto-dotfiles

source: https://github.com/rvm/rvm/issues/3788
