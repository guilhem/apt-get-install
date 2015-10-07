# apt-get-install

Simple wrapper to use for clean `apt-get install`  
Really useful when using docker layers

## Install

### PPA (ubuntu)

https://launchpad.net/~apt-get-install/+archive/ubuntu/ppa

```
sudo add-apt-repository ppa:apt-get-install
sudo apt-get update
sudo apt-get install apt-get-install
```

### ADD

```
ADD https://raw.githubusercontent.com/guilhem/apt-get-install/master/apt-get-install /usr/bin/
RUN chmod +x /usr/bin/apt-get-install
```

## How to use

Before (dirty)
```
RUN apt-get install -y my_package
```
Before (clean)
```
RUN apt-get update && apt-get install -y my_package && apt-get autoremove && apt-get clean
```

After
```
RUN apt-get-install my_package
```
