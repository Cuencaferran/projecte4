![foto](img_t02carlos/1.png)

Primer de tot hem de crear un disc de 10GB al emmagatzematge de la màquina. 


![foto](img_t02carlos/2.png)

Entrem a la màquina i anem a administracio de discos de windows. 


![foto](img_t02carlos/3.png)

I actualitzem el disc que hem creat al principi un cop actualitzat, li donem click dret i anem a nuevo volumen. 


![foto](img_t02carlos/4.png)

ens sortira aquesta part i li donem a siguiente 


![foto](img_t02carlos/5.png)

Aqui tambe posem siguiente sense tocar res


![foto](img_t02carlos/6.png)

I ja hem posat el disc anomenat T02W a dins de la màquina

![foto](img_t02carlos/7.png)

Entrem al buscador i busquem duplicati dowload.


![foto](img_t02carlos/8.png)

I descarreguem desde windows. 


![foto](img_t02carlos/9.png)

I sens posara a descarrega a descarregas


![foto](img_t02carlos/10.png)

![foto](img_t02carlos/11.png)

Un cop a dintre li donem a add + backups


![foto](img_t02carlos/12.png)

![foto](img_t02carlos/13.png)

posem un nom i una contrasenya 


![foto](img_t02carlos/14.png)

Al posem a un disc. 


![foto](img_t02carlos/15.png)

A la part de home 


![foto](img_t02carlos/16.png)

I posem cada 1 hora a las 20.


![foto](img_t02carlos/17.png)

En aquest apartat no toquem res li donem a siguiente 



![foto](img_t02carlos/18.png)

I un cop creat li donem a start. 


![foto](img_t02carlos/19.png)

S’ens comença a actualitzar al backup


![foto](img_t02carlos/20.png)

I ens surtira en vert la primera versio del backup. 

# BACKUPS DRIVE 

![foto](img_t02carlos/21.png)

Ara farem el backup del drive, posem un nom i una contrasenya.

![foto](img_t02carlos/22.png)

Escollim la destinació del drive. 

![foto](img_t02carlos/23.png)

Li donem a auth id i posem la nostre contra de drive personal ja que la de una escola no va. 

![foto](img_t02carlos/24.png)

posem el nostre link del drive i li donem a siguiente. 


![foto](img_t02carlos/25.png)

Al posem a home. 


![foto](img_t02carlos/26.png)

I al posem cada dia a las 18. 


![foto](img_t02carlos/27.png)

Aqui no posem res com a l’anterior backup 

![foto](img_t02carlos/28.png)

I li donem a start i sens actualitzara la segona backup 


![foto](img_t02carlos/29.png)

Un cop acabada entrem a las carpetes de ftxer i podem veure com ens surt las descarregues de duplicati en el disc creat. 


![foto](img_t02carlos/30.png)

I en el drive ens surten tambe tots els fitxers de duplicati 


![foto](img_t02carlos/31.png)

Anem a las nostre backups i li donem els tres punts i a restore. 


![foto](img_t02carlos/32.png)

Al posem a dintre del disc creat 


![foto](img_t02carlos/33.png)

![foto](img_t02carlos/34.png)

I ens hauria de sortir el restore fet correctament. 


![foto](img_t02carlos/35.png)

![foto](img_t02carlos/36.png)

![foto](img_t02carlos/37.png)

Ara fem al mateix amb el backup del drive 


![foto](img_t02carlos/38.png)

Al posem en el mateix disc que l’altre backup 


![foto](img_t02carlos/39.png)

![foto](img_t02carlos/40.png)

I ens surtirà completat el restore del backup del drive.

# PART LINUX: 

![foto](img_t02carlos/41.png)

Ara a la part de windows creem un disc tambe de 10GB abans de entrar la màquina 

# DISC NOU:

![foto](img_t02carlos/42.png)

nomes entrar fem un “lsblk -o NAME,SIZE,TYPE,MOUNTPOINT 


![foto](img_t02carlos/43.png)

Fem un “sudo parted /dev/sdb i ens donara la benvinguda a GNU parted i hem d’escriure help per veure la llista de ordres 

![foto](img_t02carlos/44.png)

Fem un lsblk -f per veure sda1 sda2 i sda3 


![foto](img_t02carlos/45.png)

I fem un sudo nano apt install xfsprogs per installar el xfsprogs


![foto](img_t02carlos/46.png)

fem un sudo mkfs.xfs -f /dev/sdb1 


![foto](img_t02carlos/47.png)

I amb el sudo mkdir -p /media/backup creem el /media/backup 
i despres amb el sudo mount /dev/sdb1 /media/backup montem la carpeta 


![foto](img_t02carlos/48.png)

Instal·lem el duplicity xfsprogs amb el sudo apt install duplicity xfsprogs 


![foto](img_t02carlos/49.png)

I creem els usuaris amb el sudo adduser usuari1 i li posem una contrasenya 


![foto](img_t02carlos/50.png)

I ara fem el mateix amb el usuari número 2 i li posem una contrasenya també


![foto](img_t02carlos/51.png)

Fem un cd /home/ferran i amb el fallocate -l 10M fitxer1.bin instal·lem tots els fitxers 



![foto](img_t02carlos/52.png)

Fem un export PASSOHRASE=”contrasenya_forta” 


![foto](img_t02carlos/53.png)

I fem la comanda sudo duplicity /home file:///media/backup/duplicity per crear el backup en el arxiu 


![foto](img_t02carlos/54.png)

Fem un sudo fallocate -l 4M /home/ferran/fitxer 5.bin i amb el export PASSPRHASE=”contrasenya_forta” i amb el  sudo duplicity /home file:///media/backup/duplicity 


![foto](img_t02carlos/55.png)

duplicity collection-status  file:///media/backup/duplicity mirem la collection estat 


![foto](img_t02carlos/56.png)

I fem un sudo umount /media/backup per desmuntar la carpeta 


![foto](img_t02carlos/57.png)

amb sudo nano /usr/local/bin/fullbackup.sh manualment hem de crear aquest arxiu tot a mà


![foto](img_t02carlos/58.png)

Després de l’arxiu fem aquesta comanda 


![foto](img_t02carlos/59.png)

Fem un sudo crontab -e per entrar al arxiu


![foto](img_t02carlos/60.png)

Un cop a dintre de l’arxiu abaix de tot posem 0 23 * * /usr/local/bin/fullbackup.sh per fer un backup a las 23 de cada dia a dins del directori


![foto](img_t02carlos/61.png)

Ara  entrem amb sudo nano /usr/local/bin/incrementalbackup.sh i creem el segon arxiu a mà 


![foto](img_t02carlos/62.png)

I fem al mateix després de fer l’arxiu fem aquesta comanda

![foto](img_t02carlos/63.png)

I posem una altre part que es 0 23 * * 1-6 /usr/local/bin/incrementalbackup.sh

# COMPROVACIONS: 

![foto](img_t02carlos/64.png)

Un cop fet tot aixo anem a las carpetes i podem veure que tenim els fitxers creats anteriorment a dintre de la carpeta creada anteriorment duplicity 


![foto](img_t02carlos/65.png)

Tornem a crear la carpeta amb el sudo mount /dev/sdb1 /media/backup ja que la hem desmontat anteriorment 

![foto](img_t02carlos/66.png)

fem un ls de la carpeta /media/backup/duplicity

![foto](img_t02carlos/67.png)

I tornem a fer un export PASSPRHASE=”contrasenya_forta” de la carpeta creada

![foto](img_t02carlos/68.png)

i tornem a veure l’estat del duplicity collection 
