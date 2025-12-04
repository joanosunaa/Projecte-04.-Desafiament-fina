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

<img width="687" height="458" alt="image" src="https://github.com/user-attachments/assets/b48770d4-bf1e-4c36-b06a-4401a5c51c23" />

Ara podem verificar que estem treballant com si estiguessim des de ubuntu.

whoami
hostname

Si volem desactivar l’us de root en conexions ssh per garantir una major seguretat haurem d’editar l’arxiu /etc/ssh/sshd_config

<img width="857" height="480" alt="image" src="https://github.com/user-attachments/assets/50e9bc60-f3a7-4464-9f37-ca5bd3e30619" />

<img width="978" height="566" alt="image" src="https://github.com/user-attachments/assets/090c3d11-5f1e-44ab-ba4e-99d81b03ac29" />


Fent això indiquem que el port de connexió es el 20 (Port 20) i no permitim connexions a root (PermitRootLogin prohibit-password).

<img width="397" height="143" alt="image" src="https://github.com/user-attachments/assets/794a50bc-8249-4024-bde2-3a3d6f7f7568" />

Ara podem fer una llista d’usuaris autoritzats a la connexió remota modificant l’arxiu anterior (sudo nano /etc/ssh/sshd_config) afegint la línea.

<img width="592" height="166" alt="image" src="https://github.com/user-attachments/assets/8ddafde8-8664-4bf4-b18a-696b2b6a0bbb" />


AllowUsers {usuaris separats per comes}

Per fer comprovació, crearem un nou usuari (usuari2) i provarem de conectarnos per ssh amb aquest.

sudo adduser usuari2
ssh usuari2@192.168.56.106

<img width="451" height="95" alt="image" src="https://github.com/user-attachments/assets/bee1a2af-7bc9-4623-84c6-24650a772c49" />

Com a resultat tindrem l’acces denegat!!

Ara tot el trànsit desde el client s’envia com si fos el servidor, pero si volem afegir una redirección dinàmica (dynamic forwarding) ens hem de conectar amb una variació a la comanda.

ssh -D 9876 usuari@192.168.56.106

<img width="589" height="464" alt="image" src="https://github.com/user-attachments/assets/748b73dd-8df9-4d1d-b8b5-d5f05eaa0908" />


Ara configurarem el tunel de SOCKS.

<img width="424" height="562" alt="image" src="https://github.com/user-attachments/assets/a481dca0-83a0-4ad9-97cb-aff6e9b50109" />


<img width="383" height="330" alt="image" src="https://github.com/user-attachments/assets/5da6c283-5d97-4717-afad-d6bb3f9f4067" />




<img width="381" height="420" alt="image" src="https://github.com/user-attachments/assets/d0a82796-fb1a-40e8-b01a-44df6aa23408" />


Ara veurem com conectar-nos al ssh sense haver de posar la constrasenya. Per fer-hp primer de tot haurem de generar una ssh public key amb les seguents comandes.

<img width="753" height="455" alt="capt1" src="https://github.com/user-attachments/assets/1ab88ca9-2216-4b8e-ad05-1dba2bfd3adf" />



