# Creació de còpies de seguretat

## 1. Creació d’un disc dur de 10 GB

Primer de tot, hem de crear un disc dur de **10 GB**.




<img width="618" alt="image" src="https://github.com/user-attachments/assets/4b0ea27e-9958-4721-b7f2-5b12893eb490" />

<img width="618" alt="image" src="https://github.com/user-attachments/assets/4afec940-3551-4d64-afb5-ecb8d214d969" />

 <img width="618"  alt="image" src="https://github.com/user-attachments/assets/512feeba-1972-4ac9-a2e5-fde85adf46c1" />

**Un cop li donem  add. s’obrirà aquesta** 

<img width="618" alt="image" src="https://github.com/user-attachments/assets/874ff2d6-a3c6-4c83-b01b-8b8b8f49cdc0" />

<img width="618" alt="image" src="https://github.com/user-attachments/assets/2a852d05-e9d0-4c5e-bb80-098f233d27fc" />

<img width="618" alt="image" src="https://github.com/user-attachments/assets/58f64393-d065-4aa1-8002-2400eddb30ec" />

<img width="618" alt="image" src="https://github.com/user-attachments/assets/c0af3db8-0d02-4867-890d-4081bb89d2e9" />

## 2. Creació d’un backup al núvol

**Ara hem de crear un altre **backup**, però aquesta vegada que sigui de **cloud**, utilitzant **Google Drive**.

<img width="618" alt="image" src="https://github.com/user-attachments/assets/c2ea1aef-60dd-47e3-a66a-3e44fef54443" />

<img width="618"  alt="image" src="https://github.com/user-attachments/assets/98d39dfc-ac4e-4b78-82c1-47513a258e91" />

<img width="618"  alt="image" src="https://github.com/user-attachments/assets/8380627b-4f7b-4a1e-9b12-fe2ed88a2f48" />

<img width="618"  alt="image" src="https://github.com/user-attachments/assets/c88023d0-2c53-472f-9566-1d65ca5d7e4e" />

## Part 2: Còpia seguretat servidor Linux


**De la mateixa manera que la VM de Windows haurem de tenir dos disc durs, el per defecte i un segon on guardarem les còpies. **

<img width="618" alt="image" src="https://github.com/user-attachments/assets/e0809198-8da5-478e-a64e-30d49b3c9ef3" />

Un cop dins la màquina verifiquem que estigui detectant aquest disc amb:
**lsblk**

<img width="618"  alt="image" src="https://github.com/user-attachments/assets/ac621b66-5dfc-4e1d-859e-1c803811832d" />

Creem una partició sobre el nou disc amb la comanda:
sudo fdisk /dev/sdb

<img width="618"  alt="image" src="https://github.com/user-attachments/assets/fbaa0e4e-d012-4f66-a222-003192dbf5ba" />

Un cop ens aparegui el “menu” indicarem les instruccions:
n → Per crear una nova partició
p → indiquem que es primària
Enter
Enter
Enter
W → Guardar i sortir

<img width="618"  alt="image" src="https://github.com/user-attachments/assets/b1673750-22e4-4b16-9e42-2553deff1a0f" />

<img width="618"  alt="image" src="https://github.com/user-attachments/assets/c629e784-b3ca-48ea-8fb1-e89b8724e3c8" />

**Formategem el disc en format XFS, pero primer de tot haurem d’instal·lar el servei XFS **
```
sudo apt install xfsprogs
```
<img width="618"  alt="image" src="https://github.com/user-attachments/assets/d2221638-80c5-4bc4-b8ec-03dd311af59d" />

sudo mkfs.xfs /dev/sdb1

<img width="618" alt="image" src="https://github.com/user-attachments/assets/1af326cf-6908-472b-bb86-c74866799c8c" />

Seguidament crearem una carpeta i muntarem el disc a aquesta.
```
sudo mkdir -p /media/backup
sudo mount /dev/sdb1 /media/backup
```
<img width="618"  alt="image" src="https://github.com/user-attachments/assets/5b6fdb9b-40e2-4d34-895b-c5fc447cab4c" />

Podem comprovar si està muntat correctament amb la comanda.
```
df -h | grep backup
```
<img width="618"  alt="image" src="https://github.com/user-attachments/assets/87e0f79b-5634-45ab-a619-9a995d9805f3" />

Ara instal·larem duplicity, l’eina per automatitzar les còpies.
```
sudo apt install duplicity -y
duplicity –version
```
<img width="618"  alt="image" src="https://github.com/user-attachments/assets/0c906fc5-09ff-423c-b1d1-42f5d70b1d5d" />

