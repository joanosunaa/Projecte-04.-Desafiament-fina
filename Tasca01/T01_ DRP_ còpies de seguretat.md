# **T01: DRP: còpies de seguretat. Estudi cas client (treball cooperatiu)**

| Breu descripció | Introducció La primera hora el vostre responsable de seguretat us presenta el tema de les còpies de seguretat a partir d’un material didàctic. A continuació, caldrà que hi treballeu els aspectes del tema i ho fareu mitjançant una dinàmica cooperativa. Presentació del cas client "Muntatges i Serveis Tècnics SL" és una petita empresa dedicada a la instal·lació i manteniment d'equips industrials. Infraestructura Tècnica: ·         Servidor de Fitxers (Ubuntu Server): Conté tota la documentació crítica: o   Documents de Projectes: Plànols, especificacions tècniques (300 GB, creixement moderat). o   Bases de Dades (Comptabilitat i Clients): Crítiques i d'ús diari (20 GB, canvi constant). o   Carpetes Personals dels Usuaris: Per a la feina diària (100 GB). ·         10 Equips Clients (Windows 10/11): Els usuaris treballen majoritàriament amb fitxers del servidor, però alguns tècnics guarden de forma temporal informes i altres arxius importants a la carpeta Documents. ·         Connexió a Internet: Fibra òptica de 600 Mbps (simètrica). Requisits de Recuperació: ·         Temps de Recuperació (RTO): Les dades de Comptabilitat/Clients han d'estar disponibles en menys de 4 hores. ·         Pèrdua de Dades Admesa (RPO): Es pot admetre una pèrdua màxima de 24 hores per a la majoria de dades, però les dades de Comptabilitat/Clients no poden perdre més de 4 hores de treball. ·         Retenció: Cal guardar les dades amb un historial d'almenys un mes. Fase 1: Treball individual De forma individual, heu de donar resposta a les següents preguntes basant-se en el cas pràctic: 1\.     Què copiar? (Priorització): Quines són les dades més crítiques del servidor? Cal fer còpia dels 10 equips clients? Justifica-ho. 2\.  Periodicitat i Tipus de Còpia: Proposa un calendari bàsic per a la setmana (Diari/Setmanal/Mensual) i quin tipus de còpia aplicaràs (Completa, Diferencial, Incremental) per a les dades crítiques. 3\.     Mitjans i Ubicació: Quin tipus de mitjà de còpia utilitzaries (Discs durs externs, NAS, Cloud, Cintes)? On s'hauria de guardar físicament la còpia més recent (Regla 3-2-1). Fase 2: Treball per parelles Treballant per parelles: 1\.       Discussió i Consens: Comparen les seves respostes individuals (Fase 1). 2\.     Elaboració d'una Proposta Unificada: Heu de consensuar i dissenyar el vostre propi Esquema 3-2-1 de Còpies (3 còpies, 2 mitjans, 1 fora de lloc) basat en els requisits del cas. Element Proposta de la Parella Justificació Dades Crítiques     Periodicitat (BD)     Tipus de Còpia (BD)     Mitjà 1 (Local)     Mitjà 2 (Extern)       Fase 3: Treball en grup 1\.  Debat i Selecció: Cada parella presenta el seu esquema. El grup debat els pros i contres de cada proposta (cost, temps de recuperació, seguretat, simplicitat). 2\.    Disseny de la Política Final: El grup ha de redactar la Política de Còpies de Seguretat Definitiva que presentaran a l'empresa "Muntatges i Serveis Tècnics SL". Document Final (Fase 3\) El grup ha de generar un document amb els següents punts resolts: 1\)      Dades Objecte de Còpia Quines dades es copien i amb quina freqüència (separant Servidor/Clients i crítiques/no crítiques). 2\)      Cronograma Setmanal Detallat Dia Dades (Ex: BD) Tipus de còpia Mitjà Dilluns       Dimarts       ...       Diumenge         3\)      Elecció de Mitjans i Ubicació (Regla 3-2-1) ·         Mitjà 1 (Local): Quin mitjà concret (p. ex., Disc dur USB, NAS) s'utilitza. ·         Mitjà 2 (Extern): Quin mitjà (p. ex., Cloud, LTO) i el proveïdor proposat (p. ex., Azure, Google Cloud, servei local). ·         Ubicació Fora de Lloc: On es guarda la còpia externa (física o lògica) i qui és el responsable de la seva gestió. 4\)      Estratègia de Recuperació (RTO/RPO) Com es garanteix que les dades de Comptabilitat/Clients compleixen amb el requisit de RPO (4 hores) i RTO (4 hores).   Materials i links de suport ●        Moodle 0226 Seguretat Informàtica. RA2.AA3Còpies ●        INCIBE. [Copias de seguridad](https://www.incibe.es/sites/default/files/contenidos/guias/guia-copias-de-seguridad.pdf). Una guía de aproximación para el empresario. ●        Xataka. Backup 3 \- 2 \- 1, el método definitivo para mantener a salvo tus datos. \[YouTube\]. Setembre 2017\. Disponible a: [https://youtu.be/PM\_M4Iz6I4o?si=F7DRyDDTZE3hjWn8](https://youtu.be/PM_M4Iz6I4o?si=F7DRyDDTZE3hjWn8)  |
| :---- | :---- |

**Fase 1: Treball individual**

De forma individual, heu de donar resposta a les següents preguntes basant-se en el cas pràctic:

**1\.     Què copiar? (Priorització): Quines són les dades més crítiques del servidor? Cal fer còpia dels 10 equips clients? Justifica-ho.**

Les dades més importants del servidor són:

1. **Bases de Dades (Comptabilitat i Clients):** Crítiques i d'ús diari (20 GB, canvi constant).

2.  **Carpetes Personals dels Usuaris:** Per a la feina diària (100 GB)

3. **Documents de Projectes:** Plànols, especificacions tècniques (300 GB, creixement moderat).

 


* Lo més important en recuperar és la base de dades de compatibilitat i clients, ja que només tenim 4 h de treball per poder recuperar-les, en canvi, les altres tenim 24 h per poder recuperar-ho.   
    
* Personalment, no crec que faci falta fer la còpia dels 10 equips, ja que els arxius d’aquests 10 equips estan guardats de forma temporal al servidor constantment.

**2\. Periodicitat i Tipus de Còpia: Proposa un calendari bàsic per a la setmana (Diari/Setmanal/Mensual) i quin tipus de còpia aplicaràs (Completa, Diferencial, Incremental) per a les dades crítiques.**

**Bases de Dades (Comptabilitat i Clients):**

Aquestes dades són les més crítiques i tenen canvis constants. Per complir amb el RPO de 4 hores, és necessari fer còpies molt freqüents.

* Una còpia completa setmanal, que serveix com a base per a qualsevol recuperació.

* Còpies incrementals cada 4 hores, ja que només guarden els canvis des de l’última còpia, són molt ràpides i consumeixen poc espai.


La còpia completa s’utilitza per tenir un punt de partida fiable, i les incrementals permeten restaurar la base de dades sense perdre més de 4 hores de treball.

**Documents de Projectes:** Plànols, especificacions tècniques (300 GB, creixement moderat).

El volum és molt gran, però els canvis no són constants al llarg del dia.

* Una còpia completa un cop per setmana, que ens ofereix un punt de restauració estable.

 La còpia diferencial és ideal per a dades grans: només cal restaurar la còpia completa \+ l’última diferencial. Això simplifica molt la recuperació i redueix temps comparat amb múltiples incrementals.

**Carpetes Personals dels Usuaris:** Per a la feina diària (100 GB)

Són dades importants però no tan crítiques com la base de dades. Amb un RPO de 24 hores, n’hi ha prou amb una còpia diària.

* Una còpia completa setmanal, ja seria suficient. 

Les incrementals són eficients per carpetes que canvien sovint, però no són crítiques. A més, restaurar-les és fàcil: còpia completa \+ les incrementals necessàries.

 

**3\.     Mitjans i Ubicació: Quin tipus de mitjà de còpia utilitzaries (Discs durs externs, NAS, Cloud, Cintes)? On s'hauria de guardar físicament la còpia més recent (Regla 3-2-1).**

### **1\) NAS (emmagatzematge en xarxa)**

**Serà el principal sistema de còpies.**

* És ràpid, fiable i permet automatitzar totes les còpies diàries i incrementals.

* Ideal per restauracions ràpides dins l’empresa.

* S’utilitza per guardar totes les còpies recents (incrementals i diferencials).

### 

### 

### **2\) Disc dur extern xifrat**

**Serveix per emportar-se una còpia setmanal fora de l’empresa.**

* Econòmic i fàcil d’utilitzar.

* Permet complir la part “off-site” de la regla 3-2-1.

* Ha d’estar xifrat per evitar pèrdues de dades en cas de robatori.

### **3\) Núvol (Cloud Backup)**

**Opcional però molt recomanable.**

* Ideal per tenir una còpia mensual o setmanal protegida contra desastres (incendi, robatori, fallada total).

* El núvol garanteix redundància i disponibilitat 24/7.

**Fase 2: Treball per parelles**

Treballant per parelles:

1\.       Discussió i Consens: Comparen les seves respostes individuals (Fase 1).

2\.   Elaboració d'una Proposta Unificada: Heu de consensuar i dissenyar el vostre propi Esquema 3-2-1 de Còpies (3 còpies, 2 mitjans, 1 fora de lloc) basat en els requisits del cas.

| Element | Proposta de la Parella | Justificació |
| :---- | :---- | :---- |
| Dades Crítiques | Bases de Dades de Comptabilitat i Clients. | Són dades d’ús constant i tenen un RTO i RPO molt exigent (\< 4 hores). Qualsevol pèrdua afecta directament l’activitat econòmica de l’empresa.  |
| Periodicitat (BD) | Còpia completa setmanal \+ còpies incrementals cada 4 hores. | La completa setmanal serveix com a punt base, mentre que les incrementals cada 4 hores asseguren que no es perdi més de 4 hores de treball. |
| Tipus de Còpia (BD) |  Completa \+ Incremental. | La combinació permet restauracions ràpides i còpies freqüents amb poc consum d’espai i temps. |
| Mitjà 1 (Local) |  NAS intern |  Còpia recent per restauració ràpida  |
| Mitjà 2 (Extern) |  Disc dur extern xifrat o còpia al núvol.  | La regla 3-2-1. Protegeix les dades en cas d’incendi, robatori o desastre físic.  |

**Fase 3: Treball en grup**

1\.  Debat i Selecció: Cada parella presenta el seu esquema. El grup debat els pros i contres de cada proposta (cost, temps de recuperació, seguretat, simplicitat).

### **Cost**

* Les còpies al núvol poden tenir un cost mensual addicional, però tenen un millor nivell de protecció.

### **Temps de Recuperació (RTO)**

* Les propostes que utilitzen un NAS local permeten restauracions molt ràpides, especialment per a la Base de Dades, que té un RTO de menys de 4 hores.

* Les còpies d’un disc extern o un núvol són més lentes, però adequades per situacions de desastre total.

### 

### **Seguretat**

* Les còpies al núvol aporten un nivell de seguretat addicional gràcies a la redundància geogràfica.

***2***.    ***Disseny de la Política Final: El grup ha de redactar la Política de Còpies de Seguretat Definitiva que presentaran a l'empresa "Muntatges i Serveis Tècnics SL".***

### **Dades Crítiques**

Les dades més importants són les Bases de Dades de Comptabilitat i Clients, ja que tenen un ús diari, canvis constants i uns requisits estrictes de recuperació (RTO i RPO \< 4 hores).

### **Periodicitat**

* **Base de Dades:** Còpia completa setmanal i còpies incrementals cada 4 hores.

* **Documents de Projectes:** Còpia completa setmanal i còpia diferencial diària.

* **Carpetes Personals:** Còpia completa setmanal i incremental diària.

**Tipus de Còpia**

* **Completa:** Setmanal, per tenir un punt base estable.

* **Incremental:** Per a la Base de Dades i Carpetes Personals, ja que permeten freqüència elevada amb poc espai.

* **Diferencial:** Per als Documents de Projectes, ideal per volums grans amb restauració ràpida.

**Mitjans Utilitzats (Regla 3-2-1)**

1. **Còpia local  al NAS intern:**  
    Guarda totes les còpies recents (incrementals i diferencials) i permet restauracions ràpides.

2. **Segon mitjà a disc dur extern xifrat:**  
    S’hi desa la còpia completa setmanal. El disc es rota i es guarda en un armari segur.

3. **Còpia externa mitjançant Cloud Backup:**  
    Es fa una còpia mensual Protegeix les dades davant desastres físics com incendi, robatori o fallida total.

**Objectiu de la Política**

Aquesta política garanteix:

* Restauració molt ràpida de les dades més crítiques.

* Compliment complet dels requisits RTO i RPO.

* Protecció davant errors humans, fallades tècniques i desastres.

* Un sistema senzill i sostenible per a una empresa petita.

**Document Final (Fase 3\)**

El grup ha de generar un document amb els següents punts resolts:

1\)      Dades Objecte de Còpia

