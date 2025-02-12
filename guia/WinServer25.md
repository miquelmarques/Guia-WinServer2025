# 1.  <a name="A1"></a> **Recordatoris**

0\.1. Nom d’usuari local i contrasenya **PC01\[nom usuari]**

0\.2. Tenir Configurat el DNS apuntant a ell mateix **127.0.0.1**

0\.3. Nom de la màquina fàcil d’utilitzar

0\.4. Rools and features instal·lar **Active Directory Domain Services** i **promote the server**

0\.5. Vigilar no posar OUs d’usuari dins d’equip i viceversa

0\.6. Usuaris i equips dins d’OUS

0\.7. Sharing >>> Advanced Sharing >>> I Posar **domain users** i **full control**

0\.8. Fer captura de resum permisos NFTS

0\.9. Grups globals i security

0\.10. Plantilles tot configurat però deshabilitats i sense contrasenya

0\.11. Per desplegar software ruta de xarxa i solament permisos d’escriptura

0\.12. Desplegar GPOs en OUs o dominis que toquen i grups.

# 2.  <a name="A2"></a>**Configuració VM**
<img alt="Configuracio" src="https://1drv.ms/i/c/baeccccc4c38f786/IQR3HHZC1Fs2T6XliR_r7y_qASVCrl_hzvhCP6X5foZ8XPc?width=1149&height=557">

# 3.  <a name="A3"></a><a name="3"></a>**Instal·lacio VM**

<img alt="Selecció d'idioma en Àngles i seleccio de format hora en Espanyol" src="https://1drv.ms/i/c/baeccccc4c38f786/IQS6I4qdoBJkSpAgmd6WJE_1AYTLSzFOTe8GiXqyTy8A1cs?width=1043&height=843">

<img alt="Selecció de teclat en Espanyol" src="https://1drv.ms/i/c/baeccccc4c38f786/IQQ1LnuUD8oBQpXvDMkS6jgVAbVvb2Yd90vNCgrUzPI_cuo?width=1030&height=853">

<img alt="Instalació Windows Server" src="https://1drv.ms/i/c/baeccccc4c38f786/IQSbgfC8UJj3Trb26uXx-xc1AZdeG74ruEFSyEaKsIQ0rZY?width=1056&height=858">

<img alt="Instalacio de Windows Server Standard Desktop" src="https://1drv.ms/i/c/baeccccc4c38f786/IQTPOR0dJTMqTL30q1vTzz7GAUV4GuVo_r1zRZRoH_wGKEs?width=1042&height=857">

<img alt="Contrassenya Admin" src="https://1drv.ms/i/c/baeccccc4c38f786/IQSUzp4tBcBfSooGODcUUoAAAdXjMVbcNT5kcUJmShzKoPc?width=1031&height=853">

# 4.  <a name="A4"></a>**Configuracio nom i DNS** 
   Server Manager>>> Local Server >>> Computer name>>> Change >>> Computer name: [Afegir nom]
   <img alt="Canvi de nom maquina a dc18" src="https://1drv.ms/i/c/baeccccc4c38f786/IQRVWvH-sTXWQ5cHTmxoiyeoAUUKSOwauwo0i8vUKC_iMlo?width=1021&height=764" >
   (assegurar que el domini i el nom no son el mateix)



# 5.  <a name="A5"></a>**Configuració del servidor de noms**
   Server Manager>>> Clic en el nom d'Ethernet: [nom adaptador]>>> clic esquerra en l'adaptador >>>Propietats>>>Internet Protocol Version 4>>> propietats>>> Posar DNS 127.0.0.1

   <img alt="Nom de domini 127.0.0.1" src="https://1drv.ms/i/c/baeccccc4c38f786/IQREFfUMnfpeRr0yljhr10K7AdKPE98bVpBMR-6VtjKIRnw?width=1017&height=770">

   (Si no ens apuntem a nosaltres el controlador no ens veu. No funciona res)




