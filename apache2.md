# Hapus Apache2 on linux
**stop service apache2**
```ruby
$ sudo service apache2 stop
```
**hapus semua paket yg berhubungan dengan apcache2**
```ruby
$ sudo apt-get purge apache2
$ sudo apt-get autoremove
```
lankah diatas sudah berhasil uninsatll namun jika ingin memastikan file yang berkaitan dengan `apache2` itu telah bersi dihapus dengan cara menggunakan `whereis`
```ruby
$ whereis apache2
```
> output : apache2: `/etc/apache2`
hapus repo `apache2`
```ruby
sudo rm -rf /etc/apache2
```
