# 📁 T03 — DRP: Pla de Recuperació davant Desastres  
### *Imatges del Sistema — Creació i Restauració*  
**Mòdul:** Seguretat Informàtica  
**Objectiu:** Avaluar eines de creació d’imatges del sistema i elaborar una guia operativa per assegurar la continuïtat del negoci.



## 🏢 Introducció al cas  
El client, satisfet amb la recuperació i fortificació d’un portàtil en una tasca anterior, ha encarregat la creació del seu **Pla de Contingència i Continuïtat del Negoci**. Dins d’aquest document, cal desplegar un **Pla de Recuperació davant Desastres (DRP)** que garanteixi la restauració ràpida de dades, equips i programari crític.

Un element clau del DRP és assegurar que els treballadors puguin tenir **equips funcionals de forma immediata** en cas de robatori, fallada o avaria. Per això, es requereixen **imatges de restauració del sistema** que permetin reinstal·lar una màquina completa sense haver de repetir el procés manual d’instal·lar, configurar i personalitzar aplicacions.

El client utilitza **Zorin OS 18** en tots els seus equips, amb configuracions i aplicacions específiques.


# 🧩 FASE 1 — Anàlisi i justificació de la solució tècnica

En aquesta fase cal investigar eines capaces de:

- Crear imatges completes d’un disc
- Permetre restauracions ràpides i fiables
- Mantenir configuracions, aplicacions i personalització
- Ser compatibles amb GNU/Linux

S’han d’analitzar **dues eines comercials** i **dues eines de comunitat**, comparant:

- Característiques principals  
- Fiabilitat i facilitat d’ús  
- Compatibilitat amb Linux  
- Llicències i preu  
- Escalabilitat  
- Adaptació al cas del client  

Finalment, cal **proposar la millor opció** i justificar-la basant-se en els criteris analitzats.



# 🧩 FASE 2 — Guia d'Ús Tècnica (Manual Operatiu)

Per preparar la prova de concepte, el client proporciona una màquina base (simulada amb una OVA).  
A partir d’aquesta màquina, cal:

### 🎯 Objectius
- Crear una **imatge completa del sistema**
- Restaurar aquesta imatge en una **màquina idèntica**, però sense sistema operatiu

La guia ha de servir perquè el personal tècnic pugui realitzar tot el procés sense dubtes.  
Per tant, cal documentar:

- Passos detallats  
- Captures d’imatge rellevants  
- Configuració abans i després  
- Notes i possibles problemes habituals  

### 🛠 Eina utilitzada: **Rescuezilla**
Com que encara no se sap quina solució aprovarà el client, per a la prova de concepte s’utilitza **Rescuezilla**, una eina gratuïta i senzilla per crear i restaurar imatges de sistemes basats en Linux.

### 📌 Procediments a documentar
1. Arrencar la VM amb Rescuezilla  
2. Crear la imatge del disc complet  
3. Guardar la imatge en un mitjà extern (disc, carpeta, etc.)  
4. Crear una segona VM idèntica sense SO  
5. Arrencar-la amb Rescuezilla  
6. Restaurar la imatge creada  
7. Verificar que la restauració és completa i funcional  

> La guia ha de ser precisa, clara i incloure totes les imatges necessàries.



# 📚 Recursos  
- **INCIBE — Pla de recuperació davant desastres**  
  https://www.incibe.es/empresas/blog/tienes-tu-plan-recuperacion-desastres  
- **Rescuezilla (oficial)**  
  Documentació i descàrregues disponibles a la seva web oficial



> ✨ *Tasca enfocada a entendre, comparar i implementar solucions de creació d’imatges del sistema com a part essencial d’un Pla de Recuperació davant Desastres professional.*

