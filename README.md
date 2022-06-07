# XBTS DEX Market API v2 

Windows environment settings
------------
* Download & install Ruby 2.7 https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-2.7.6-1/rubyinstaller-devkit-2.7.6-1-x64.exe
* `gem update --system`
* `gem install bundler`

Ubuntu environment settings
------------

* `sudo apt install ruby ruby-dev build-essential libffi-dev zlib1g-dev liblzma-dev nodejs patch`
* `gem update --system`
* `gem install bundler`

Build & Dev
------------------------------
* To do the first option, run local server for dev:

`bundle exec middleman server`

* Building html files:

`bundle exec middleman build`
