Ruby
====

A very basic ruby image with ruby-install to set the basics
for ruby applications.

##Requiremenrs

A `.ruby-version` file needs to be present when building the image.
This file will determin which version of ruby will be installed.

##Side-effects

Images built on top will have the following characteristics:

* /home/app folder will contain the content of the folder in which the image is being built
* Bundler will be run on build, so the lack of a Gemfile will cause errors.