# 6. <a name="A6"></a>**Domini en nou bosc amb nom soXX.test i nivell funcional 2025**
   Server Manager >>> Manage >>> Add roles and features >>> Next >>> Role-based or feature based installation >>> Instal·lar en el servidor (Next)>>> Active Directory Domain Services >>>Acceptar instal·lar les dependències (Add Features)>>>Next en Features>>> Next en AD DS>>> Confirmation install 

   <img alt="Instal·lació complerta" src="https://1drv.ms/i/c/baeccccc4c38f786/IQSzXKWXDdXMTLR8zCIqVA5UAUVZqE3_mAlCJE8oy0B-Eto?width=360&height=283">

   Un cop instal·lat ens apareix una dependencia que hem de pitjar el botó “promote this server to domain controller”>>>Posar Add a new forest>>> root domain name: [nom]

   <img alt="Creació d'un nou bosc amb el domini so18.test" src="https://1drv.ms/i/c/baeccccc4c38f786/IQSvoVaZ8CpIR4EUkXmzmitsAe99MiFa1WX_aDSBVTj6m0g?width=1020&height=768">

   Next>>>Posar Windows server 2025 i Posar contrasenya

   <img alt="Posar contrasenya de recuperacio de AD DS" src="https://1drv.ms/i/c/baeccccc4c38f786/IQSYHgalLcPQRpjNwSUxA9TNAeXS-pm-Wf-UFSf3NfG2nU0?width=1018&height=762">

   Next (perquè ens diu que no detecta ninguna màquina amb aquell nom)>>>Next >>> I esperar que et doni el nom de NetBios
   <img alt="Configuracio automatica del NetBIOS" src="https://1drv.ms/i/c/baeccccc4c38f786/IQSYVuzQ-5HGQ7kSZcfjM50nAa4iei8Rjm3S4nOOJDfVDYY?width=773&height=564">

   Next

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQS6blAbgxIsSJKrpEya1S-IAfP7XeuXF4cu58DVK-XfoMo?width=1020&height=839" alt="Resum configuracio">

   Li dones a next i comprovarà si la instal·lació és correcta

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSmQobc8kf8R4RWwxXpSQdSAc1tPuwyH0_wR_bTrOJ8-Ko?width=1005&height=693" alt="Comprovacó de carateristiques de la instal·lacio/Configuració">

   Li dones a instal·lar on automàticament es reiniciarà amb tot fet

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSXMtOlXoJgRYKPsEA2aLPoAXmQgu1HReMaeC1VWrzMGfQ?width=765&height=594" alt="Instal·lacio de AD DS">

# 7. <a name="A7"></a>**Resum procés promoció domini i comandes PowerShell**

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQS6blAbgxIsSJKrpEya1S-IAfP7XeuXF4cu58DVK-XfoMo?width=1020&height=839" alt="Resum configuracio">

**Scrypt**

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQMzEUy5pF5Sqi7L5eHR0DkAXbLMRIg74KbkxI8IPMqenM?width=429&height=322" alt="Scrypt d'instal·lacio de AD DS">

# 8. <a name="A8"></a>**Creació de reenviador condicional**

Server Manager >>> DNS >>>Clic esquerre en el Server>>>DNS Manager

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQS62hF_AxdkTa1Dc8Dqg4s7AZVIUCKBhEsGl_z7csHA8mI?width=1031&height=775" alt="Acces a DNS Manager">

 DNS Manager>>> doble clic Server>>>Forwarders

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTc8Hr0M9smSbgr9rIeP8dKATD3eF9l8ZdymbM_-1c1ci8?width=757&height=540" alt="Acces a forwarders">

 Propietats Forwarders>>>Edit>>>Afegir IP del reenviador

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRlZ_CG63bJQLvHDrFXZy8QATmyCKmIEKuKW-HkBse4nuA?width=523&height=450" alt="Afegir el renviador 8.8.8.8 de google">



# 9. <a name="A9"></a>**Canvi horari**
   Time zone: [horari]>>> Change time zone >>> Seleccionar la corresponent i comprovar hora

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQJ7q18aVsiTqWuT-uhYdHbASNlAPkLRJyNIMM5xVrHwtg?width=470&height=488" alt="Configuració de l'hora">

   I per canviar l’hora manualment en el botó de change date and time
