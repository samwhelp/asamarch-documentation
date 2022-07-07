

# asamarch-documentation

* [asamarch-documentation](https://samwhelp.github.io/asamarch-documentation/) ([GitHub](https://github.com/samwhelp/asamarch-documentation))
* [asamarch-repository](https://github.com/samwhelp/asamarch-repository)
* [asamarch-packaging](https://github.com/samwhelp/asamarch-packaging)
* [asamarch-iso-profile](https://github.com/samwhelp/asamarch-iso-profile)
* [asamarch-iso-release](https://github.com/samwhelp/asamarch-iso-release)
* [system-modeling](https://samwhelp.github.io/system-modeling/) ([GitHub](https://github.com/samwhelp/system-modeling))
* [note-about-asamos](https://samwhelp.github.io/note-about-asamos/) ([GitHub](https://github.com/samwhelp/note-about-asamos))


## Use Remote

* /etc/pacman.conf

``` ini
[asamos]
SigLevel = Optional TrustAll
Server = https://samwhelp.github.io/asamarch-repository/repo/main
```

run

``` sh
sudo pacman -Sy
```

run

``` sh
sudo pacman -S asamos-hello
```


## Use Local

run to clone

``` sh
sudo mkdir -p /opt/asamos/
sudo chmod 777 /opt/asamos/
git clone https://github.com/samwhelp/asamarch-repository.git /opt/asamos/asamarch-repository
```


* /etc/pacman.conf

``` ini
[asamos]
SigLevel = Optional TrustAll
Server = file:///opt/asamos/asamarch-repository/repo/main
```


run

``` sh
sudo pacman -Sy
```

run

``` sh
sudo pacman -S asamos-hello
```


## Use Include

* [/etc/pacman.d/asamos-mirrorlist](https://github.com/samwhelp/asamarch-packaging/blob/main/pack/base/asamos-mirrorlist/asset/etc/pacman.d/asamos-mirrorlist)

```
#Server = file:///opt/asamos/asamarch-repository/repo/main
Server = https://samwhelp.github.io/asamarch-repository/repo/main
```

* /etc/pacman.conf

``` ini
[asamos]
SigLevel = Optional TrustAll
Include = /etc/pacman.d/asamos-mirrorlist
#Server = file:///opt/asamos/asamarch-repository/repo/main
#Server = https://samwhelp.github.io/asamarch-repository/repo/main
```

run

``` sh
sudo pacman -Sy
```

run

``` sh
sudo pacman -S asamos-hello
```