Quines dades es copien i amb quina freqüència (separant Servidor/Clients i crítiques/no crítiques).

2\)      Cronograma Setmanal Detallat

 

| Dia | Dades | Tipus de còpia | Mitjà |
| ----- | ----- | ----- | ----- |
| **Dilluns** | Bases de dades | Incremental | NAS intern |
| **Dimarts** | Documents de Projectes | Diferencial | NAS intern |
| **Dimecres** | Carpetes personals | Incremental | NAS intern |
| **Dijous** | Bases de dades | Incremental | NAS intern |
| **Divendres** | Documents de Projectes | Diferencial | NAS intern |
| **Dissabte** | Carpetes personals | Incremental | NAS intern |
| **Diumenge** | Bases de dades (completa) \+ Documents de Projectes mensual) | Completa | NAS intern \+ Disc dur extern / Cloud |

**3\)      Elecció de Mitjans i Ubicació (Regla 3-2-1)**

·         Mitjà 1 (Local): Quin mitjà concret (p. ex., Disc dur USB, NAS) s'utilitza.

·         Mitjà 2 (Extern): Quin mitjà (p. ex., Cloud, LTO) i el proveïdor proposat (p. ex., Azure, Google Cloud, servei local).

·         Ubicació Fora de Lloc: On es guarda la còpia externa (física o lògica) i qui és el responsable de la seva gestió.

