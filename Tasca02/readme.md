# 📁 T02 — DRP & Còpies de Seguretat  
### *Cas pràctic: Implementació i proves de concepte*  
**Mòdul:** Seguretat Informàtica  
**Objectiu:** Posar en pràctica la política de còpies de seguretat dissenyada a la T01 i elaborar guies tècniques per al client.



## 🏢 Introducció al cas  
Després de definir una política de còpies per al client **Muntatges i Serveis Tècnics SL**, ara toca **implementar-la i documentar-la**. L’empresa necessita guies tècniques i proves de concepte perquè el seu personal pugui desplegar el pla de còpies de manera segura i autònoma.

La tasca es divideix en dues parts principals:  
1. **Còpies de seguretat en equips Windows (client)**  
2. **Còpies de seguretat en servidor Linux**



# 🧩 PART 1 — Còpia de seguretat en Windows (client)

L’empresa demana que es faci una excepció i es configurin còpies per a l’equip **Windows del director**, on guarda informació sensible que no està al servidor.

### 🎯 Objectiu  
Crear una política **3-2-1** utilitzant:  
- 📀 Còpia local → segon disc del mateix PC  
- ☁️ Còpia al cloud → Google Drive  
- 🛠 Eina → **Duplicati**

### 🖥️ Prova de concepte  
Per desenvolupar la guia tècnica:

- Crear una **VM Windows 11** amb:
  - Disc principal → sistema operatiu  
  - Disc secundari de **10 GB** → destí de còpies locals  

- Utilitzar un **compte de Google Drive no escolar**.

### 📌 Tasques a realitzar
- Instal·lació i configuració de **Duplicati**  
- Configurar:
  - Còpies **cada hora** del perfil d’usuari al disc secundari  
  - Còpia **diària a les 18:00** cap a Google Drive  
- Afegir arxius al perfil (especialment *Documents*)  
- Esborrar Documents i fer:
  - 🔄 Restauració des del disc secundari  
  - 🔄 Restauració des de Google Drive  

Documentar tot el procediment com una *guia pas a pas*.



# 🧩 PART 2 — Còpia de seguretat del servidor Linux

Per al servidor Linux, es farà servir **Duplicity**, juntament amb **cron**, per implementar còpies completes i incrementals.

### 🖥️ Prova de concepte en Ubuntu Server  
Crear una VM amb:
- **Ubuntu Server**
- Segon disc de **10 GB**, que actuarà com a unitat auxiliar



## 🧪 Procediment tècnic a documentar

### 🔹 Preparació de la unitat
1. Inicialitzar i formatar el disc en **XFS**  
2. Crear `/media/backup`  
3. Muntar la unitat manualment  
4. Instal·lar **Duplicity**

### 🔹 Preparació del sistema
5. Crear 2 usuaris nous amb carpeta home  
6. Crear arxius de prova (4 fitxers de 10 MB)  

### 🔹 Proves de còpia
7. Fer una còpia completa de **/home**  
8. Esborrar els fitxers i fer una **restauració**  
9. Crear un nou fitxer de 4 MB i fer una nova còpia per comprovar que és **incremental**  
10. Desmuntar la unitat de backup  



# ⚙️ Automatització amb scripts + cron

La unitat de backup ha d'estar **sempre desmuntada per defecte**, i només es munta durant la còpia.

### 🔹 Script 1 — `fullbackup.sh`
- Fa una còpia **completa** de `/home`  
- Usa la variable d’entorn `PASSPHRASE`  
- S’ha de marcar com executable  
- Programar amb **cron**:
  - ⏰ *Diumenge a les 23:00* com a *root*

### 🔹 Script 2 — `incrementalbackup.sh`
- Fa una còpia **incremental** de `/home`  
- Usa també `PASSPHRASE`  
- Marcar com executable  
- Programar amb **cron**:
  - ⏰ *De dilluns a dissabte a les 23:00* com a *root*



# 📚 Recursos
- **Duplicati:** https://duplicati.com/  
- **WayToIT — Crear arxius (Windows):** https://waytoit.wordpress.com/2015/03/15/creando-archivos-con-fsutil/  
- **WayToIT — Crear arxius (Linux):** https://waytoit.wordpress.com/2015/03/21/creando-archivos-de-prueba-en-linux/  
- **Duplicity man page:** http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html  
- **Cron — Programar tasques:** https://geekytheory.com/programar-tareas-en-linux-usando-crontab



> ✨ *Tasca enfocada a aprendre com implementar, provar i automatitzar còpies de seguretat reals en entorns Windows i Linux, preparant guies professionals per al client.*

