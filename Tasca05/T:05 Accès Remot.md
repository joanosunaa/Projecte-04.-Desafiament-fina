T05: Accés Remot. Connexió via SSH (tasca individual)
Haurem de tenir dues VM, les dues amb interfícies Xarxa NAT i Host-Only. Per tant amb DHCP activat (true).

A continuació instal·larem ssh

sudo apt upgrade && sudo apt update && sudo apt install ssh -y
<img width="846" height="455" alt="image" src="https://github.com/user-attachments/assets/00fd1168-a87a-4072-ab6e-05cb535b3a4e" />

<img width="632" height="204" alt="image" src="https://github.com/user-attachments/assets/be8a6a55-5718-4045-be07-af390e42051f" />

També habilitarem i iniciarem el servei ssh

sudo systemctl enable ssh
sudo systemctl start ssh
Per verificar

sudo systemctl status ssh
Un cop hem pogut observar quina es la IP del nostra servidor haurem d’instal·lar i configurar un client Windows, un cop estiguem dins haurem d’entrar a la terminal PowerShell, ara podrem conectarnos al servidor vía ssh.

ssh usuari@192.168.56.106
ssh usuari@[IP del servidor del adaptador host-only]

Ara podem verificar que estem treballant com si estiguessim des de ubuntu.

whoami
hostname
Si volem desactivar l’us de root en conexions ssh per garantir una major seguretat haurem d’editar l’arxiu /etc/ssh/sshd_config

Fent això indiquem que el port de connexió es el 20 (Port 20) i no permitim connexions a root (PermitRootLogin prohibit-password).


Ara podem fer una llista d’usuaris autoritzats a la connexió remota modificant l’arxiu anterior (sudo nano /etc/ssh/sshd_config) afegint la línea.

AllowUsers {usuaris separats per comes}

Per fer comprovació, crearem un nou usuari (usuari2) i provarem de conectarnos per ssh amb aquest.

sudo adduser usuari2
ssh usuari2@192.168.56.106


Com a resultat tindrem l’acces denegat!!

Ara tot el trànsit desde el client s’envia com si fos el servidor, pero si volem afegir una redirección dinàmica (dynamic forwarding) ens hem de conectar amb una variació a la comanda.

ssh -D 9876 usuari@192.168.56.106


Ara configurarem el tunel de SOCKS.


Ara veurem com conectar-nos al ssh sense haver de posar la constrasenya. Per fer-hp primer de tot haurem de generar una ssh public key amb les seguents comandes.




