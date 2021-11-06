# MOUNT 
### cek nama drive
```ruby
$ sudo fdisk -l 
```
### biar rapi buat repo di directory `media`
```ruby
$ mkdir -p /media/data
```
### exce mount partisi dengan beberapa tipe
1. normal mount
```ruby
$ mount /dev/<device_name> /media/<repo_mount_tujuan> 
```
2. read only mount
```ruby
$ sudo mount -o ro /dev/sdb1 /media/<name_mount_point> 
```
3. read write mount
```ruby
$ sudo mount -o rw /dev/sdb1 /media/<name_mount_point> 
```

# UMOUNT 
```ruby
$ umount /media/<name_mount_pount>
```
> note : buat temen mau mount hdd read-only padahal sudah dibuat mount 
> bisa jadi karan pc anda terdatap dual boot sehingga shutdown dulu terus coba lagi
  
ini case saya mau copy file dari hdd yg sudah di mount tapi ke desible padahal sudah open folder in root. saya juga aneh dengan mount tsb kadang bisa copy file, kadang ga bisa. dan ternyata partisi yang kita mount masih terbaca di os lain dalam kasus ini drive saya masih terbaca oleh windows (jadi kek proses gantung diri wkwk) 
karna saya pakai dual boot satu windows satu nya lagi linux. nah caranya adalah shutdwon trus try again . semoga berhasil
  
**_kalau cara diatas tetap tidak bisa kalian bisa coba cara dibawah ini_**

- fixed paritsi ntfs karna pada dasarnya partisi windows biasanya menggunakan `ntfs`
```ruby
$ sudo ntfsfix /dev/sdb1
```
- lalu coba mount ulang
```ruby
$ umount /media/<name_mount_pount>
$ sudo mount -o rw /dev/sdb1 /media/<name_mount_pount>
```

jika cara diatas tidak ada keterangan error maka mount rw anda berhasil. thank you