Crearem dos usuaris, asegurant-nos que tenen directoris personals.
```
sudo adduser usuari1
sudo adduser usuari2
```
<img width="618" alt="image" src="https://github.com/user-attachments/assets/3f6b45a7-3d39-4eb8-b8e0-5e635db959f5" />

<img width="618" alt="image" src="https://github.com/user-attachments/assets/a21810d2-3129-45c8-a0b7-f26e4b2dc16f" />

Ara crearem 4 fitxers de 10 MB dins el directori que hem creat anteriorment.
for i in 1 2 3 4; do sudo dd if=/dev/zero of=fitxer$i bs=1M count=10; done

<img width="618" alt="image" src="https://github.com/user-attachments/assets/63e86fb6-a0cc-4db9-a369-6ba5eabdd444" />

Comprovem amb:
```
ls -lh
```
<img width="618"  alt="image" src="https://github.com/user-attachments/assets/9ea278a0-6417-419b-a1ea-42cc3237b569" />

Crearem la copia amb duplicity, ens demana un passphrase (contrasenya) la qual la xifrarà.
```
sudo duplicity /home file:///media/backup/home-backup
```
<img width="618" alt="image" src="https://github.com/user-attachments/assets/722163f4-8ecb-40b6-a762-718f9fe80a8c" />


Al finalitzar, podem observar que hi ha al directori destí.

<img width="618"  alt="image" src="https://github.com/user-attachments/assets/2cf6c149-a0f6-4b4d-ae56-1a069c3a255d" />

Seguidament esborrarem els arxius de prova creats anteriorment per veure si els pots restaurar correctament 
```
sudo rm fitxer1 fitxer2 fitxer3 fitxer4
ls
```
<img width="618"  alt="image" src="https://github.com/user-attachments/assets/7b56dd05-8dca-4304-b87a-e92927f2ceea" />

Ara restaurarem els arxius amb duplicity
```
sudo duplicity restore file:///media/backup/home-backup /home/restored

ls /home/restored/usuari
```
<img width="618"  alt="image" src="https://github.com/user-attachments/assets/62bfc973-0b4d-4c58-8d26-1320396bce60" />

Com podem observar ens ha restaurat els fitxers.

Ara afegirem un fitxer nou i veurem com la nova còpia és incremental.​
```
sudo dd if=/dev/zero of=fitxer_nou bs=1M count=4
ls -lh
```
<img width="618" alt="image" src="https://github.com/user-attachments/assets/6417e60e-b48b-4453-94d9-4cc239fd3e1f" />

Executarem la mateixa comanda d’abans per crear la còpia.
```
sudo duplicity /home file:///media/backup/home-back
```
<img width="618"  alt="image" src="https://github.com/user-attachments/assets/c5bd6db1-edcd-493e-9022-9b3b8bb73528" />

Podem veure l’informació del backup
```
sudo duplicity collection-status file:///media/backup/home-backup
```
<img width="618" alt="image" src="https://github.com/user-attachments/assets/5f99092c-8fb5-46c7-ab25-c7b650279fdf" />

Ara desmontem l’unitat
```
sudo umount /media/backup
```
I comprovem 
```
df -h | grep backup
```
<img width="618"  alt="image" src="https://github.com/user-attachments/assets/f5a021ea-a1b3-43e6-9ef3-bacce46dfa71" />
Ara automatitzarem tots aquest procesos amb un script.

sudo nano /root/fullbackup.sh

```

#!/bin/bash

mount /dev/sdb1 /media/backup

export PASSPHRASE="la_teva_contrasenya"

duplicity full /home file:///media/backup/home-backup

unset PASSPHRASE

umount /media/backup

```

<img width="618"  alt="image" src="https://github.com/user-attachments/assets/a05aebaa-bb06-4c26-bc89-79d42b2167e6" />

Ara donem permisos d’execució a aquest script.
```
sudo chmod +x /root/fullbackup.sh
```
<img width="618" alt="image" src="https://github.com/user-attachments/assets/9bd368af-ae98-46e1-82af-8e117041818f" />

I el provem manualment
```
sudo /root/fullbackup.sh
```
<img width="618"  alt="image" src="https://github.com/user-attachments/assets/be8d6bde-c2f1-43cf-a51b-94b77ceae963" />

Si no dóna errors, està bé.​

Ara programarem l'execució amb cron.
```
sudo crontab -e 
```
I afegim aquesta línea al final:
```
0 23 * * 0 /root/fullbackup.sh
```

<img width="618"  alt="image" src="https://github.com/user-attachments/assets/828ed722-f50d-44d7-84c0-988a8c2a10b4" />

Guardem els canvis amb 
```
sudo crontab -l
```

<img width="599" height="618"  src="https://github.com/user-attachments/assets/f39760da-184d-4677-bab6-3fee69fe8063" />




