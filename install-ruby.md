# Installing Ruby

## Objectives

* Install Ruby 
* Have the correct Ruby running
* Easily switch Ruby versions
* Execute a Ruby script

## Install rbenv and ruby (Mac and Ubuntu)

1. Fork and clone the REPO
1. cd to the repo folder
1. run the file ruby-script.sh in the terminal
```bash ruby-script.sh ```

The commands inside this file will let you install ruby and gem and ruby on rails

## Check up installations 
 - ruby version
 ```ruby -v```  
-  gems 
```gem -v ```
-  rbenv 
```rbenv -v```

```
~ $ ruby -v
ruby 2.6.3p62 (2019-04-16 revision 67580) [x86_64-darwin18]
~ $ gem -v
3.0.6
~ $ rbenv -v
rbenv 1.1.2
```

*Note:  rbenv is a lightweight Ruby version management tool*

## Common commands : 
- ruby testing shell  
```irb``` OR ```pry``` 
- To end it: ```CTRL+D```
- ruby version ```which ruby```
- Format for ruby files
```ruby fileName.rb``` 

## Helpful extensions for VS Code : 
- Ruby Solargraph
- Ruby
- Simple Ruby ERB
- VSCode Ruby
- rufo *prettier for ruby*



## Installations for Windows :
1. [Ruby Installer](https://rubyinstaller.org/)
1. install Ruby+Devkit 2.6.X (x64)
1. checkbox the run rdik install
1. install in order in the next window 1 , 2 , 3 
1. close & check your Ruby ver by ruby -v


## Helpful extensions for Atom:
- atom- runner




# Have the correct Ruby running

MacOS comes with its own version of Ruby. The OS uses Ruby to run various processes. So while it’s not terrible to mess with the configuration of your systems Ruby (i.e. changing permissions, sudo installing gems etc.), it’s better just have our own version that we can change and update without worrying about the side effects.   

If we run `$ ruby -v`, it'll output the standard one at the current time. Not every app uses this version, so we need to use our own tool to manage Ruby versions.


```ruby
# example.rb
puts "Hello World!"
```

```bash
# bash
ruby example.rb
```

Yay!