# 10. <a name="A10"></a>**Creacio de l’estructura OUs** 
   Active directory Administrative Center>>>Click esquerra >>> New >>> OrganitzationalUnit

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTs37pYQK7lTru6SNj9JE8MAZNRwQVXfrGvZwR12l3y34c?width=586&height=589" alt="Creació de l'OU Mataró">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTxATR0SEEVQokzE7yGLteJAYPg5xi6ks_tjYdzaa56eEw?width=1037&height=307" alt="Creació D'OU usuari i OU equips dins l'OU de mataró"/>


# 11. <a name="A11"></a>**Crear disc compartit**
   **Crear disc a traves de VMbox**

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSjo0uzqpumQKX0DkhAd0fFAQ4sJaYTU0On5cLER1rWwis?width=968&height=813" alt="Creació d'un disc a VirtualBox">

 ## <a name="A11.1"></a>**11.1. Formatar disc**

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTGftfMI2XbQosW3dENjEikAWbOyjxArDmfCmG6CPviuYs?width=839&height=649" alt="Inicar disc en GPT">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSIBwH82u_ARIZa_JhZKIDYASlMpY8kpEDJYi0snYOgz_s?width=878&height=635" alt="Formateig en NFTS del disc">

## <a name="A11.2"></a>**11.2. Crear carpeta i configurar permisos**

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRBVzIxoi48TJxA8mQ2Ew2GAQar1yzccSrxUzkIR18dbrI?width=812&height=570" alt="Creació de la carpeta home">

 ### <a name="A11.2.1"></a>**11.2.1 Permisos de xarxa**
   properties>>>Sharing>>>Advanced Sharing>>>Share this folder>>>Posar un límit d'usuaris a la vegada>>> Permisions>>> afegir “domain users” i posar full control.>>> apply

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSVzXmtN_IFSY0c1Mv68UmpAZIid-RbpVSn7WJ6INYeIfQ?width=828&height=655" alt="Configuració carpeta en Xarxa">

##### <a name="A11.2.2"></a>**11.2.2 Permisos NTFS**
   Properties>>> Security>>>Advanced>>> Disable inheritance>>>pulsa en  **“Convert Inherited permisions into explicit permisions on this object”**
   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSiHyk9hqRjRba8exrst6H7AUuxPKuKsCdZ8XZxJbSetDA?width=767&height=574" alt="Configuració avaçada dels permisos"/>


   Click en el grup >>> Edit>>>Show advanced permisions>>> posar permisos >>> OK>>>apply

   Resultat:

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRAJW3b8kGCRK3ylF18UPWIAexQ-v0GwA0wrIpwFKMsfg4?width=930&height=605" alt="Permisos dels usuaris del domini">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTT076gMOOxSZ82WA-SrP8aAVbBhLvywl3Xq2B09_4YX6c?width=932&height=605" alt="Permisos Creator Owner">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQ-08FLRV6CQY24xr4u61WzAWi7oWCYVyeB-4ms3_pOTmI?width=774&height=556" alt="Resum dels permisos">


Aquest resultat pot variar, ja que pot ser que els administradors no puguin tenir el control això depèn de l’empresa.
# 12. <a name="A12"></a>**Creació de grups**
   Active Directori Users and Computers>>> Sobre carpeta Users>>>Clic dret>>> new>>> group>>> grup
   
   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSavhYoUtNITKOXPLxKVGCRAY5ihVQhFoUuUr1qIbMmnRg?width=1024" alt="Creació d'un grup global">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRCu8j9dEP4Tq5QNldsNZARAZgihc1-Q-7Aej95Xp48dvg?width=758&height=530" alt="Captura resum dels grups">