### **Mitjà 1 (Local)**

* **Dispositiu:** NAS d’emmagatzematge local amb RAID 1\.  
* **Ús:** Còpies incrementals i diferencials ràpides.  
* **Motiu:** Resta físicament a l’empresa, permet recuperació immediata.

### **Mitjà 2 (Extern)**

* **Tipus:** Núvol (Cloud Backup).  
* **Proveïdor recomanat:** Azure Backup o Google Cloud.  
* **Ús:** Còpia completa setmanal i retenció llarg termini.  
* **Motiu:** Fiabilitat, alta disponibilitat i xifratge.

### **Ubicació Fora de Lloc**

* **Localització:** Plataforma Cloud .  
* **Responsable:** Cap de Sistemes de l’empresa.  
* **Funció:** Validar la pujada, integritat i retencions.

  **4\)      Estratègia de Recuperació (RTO/RPO)**

Com es garanteix que les dades de Comptabilitat/Clients compleixen amb el requisit de RPO (4 hores) i RTO (4 hores).

**RPO 4 h:** Es fan còpies incrementals cada 4 hores de la base de dades de Comptabilitat/Clients, així la pèrdua màxima és inferior a 4 hores.

**RTO 4 h:** El NAS permet una restauració ràpida. Si falla, es recupera des del núvol amb la fibra de 600 Mbps, mantenint el temps total per sota de 4 hores**.**

