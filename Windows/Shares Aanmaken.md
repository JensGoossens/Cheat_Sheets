#Aanmaken van een share

1) Allereerst gaan we in elke globale groep die bestaat in de OU's een domein lokale groep aanmaken die begint met een *T_*. Dus de groep Administratie krijgt zo een extra groep T_Administratie. Dan moet je de originele groep lid maken van de domein lokale groep.

2) Nu kunnen we op de gewenste harde schijf de gewenste shares aanmaken.

3) In het `File and Storage Services`-scherm kunnen we nu onder het tabblad `shares` van de aangemaakte mappen een share maken. Dit doen we door bij `tasks` het onderdeel `new share` te selecteren en de stappen daarna in te vullen.

4) één van deze stappen is bij sharing en security de juiste permissies instellen: Bij `security` verwijderen we alles buiten de `CREATOR OWNER`, `SYSTEM` en `Administrator` en voegen we `T_JuisteGroep` toe. Bij `sharing` voegen we deze ook toe en laten we de `Administrators` staan. 

5) Nu moeten we ervoor zorgen dat er een automatische mapping komt voor de gebruikers. Dit gebeurt a.d.h.v. GPO filters. In het `Group Policy Management`-scherm en maken we een GPO-filter aan voor de gewenste groep (bv. AdministratieGPOfilter). We halen hier het tabblad `delegeation` voor ons en we verwijderen de `authenticated users` en we voegen er in dit geval de groep `administratie` aan toe met permissie `allow: read en allow: apply group policy`. 

6) Nu wordt het effectieve drive mappen ingesteld. We zitten nog steeds in hetzelfde scherm en we gaan de editor openen en het scherm als volgt uitschuiven: `User configuration` --> `Preferences` --> `Windows Settings`--> `Drive maps`