# 13. <a name="A13"></a>**Creació de plantilles d’usuari**
   Active directory Users and Computers >>> clic esquerra sobre mataro/usuaris >>> clic dret >>> new >>> user

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQOA6qBABDORJ8dAyNpgdwSAZs9X5VDR5jHaNWFdHrD6gc?width=1020&height=844" alt="Creació d'un usuari">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRRF_oM4CcSSpxgRIrkiZjkAYh8N6pGBbBUeX5LN3RCxVI?width=442&height=381" alt="Deshabilitant l'usuari perquè es una plantilla">

   Sobre usuari>>> propieties >>> Profile >>>> connect >>> **[nomequip]\\home\%username%**

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRobx3Jm_0MRKjouWKJkaXCASU2CpcDqI2Cv9I-35A6g2U?width=416&height=576" alt="Afegin el home folder mitjançant xarxa">

   Propierties >>> Member of >>> add >>> [grup]

  
   Per comprovar mira la carpeta home
   
   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTc8gk2lrt3R70TPPwaaVaPAckqOykiCPIhXy4y4XRV_N0?width=786&height=598" alt="Comprovació de la carpeta home">

 Copy user>>> Posar nom  i posar contrassenya i habilitar usuari i posar que canvi la contrassenya

 <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTaK_XwzE7kQKnC3qmZWZPbAdsaiogZSlICasGjo7qVqT0?width=1024" alt="Copia d'usuari plantilla">

<img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQb0eWZOKioR5UG1m5eZmgLAX4RHGmiSmGOcPtjh-iqTs0?width=438&height=388" alt="Creació d'una contrassenya pel l'usuari copìat">

# 14. <a name="A14"></a>**Creació d’un ordinador**

   Active directory Users and Computers >>> clic esquerra sobre mataro/computers>>> clic dret >>> new >>> Computer

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSb0OapHznQR72oPKv6z6rXAYkhXZjUT5Koyjk7BSv339c?width=452&height=418" alt="Afegin un ordinador al AD DS">

   ## <a name="A14.1"></a><a name="_iv7acn4ztc"></a>**14.1. Configurar la máquina Windows 11**
   Settings >>> About>>>> Domain or workgroup >>> Change>>>Posar el nom i el domini>>> I posar contrasenya administrador

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRcNnaV7drsQ44P06Pa0oaSARfABWOH_NSfGZY1IpHRBSE?width=425&height=483" alt="Afegint ordinador al domini">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQLI-tvqov0S5yF75Eze49AAa6iFg7wOZPNu_g-qBVaeEQ?width=463&height=437" alt="Posant el password del administartor per inscriure el PC">

   I toca canviar la IP del DNS 



# <a name="P1"></a>**P1 GPO**
   **RECORDA:** Nom d’usuari local i contrasenya

   ```PC01\[nom usuari]```

   1. **Configurar la Default Policies perquè els usuaris del domini facin servir una contrasenya de 8 caràcters.**

   Group Policy Management>>> Default Domain Controller>>> Clic dret: Edit..>>> Computer Configuration>>> Policies>>>Windows Settings>>> Security Settings>>>Account Policies >>> Password Policies>>>Minimum Password Lenght >>> Posar 8 caracters

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQT79UyOL1CHSYmyya65gftXAfcGlrBmLl2pgbKUkWpMGww?width=1040&height=756" alt="Politica de Contrassenya">


1. ` `**Crear GPO en l'OU de Mataró que afecti els usuaris del grup Dirrecio que tingui 18 caracters i 28 dies de duracio sense complexitat.**

   Group Policy Management>>>mataro>>> Clic dret: New GPO i edit.>>> Computer Configuration>>> Policies>>>Windows Settings>>> Security Settings>>>Account Policies >>> Password Policies>>>Minimum Password Lenght >>> Posar 18 caracters >>> Maximum password age>>> 28 dies

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQFHG8KguuQRJu2_qnSJ05_Aco8_wz8pszLI6gnAppyLFA?width=791&height=575" alt="Resum de politiques">

   Group Policy Management>>>mataro>>> Click>>> Delegation>>> Advanced >>> Treure: Apply this policy als authenticated users >>>Security filtering >>>add:Grup

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQ6kif5_wKwT7z2pakjXGvrAeJmkdlc_AgAzQG5GWwwfts?width=776&height=547" alt="Filtrat de grup">

   2. **Mapejat de xarxa**

   Group Policy Management>>>dc.so18.test>>> Clic dret: New GPO i edit.>>> User Configuration>>>Preferences>>>Windows settings>>>Drive Maps >>> clic dret: New

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQFZQH2HJedT5FwqQCUvmdzAd7NGXHiWm21vl7BBLdr8yA?width=805&height=593" alt="Afgeint carpeta de xarxa">

**3.1. Altres opcions**

