```
$ sudo apt-get install build-essential curl file git
```
```
$ wget https://cache.ruby-lang.org/pub/ruby/2.6/ruby-2.6.8.tar.bz
$ tar xf ruby-2.6.8.tar.bz2
$ cd ruby-2.6.8
$ RUBY_VERSION="2.6.8"
$ PREFIX=/home/linuxbrew/.linuxbrew/Library/Homebrew/vendor/portable-ruby
$ INSTALL_DIR=${PREFIX}/${RUBY_VERSION}
$ ./configure --prefix=${INSTALL_DIR} --enable-load-relative --with-static-linked-ext --with-out-ext=tk,sdbm,gdbm,dbm --without-gmp --disable-install-doc --disable-install-rdoc --disable-dependency-tracking
$ make
$ make install
$ cd ${PREFIX}
$ ln -s ${RUBY_VERSION} current
$ export  PATH=${PREFIX}/current/bin:${PATH}
$ which ruby
$ ruby --version
```
```
$ nano .bashrc

+ export export PATH="/home/linuxbrew/.linuxbrew/Library/Homebrew/vendor/portable-ruby/current/bin:/home/linuxbrew/.linuxbrew/bin:${PATH}"
```

シェル再起

```
$ cd /home/linuxbrew/.linuxbrew/
$ sudo git clone https://github.com/Homebrew/brew /home/linuxbrew/.linuxbrew/Homebrew
$ sudo mkdir /home/linuxbrew/.linuxbrew/bin
$ sudo ln -s /home/linuxbrew/.linuxbrew/Homebrew/bin/brew /home/linuxbrew/.linuxbrew/bin
$ eval $(/home/linuxbrew/.linuxbrew/bin/brew shellenv)
```
シェル再起いるかも？
```
$ cd
$ which brew && brew -v
```
```
>> /home/linuxbrew/.linuxbrew/bin/brew
Homebrew 3.5.4
Homebrew/homebrew-core N/A
```

```
$ sudo chown -R $(whoami) /home/linuxbrew/.linuxbrew/
$ brew update --force
```
```
$ brew doctor
>> Warning: Your CPU architecture (arm64) is not supported. We only support
x86_64 CPU architectures. You will be unable to use binary packages (bottles).
You will encounter build failures with some formulae.
Please create pull requests instead of asking for help on Homebrew's GitHub,
Twitter or any other official channels. You are responsible for resolving
any issues you experience while you are running this
unsupported configuration.
```

