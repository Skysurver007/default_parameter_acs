# default_parameter_acs

https://github.com/Skysurver007/default_parameter_acs/raw/refs/heads/main/genieacs_backup_default.tar.gz



# 1. DOWNLOAD
```
wget "https://github.com/Skysurver007/default_parameter_acs/raw/refs/heads/main/genieacs_backup_default.tar.gz" -O genieacs_backup_default.tar.gz
```

# 2. Ekstrak file backup tersebut
```
tar -xzvf ~/genieacs_backup_default.tar.gz -C ~/
```
# 3. Restore ke MongoDB dan hapus konfigurasi yang salah (--drop)
```
sudo systemctl stop genieacs-cwmp genieacs-nbi genieacs-fs genieacs-ui
```

```
mongorestore --drop --db genieacs ~/genieacs_backup_default/genieacs
```
# 4. Restart seluruh layanan GenieACS agar memuat konfigurasi yang baru
```
sudo systemctl restart genieacs-cwmp genieacs-nbi genieacs-fs genieacs-ui
```
```
sudo systemctl start genieacs-cwmp genieacs-nbi genieacs-fs genieacs-ui
```