Crear un grup d’usuaris que siguin administradors locals de la màquina Windows.

Crear GPO en mataro>>>edit>>>Computer Configuration>>> Prefences>>> Control panel Settings >>>Local Users and Groups>>>Clic dret: All task>add

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQSxd2cC-L7SacjWbQUOdi2AVKIl5jm1Z-ZApnxYErM1Dg?width=439&height=501" alt="Afegint Local Administartors al grup IT">

I el filtratge es queda per tots els usuaris, ja que solament aplicarà en aquell grup d’IT, pel fet que diu que afegeixi el Grup d’IT per

1. **Fer un GPUpdate mitjançant el server**

   Per fer això primer hem d’establir a Domain Controlers la norma que pugui rebre han de tenir l’excepció de rebre remotament dels tallafocs per poder-se fer.

   Group policy Management>>> Domain Controller>>> Edit >>>Computer Configuration>>>Policies>>>Administrative Templates>>> Network>>>Network connections>>>Domain profile
   
   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQR9q4iebaHhQbVCKgL60NewAeZvipZPQdZL8pKLCc3QHhc?width=1116&height=815" alt="Modificant la politica de control remot">

   Pitges editar la norma i poses en habilitat i la IP del Servidor

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRAkDa-pbZYSLhDA2x152O1AR-PbEVjotYmtbse-vhvQoY?width=696&height=646" alt="Modificant la politica de control remot afegint la IP">

   Un cop fet ja pots fer remotament una GPUpdate remotament que simplement fent clic dret en una OU apareix l’opció de fer un Gpupdate.

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQT_cRCLbLFMT4qDYnVpD4tOAQxbrPGnF20HU_tMh7GpbQU?width=899&height=555" alt="Gpupdate Remot">

   En què li dones i automàticament es fa una actualització de GPO i et mostra el resultat.

# <a name="P2"></a>**P2 Desplegament d’aplicacions**
1. **Crear un GPO per desplegar el 7zip de forma assignada als usuaris de gestió.**

   Group Policy Management>>>Mataró>>> Clic dret: New GPO i edit.>>> User configuration>>> Software Settings >>> add.>>> Poses el paquet msi i tria l’opció advanced

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQLc4OE4uXPQZLG0qVQiF5xAZSCUAHSBnzKIbsdYDBGybE?width=1040&height=847" alt="Desplegant 7zip">

   Group Policy Management>>>Mataró>>> GPO >>>User Configuration>>> Security filtering >>add >> Grup>>> eliminar antic grup

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRw3Z_5jWBCQoF-dB0C577QASJz6xzknSU9MHXcDMjhnNY?width=783&height=533" alt="Filtratge per grup">

1. **Crear una GPO per desplegar el Firefox de forma publicada als usuaris de direcció.**

   **S’ha de fer mitjançant una carpeta de xarxa**

   Group Policy Management>>>Mataró>>> Clic dret: New GPO i edit.>>> User configuration>>> Software Settings >>> add i poses la ruta de la carpeta de xarxa>>> Poses el paquet msi i tria l’opció advanced

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQ0PCZNou9BTpvhTZLg5rZlAdJe2-9OkCBw5_sNAiXufEE?width=1038&height=853" alt="Firefox Publicat">

   Group Policy Management>>>mataro>>> GPO >>>User Configuration>>> Security filtering >>add >> Grup>>> eliminar antic grup

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQiuNzsLAhPRbJq-Er9aayIARx8GZKTjUARMo9mEkPRSfI?width=793&height=732" alt="Filtragte per grup">

1. **Com podem crear arxius msi per poder desplegar les nostres aplicacions?**

   Hi ha una sèrie d’eines que permeten agafar un arxiu .exe i convertir-lo en arxiu .msi aquestes eines com MSI wrapper permeten fer la conversió a MSI.

