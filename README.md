# default_parameter_acs

https://github.com/Skysurver007/default_parameter_acs/raw/refs/heads/main/genieacs_backup_default.tar.gz



# Pindah ke direktori home
cd ~
```
wget "https://github.com/Skysurver007/default_parameter_acs/raw/refs/heads/main/genieacs_backup_default.tar.gz" -O genieacs_backup_default.tar.gz
```




# 1. Ekstrak file backup tersebut
tar -xzvf ~/genieacs_backup_default.tar.gz -C ~/

# 2. Restore ke MongoDB dan hapus konfigurasi yang salah (--drop)
mongorestore --drop --db genieacs ~/genieacs_backup_default/genieacs

# 3. Restart seluruh layanan GenieACS agar memuat konfigurasi yang baru
sudo systemctl restart genieacs-cwmp genieacs-nbi genieacs-fs genieacs-ui
