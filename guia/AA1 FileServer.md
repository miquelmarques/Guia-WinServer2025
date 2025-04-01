
# <a name="FilServer">**AA1 FILE SERVER**
#
# <a name="AA1"></a>Exercici 1: Compartició a traves del sistema d'arxius

- **Crea al server un directori anomenat shared al segon disc i dona-li permisos per lectura i executar els usuaris del domini i els per defecte pel grup Administrators.**

  En aquest punt creem la carpeta en el segon disc i comencem a posar els permisos de xarxa que en aquest cas col·loco que tots els del domini puguin tenir control total perquè seguidament en els permisos NTFS filtratge més exacte.
  <img alt="Permisos SMB carpeta shared" src="images/fileServer/image001.png">

  Un cop feta la compartició anem als permisos avançats i allà posem els permisos que pertoquen com que els usuaris del domini tenen permisos de lectura i execució i els administradors els que tenen per defecte que és el control total

<img alt="Permisos NTFS carpeta shared" src="images/fileServer/image003.png">

- **Mostra els permisos locals i compartits des de l'opció de Seguretat Avançada.**

  **Permisos Locals/ NTFS**

<img alt="Permisos NTFS carpeta shared" src="images/fileServer/image005.png">

 
  **Permisos Xarxa/SMB**

<img alt="Permisos SMB carpeta shared" src="images/fileServer/image007.png">



- **Comprova que es pot accedir a aquest directori des del W10 client i què pot fer cada tipus d'usuari (normal o administrador), des de l'Explorador d'arxius.**

  **Usuari del domini normal:**

<img alt="Comprovacío usuari normal" src="images/fileServer/image009.png">

  A qui si forcem la creació d’un arxiu ens avisa que no tenim permisos per poder crear arxius.

  **Usuari Administrador:**

<img alt="Comprovació usuari Administrator" src="images/fileServer/image011.png">

  En el cas de l'administrador en tenir permisos de control total pot crear arxius canviar la propietat, atributs i altres.


# <a name="AA2"></a>Exercici 2:

- **Instal·la el rol File and Storage Services Manager al Server.**

  En aquest punt el que fem és instal·lar el file and Storage Manager en què en el nostre cas ja ho tenim instal·lat. 

<img alt="Afgeir el rol de fssrm" src="images/fileServer/image013.png">

- **Crea al server un directori anomenat fssmshare, comparteix-lo amb FSSM i dona-li permisos per accedir-hi i executar els usuaris del domini.**

  En Aquest punt hem de crear un SMB Share - Quick que significa que fem una compartició bàsica de SMB en què posem els permisos locals els mateixos la ubicació de la carpeta.

<img alt="Ubicació en el disc" src="images/fileServer/image015.png">


  En aquest punt posem on es crearà la carpeta i a quin disc.

<img alt="Ubicació carpeta i nom" src="images/fileServer/image017.png">


  En aquest posem el nom de la carpeta i la ruta de xarxa

<img alt="Permisos NFTS carpeta fssmshared" src="images/fileServer/image019.png">

  Posem els permisos de la carpeta tan locals com en xarxa.

<img alt="Resum de la carpeta de xarxa" src="images/fileServer/image021.png">


- **Comprova que es pot accedir a aquest directori des del W10 client assignant manualment una unitat X: i què pot fer cada tipus d'usuari.**

  En el servidor d d’arxiu dli dones clic dret en l’apartat de Network i li dones a Map Network drive ..

<img alt="Com inserrir un Network Drive" src="images/fileServer/image023.png">


  En aquest punt posem la lletra que ocuparà el disc de xarxa i la ruta per accedir-hi.

<img alt="Connectant carpeta com ha Network Drive" src="images/fileServer/image025.png">

<img alt="Resultat connexió" src="images/fileServer/image027.png">

  **Usuari normal**

<img alt="Comprovació Usuari Normal" src="images/fileServer/image029.png">

  **Usuari Administrador**

<img alt="Comprovació Administrador" src="images/fileServer/image031.png">

# <a name="AA3"></a>Exercici 3:

- **Crea al server un directori anomenat pshellshare, comparteix-lo amb PowerShell i dona-li permisos per accedir-hi a un grup determinat i a un altre no.**

  En aquest punt el primer que fem és crear una carpeta anomenada pwshell i després posem la comanda de New-SmbShare en el fet que posem la ruta el nom de com es mostrara en la xarxa qui té full accés que aquest cas el equipit i el altre que és el grup de finances no té accés.


<img alt="Creació de la carpeta i configuració via PowerShell" src="images/fileServer/image033.png">

- **Crea al server una GPO que permeti als usuaris del client accedir-hi directament com una unitat de xarxa.**

<img alt="Creació de la GPO" src="images/fileServer/image035.png">

  En aquest punt creo la GPO en què s’aplica a l’OU on està els equips i usuaris i seguidament editar-ho la GPO i vaig en l'apartat de “Drive Maps” i editar-ho la configuració per posar una ruta cap ala carpeta i la lletra.

- Comprova que un usuari pot accedir a aquest directori des del W10 client i que un altre no.

  **Usuari de equipit (Grup1)**

<img alt="Resultat grup equipit" src="images/fileServer/image037.png">

  **Usuari del grup finances (Grup 2)**

<img alt="Resultat grup finances" src="images/fileServer/image039.png">


# <a name="AA4"></a>Exercici 4: Carpeta oculta compartida

- **Crea una nova carpeta i anomena-la hidden. Comparteix-la amb els permisos per defecte (Domain Users lectura i Administrators Full Control), però usant com a nom compartit hidden$. Posa algun arxiu a dins. Comprova des del client com la carpeta no es veu si des de l'explorador d'arxius mirem els recursos compartits del servidor.**

  En aquest punt modifiquem el nom que té el disc en la màquina del servidor afegint-li solament el símbol del dòlar en el final.

<img alt="Creació i configuració carpeta $hidden" src="images/fileServer/image041.png">

  I fent la comprovació no apareix si no posem la ruta completa

<img alt="Resultat carpeta $hidden" src="images/fileServer/image043.png">

- **Comprova ara, com si poses la ruta amb el nom, accedeixes a dins la carpeta.**

<img alt="Resultat carpeta $hidden" src="images/fileServer/image045.png">

En aquest punt poses la ruta per accedir-hi i es mostra mentre que si faig un llistat de dc18 no es mostra.