1. **Explicació funcionament** 

   Les GPO filtrades per grup no funcionen si elimines el “Authenticated Users”, per filtrar-ho amb el grup anteriorment seleccionat no funciona, però sí que modificaràs la delegació d'equips i poses que els Authenticathed users solament puguin llegir, però no s'aplica la GPO llavors sí que funciona. 
   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTNvba8BPf7TKJF12EdS0kIAVYwlJr2fDupPgkP8FYZvXE?width=358&height=393" alt="Configuració avançada Scope">

    En la imatge hem de posar aquesta configuració en què l'Authenticated users puguin llegir la GPO, però no s’aplica en ell, i llavors en el scope poses el grup que pertoca i automàticament es posa correctament.
   # <a name="P3"></a>**P3 Perfils**
   RECORDA: Mai posar en el perfil mòbil la redirecció!!! 

1. **Crear dins la unitat de dades, una carpeta que s'anomeni perfils (compartiu-la amb els permisos adients).**

   **Permisos de SMB (xarxa)** 

   Crear carpeta>>> Propietats>>>> Sharing>>> Advanced Sharing
   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRQYWFseJd2QLvsj8_oAOgAAQtxtggTOmw6FMaU6nfFg6g?width=747&height=507" alt="Permisos SMB de perfils">

   **Permisos NTFS**

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTBAj_m0cAoQb7gu3Q0J042AWjrs65NOk1JzL9IyyIc4JM?width=907&height=394" alt="permisos Users">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQKFmTRfyjQSbnSonzURHsFAZEdcrcOiIW_gljmoVygDnw?width=911&height=325" alt="Permisos Creator Owner">

   En aquest cas creo els mateixos permisos que la unitat de xarxa d'home.

1. **Configurar la plantilla de gestio perquè tingui un perfil mòbil.**

   Active Directory User and Computers>>>Anar a la plantilla de gestio>>> Clic dret: propietats>>>Profile>>>Profile path>>> posem la ruta amb %username%

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSwCmW-uU8PTb0xxrFi4QTzAZNNlAHVY98BxzJoY2URnsE?width=770&height=554" alt="Configuració del perfil mobil">

1. **Crear un nou usuari de gestió i mostrar com es crea el seu perfil dins aquesta carpeta.**

   Active Directory User and Computers>>>Anar a la plantilla de gestio>>> Clic dret: copy

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRz4zOs6FtxQpGDpzFARxnIAehaM3-4nT-xqvD5iobEoFI?width=461&height=407" alt="Coipian un usuari per comprovar el perfil">

   Un cop fet l'usuari anem a la màquina client i provem d’accedir amb el nou compte.

    I comprovem que la màquina s’ha creat.

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSfKT0aHybpRZlXXOulwRBzAdcFcL0wzHqdcwQb9bG50_g?width=784&height=433" alt="Comprovació de perfil mobil">

1. **Configurar una GPO que esborra usuaris més antics que X temps**

   GPO>>>Clic dret: edit>>> Computer preferences >>> Administrative Templates >>> System >>> User Profiles >>> Delete user profiles older than…

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQT_1u_C3XHJQbVG2dJPG2m9AaJMu7QE6Fh-kHBfIOp9fYc?width=1028&height=771" alt="GPO de elmimnar perfils antics">

 # <a name="P4"></a>**P4 Redirecció de Carpetes**
1. **Configurar una directiva per tal que els usuaris del grup gestio, encaminin la carpeta Documentos a una carpeta que també anomenarem Documentos, dins la seva carpeta personal en xarxa (compte no la carpeta de perfil).**

   Group Policy Management>>>Situat sobre l'OU de Mataró>>> New GPO>>> Edit>>> User Configuration>>>Windows Settings>>>Folder redirection>>>Documents propierties

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQnG-mTb7MPQrCLf8IhxHTKARt2XcE4EmsFOgh5b42P66Q?width=402&height=466" alt="Redireccio carpeta documents a la home folder">

   I un cop aplicat filtrem la GPO.

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQt1f4Q6QtKTICZeQFa2KCRARdnqg6egX31TEvgWeDnjOs?width=866&height=391" alt="Filtratge per grup">
   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQJNqMawB8xQKCgxuuV62G9AYjwm5bAKVk1LkY1JB39vGw?width=525&height=252" alt=" Filtratge grup a traves de delegation">

