## T06: Accés remot - Escriptori remot (RDP)

Per poder fer aquesta pràctica haurem de tenir dues VM una Windows i una Zorin, les dues amb xarxa NAT per a que puguin veures entre elles dins la xarxa.

Farem comprovacions inicials amb ping entre elles, abans haurem de desactivar el firewall de Windows, sino no funcionarà.


<img width="823" height="483" alt="image" src="https://github.com/user-attachments/assets/dd2a748a-b2e7-4e04-b08c-3148bbc1dffa" />



<img width="551" height="493" alt="image" src="https://github.com/user-attachments/assets/ac44d3ab-2ba8-4e78-96cb-421ffd65bfb3" />

Com a primer pas haurem de tenir una màquina virtual amb Windows i activar l’escriptori remot en aquesta. Des de configuració → Sistema → Escritorio remoto

Es recomanable deixar activada la autentificació a nivell de xarxa.

<img width="796" height="391" alt="image" src="https://github.com/user-attachments/assets/693b95fe-295a-416f-82d0-d0dbd6977b84" />

Hem de desactivar el friewall de windows ja que sino no ens deixa conectarnos desde la maquina zorin 
<img width="785" height="603" alt="image" src="https://github.com/user-attachments/assets/faa10c43-c438-45c0-8482-d9de275642fa" />

Hem d'entrar a usuaris d'escritori remot i hem ficat el nom del nostre pc

<img width="833" height="673" alt="image" src="https://github.com/user-attachments/assets/19e5cc4f-bd5e-4331-87ef-3e61d7ca1a31" />

Seguidament hem d'entrar a la maquina virtual de zorin. Provarem de conectarnos al escriptori remot de Windows per fer-ho hem d’obrir Remmina.

<img width="657" height="686" alt="image" src="https://github.com/user-attachments/assets/1f6e08ad-2fd3-43ef-8e76-3d6dc193e28a" />

<img width="825" height="328" alt="image" src="https://github.com/user-attachments/assets/8a042fd9-c5f8-4abc-8c4e-2160d295f7cc" />

<img width="943" height="995" alt="image" src="https://github.com/user-attachments/assets/357cb09f-faf0-459e-b5dc-6ff439798ca2" />

**Ara activarem el control remot a Zorin, per fer-ho accedim a Configuració → Compartir → Activar "Compartir pantalla" seguidament activem"Control remot" → Definir contrasenya.

Ara definim les dades d'accés segons sigui necessari.**

<img width="962" height="661" alt="image" src="https://github.com/user-attachments/assets/5fb8aba5-4a2a-4a47-bb7c-164aba3558db" />

<img width="691" height="800" alt="image" src="https://github.com/user-attachments/assets/c7758caa-fcd5-44f7-b7cd-c684911ac7a6" />


Des de Windows ara podem conectarnos a zorin, amb Escritorio Remoto. Obrirem l’aplicació i introduïrem les dades d’acces.

<img width="404" height="488" alt="image" src="https://github.com/user-attachments/assets/04ca15dc-5dc6-4c2d-8360-8585b198fa8b" />

Equipo: usuari-VirtualBox.local com hem observat abans quan hem configurat l’escritorio remoto a zorin. Usuario: usuari, ja que es el que hem definit a zorin.

<img width="620" height="600" alt="image" src="https://github.com/user-attachments/assets/64996999-e7f1-4141-a604-ff9adcf84226" />
Introduim la contrasenya que hem definit a ZORINOS 

<img width="398" height="439" alt="image" src="https://github.com/user-attachments/assets/b6d9be67-877d-480f-b511-a39bd0e86f6a" />


Acceptem i ja estariem conectats

<img width="1920" height="907" alt="image" src="https://github.com/user-attachments/assets/fdd3ea2c-8d16-4823-92ca-31f3116fb928" />