1. **Documenteu el correcte funcionament del procés.**

   Un cop ho tenim tot fet fem un **gpupdate /force** en què ens demanarà tancar sessió i tornar a entrar i un cop fet entrem a la carpeta de documents i provem de crear un arxiu i també podem veure que a la carpeta apareix una icona de sincronització.

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQc4c3LMr0GR5qmVoXPhX_cAeBV2HGKG0C9f9i8jAizlxo?width=883&height=611" alt="Comprovacio redirrecio">
# <a name="P5"></a>**P5 Monotritzacio**

1. **Fer una captura de l'estat del servidor: consum CPU,RAM ...**

    Taskmgr>>> Performance>>>CPU

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSt7YrYieG7R4HJAbLdF8W8ARC3T1IioA7Ikx_SW_38CJE?width=767&height=577" alt="Consum CPU">

    Taskmgr>>> Performance>>>RAM

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSdbHFm05w7Tr41Xyuk4TSnAZ79ivr1oA2vIP9--b4j5EU?width=780&height=604" alt="Consum RAM">

1. **Configureu el sistema per auditar els inicis de sessió dels usuaris (tant els bons com els intents fallits)**

   Group Policy Management >>> GPO: Default Domain Policy Control >>> Clic dret: Edit>>>Computer Preferences >>> Windows Settings >>> Security Settings >>> Local Polices >>> Audit Polices 

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQSN5grafDuSL9aFxco6fsOAfG2FSnKz98Tt7DsYxsIFho?width=804&height=577" alt="Politica auditoria d'inici de sessio">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQT_VKesAY5HRra_RcSd5LGGAUSL07xqZ1lj762B2cKuArc?width=600&height=577" alt="Politica auditoria d'inici de sessio 2">

1. **Cercar un log relatiu a Security al Event Viewer. Buscar informació addicional a partir del seu ID.**

<img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSxaoq5mpb-R6jCZHcnRMWTAR1431Kh_PuCG3qmGd-YOAs?width=620&height=444" alt="Propietats del LOG">

1. **Proveu a fer accessos incorrectes al domini i documenteu com queden registrats.**

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQ66FUvqMf5SKCvop8sh1SdAZjDweW9kJtXskQWF9xTshc?width=728&height=501" alt="Event de autenticació fallit">

    Queden enregistrats com audit failure i que  la categoria prove de Kerberos Authentication Service. També queda registrat amb quin nom d’usuari es volia accedir a la maquina i quina maquina ha estat en la que han volgut accedir aquest( IP)

1. **Com visualitzar events en el BPA results** 

   Server Manager >>> BPA Results

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQeOyzYn1tDSKFoCC4xb9vMAXivU2uck9F3inDDFZhNmUk?width=713&height=509" alt="BPA Result del Server Manager">

1. **Monitor de fiabilitat**

   Panell de control>>>Sistema>>> Seguretat i manteniment>>>visualitza els missatges arxivats

1. **Auditar accés a recursos**

   Group Policy Management >>> GPO: Default Domain Policy Control >>> Clic dret: Edit>>>Computer Preferences >>> Windows Settings >>> Security Settings >>> Local Polices >>> Audit Polices 

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQRWzfnKzESRbkXkO7Y02EDAWjQrmg4LH8GEzaz0rWLM1Y?width=911&height=584" alt="Politica d'object access">

    I ara pots veure i pots auditar qui pot accedir a uns arxius qui ho elimina o depen 

   Carpeta ha auditar >>> Clic dret: Propierties >>> Security >>> Advanced >>> Auditing 

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTBFNh5wtxcTrtxko6ToSVUAT3AOQ0G-kQpgZ6BKIpyxzI?width=1010&height=699" alt="Auditoria de la carpeta comuna">

   I seguidament anar a la GPO i configura les propietats avançades de audit.

   Group Policy Management >>> GPO: Default Domain Policy Control >>> Clic dret: Edit>>>Computer Preferences >>> Windows Settings >>> Security Settings >>> Advanced Audit Policy Configuration >>> Audit Policies >>> Object Acces >>> Audit file system i Audit Handle Manipulation

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTxhRUsuYFAQpEG6sR0vAoQASL1LGq5jPD6Yf67DZ-Kj9I?width=856&height=654" alt="Politica de manipulació manual">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRPJ12jWSnTSqTamtfzcduMAUz34Gvkx83fbBHhf6OXUy4?width=831&height=586" alt="Politica de Sistema de fitxers">



# <a name="P6"></a>**P6 Adm. Remota i delegació**

1. **Habilitar RSAT**

   Entrar en la màquina client com a administrador per tal de poder instal·lar el RSAT

   Settings>>>System>>>Optional features >>>View features>>> Buscar:RSAT i afegir RSAT Server Manager i  RSAT Active Directori…

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRLUctEnFMQS5FRBc3XBYhfARP-8GUrr9IgLLWe9qU-7b8?width=714&height=438" alt="Instal·lació del servei RSAT">

1. **Afegir servidor**

   Server Manager>>>Add other servers to manage>>>Buscar el servidor

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRoEXtY9nLeQbARkJsy57O2Af-oGjmwH8c0Itf4S_UgC8E?width=717&height=425" alt="Afegir un servidor del domini">

1. **Afegir un grup/usuari en què pugui delegar el servidor**

   Servidor>>>Active Directory Users and Computers>>>Clic dret (Sobre la OU): Delegate Control

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQToLlAeUMMqTJyTsJt48I3CAS8xzguPc4ZZvURwtAb25TM?width=793&height=536" alt="Delegació de Control a IT">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSA7_g_ILmIT40StGvCeQiNAZT6Pd4YM8b_SLyY1EFP0H4?width=776&height=547" alt="Elements que delega IT">

 ## <a name="AA6"></a>**Activitat: AA6 Delegació**

1. **Crea un usuari dins la OU usuaris anomenat adminOU.** 

   Active Directory User and Computers>>> Clic dret(sobre l’OU)New >>> User

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQR6BU_GUlDWRaKc2LwUxle3AQZ4KDOB6UqDiw5sdqmVs5w?width=808&height=555" alt="Creació d'un usuari">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQR6BU_GUlDWRaKc2LwUxle3AQZ4KDOB6UqDiw5sdqmVs5w?width=808&height=555" alt="Captura de usuaris">


1. **Delega el control de l'OU Mataró per aquest usuari amb les següents regles:**
- **Pot reiniciar els passwords dels usuaris de l'OU.**
- **Pot modificar la pertinença a grups.**

Active Directory Users and Computers>>>Clic dret (Sobre la OU): Delegate Control>>> Usuari>>> I posar els seguents punts

<img src="https://1drv.ms/i/c/baeccccc4c38f786/IQQOb1ARtlI4QKMwtkEfVCLeAbxytF1fAUY8oWpheR45oSs?width=783&height=541" alt="Opcions que realitza el AdminOU">

1. **Documenta com aquest usuari no pot crear un usuari nou, però sí que pot fer les accions esmentades sobre un usuari existent.**

   Per comprovar-ho anem a la màquina client i entrem amb l'usuari i contrasenya del adminOU.

   **Comprovar crear usuari**

    Server Manager>>>Active Directory Users and Computers >>> OU de mataró

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQRwVy_iVu_ETpuT0sPsGn_6AaGnlWGpspY8ipdMBkduoJM?width=841&height=578" alt="Coprovació d'elements que no pot realitzar">   

    En aquests de voler crear un usuari ho tenim deshabilitat, per tant, no surt ni l’opció de crear-ho i tampoc surt l’opció de crear un grup o una OU.

    **Canviar contrasenya i canviar pertinença de grup**

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQSkfrtuetqdTYnyH8_CLVOfASE7FzAlS_IxDqDxrFaOlZ4?width=1027&height=819" alt="Canviant contrassenya desde AdminOU">

   <img src="https://1drv.ms/i/c/baeccccc4c38f786/IQTKw0OSHE3hToAVM5jtQFgZAdK1SosS7YzDfuopWiYr_YU?width=1028&height=882" alt="Canvi de pertinenca de grup">

    En aquest cas sí que ho podem realitzar correctament ja que tenim prou delegació per fer-ho. I passa el mateix amb la pertinenca a un grup



##

# Guia Windows Server 2025 © 2025 by Miquel Marquès Bravo is licensed under [CC BY-NC-ND 4.0 ](https://creativecommons.org/licenses/by-nc-nd/4.0/?ref=chooser-v1)




