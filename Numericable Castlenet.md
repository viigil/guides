

## Vue d'ensemble

<!-- 

TODO: deactivate guest network

TODO: Page on Reset 
TODO: Page on hiding SSID


Optionally: deactivate interface?
What does "WAN Blocking" (Advanced > Options) do? fully block incoming packets? (check with remote web interface enabled, port forwarding) 

-->

Si vous êtes sur de n'avoir changé aucun paramètre sur votre box ou après un reset (Effectuer un reset est grandement conseillé dans la mesure du possible):

* Changer votre SSID ("Numericable-0000" le nom publique de votre réseau Wi-Fi)
* Passer du chiffrement Wi-Fi WEP par default au chiffrement WPA2
* Utiliser une Pre Shared Key (mot de passe Wi-Fi) forte
* Changer le mot de passe par default de l'interface routeur

Si vous n'effectuez pas de reset, soyez sur, **en plus** des etapes ci-dessus:

* Que l'acces WAN a l'interface routeur est desactive
* Que WPS est desactive


Meme pas peur? C'est parti!


## Connection a l'interface

L'interface de votre box est disponible a l'addresse [192.168.0.1](http://192.168.0.1) (Clickez ce lien ou entrez l'addresse dans votre navigateur manuellement)


<iframe data-interface >
  "src": "castlenet/login.html",
  "width": 775
</iframe>


#### Entrez le nom d'utilisateur et le mot de passe:

* Nom d'utilisateur: <b data-interface-selector="[name=loginUsername]" data-layout="push" data-color="ctyellow">admin</b>
* Mot de passe: <b data-interface-selector="[name=loginPassword]" data-layout="push" data-color="ctorange">password</b>

(A changer imperativement dans la rubrique *Changement des identifiants de l'interface* ci-dessous, si ce n'est deja fait)


## Changer votre SSID
Le SSID est public. Toute personne dans la vicinite de votre habitation peut facilement l'obtenir. Évitez donc toute information personnelle, comme le nom de votre fournisseur Internet! Ce dernier est egalement source de confusion en ville ou l'on trouve une forte concentration de reseau wifi. Votre SSID est en revanche moins critique que votre PSK (mot de passe) et ne premet pas par lui meme la connection a votre reseau, choissez donc quelquechose de familier comme par exemple l'espece des arbres dans votre rue.

> Notez qu'une autre information publique, votre BSSID, continuera a renseigner le nom de votre fournisseur Internet. Si vous voulez aller plus loin, vous devrez donc desactive le Wi-Fi de votre box et utilisez, au besoin, un autre routeur Wi-Fi.


<!--Some company want to advertise their network with SSID-->

<iframe data-interface >
  "src": "castlenet/wireless_basic.html",
  "height": 450,
  "width": 775
</iframe>



#### Changement du SSID


 * Menu <b data-interface-selector="[src='./assets/btn_wireless_y.gif']" data-color="ctyellow">Sans fil</b>
 * Saisissez <b data-interface-selector="[name=ServiceSetIdentifier]" data-layout="push" data-color="ctgreen">votre SSID</b>
 * Cliquez <b data-interface-selector="[value=Appliquer]" data-layout="push" data-color="ctorange">Appliquer</b>
 
Notez que l'option *Open* dans *Type du reseau* n'a rien a voir avec le chiffrement. C'est une maladresse constructeur. Il s'agit en fait d'emettre ou non (cacher) votre SSID. En général, nous déconseillons de cacher votre SSID: cela n'apporte qu'un semblant de sécurité au detrimant de la simplicité. **L'option** ***Type de reseau "Open"*** **est sécurisée, et ne fait pas de votre réseau un réseau Ouvert.**


## Chiffrement fort avec WPA2

Le chiffrement WEP est obsolete depuis plus de 10 ans et ne devrait jamais etre utilise de nos jour. Ordinateurs et autres appareils mobiles supportent tous WPA depuis des annees. Pas d'excuses.

<iframe data-interface >
  "src": "castlenet/wireless_security.html",
  "height": 450,
  "fitElsX": "td:has(> [name=WpaPreSharedKey])"
</iframe>



#### Choisir le chiffrement WPA2

 * Sous-menu <b data-interface-selector="[src='./assets/btn_security_y_g.gif']" data-color="ctorange">Securite</b>
 * Choisir *Active* pour <b data-interface-selector="[name=Wpa2PskAuth]" data-layout="push" data-color="ctviolet">WPA2-PSK</b> (et pour aucun autre chiffrement)
 * Choisir *AES* pour <b data-interface-selector="[name=WpaEncryption]" data-layout="push" data-color="ctgreen">Chiffrement WPA/WPA2</b>
 
*N'oubliez pas de valider vos changement ci-dessous! (ou cliquez maintenant sur* ***Appliquer***
 

 
 
 
## Pre Shared Key forte

Viigil recommendent les **passphrases** pour tout mot de passe que vous devez retenir ou tapper regulierement. Votre PSK (Mot de passe wifi) sera rarement utilisee, par exemple lorsque vous avez un nouvelle appareils qui n'est pas encore connecte a votre reseau Wi-Fi, et WPA, contrairement au chiffrement WEP (et autre site internet, qui peuvent parfois avoir des problemes avec les espaces egalement) accepte des PSK longue (63 characteres). N'hesitez donc pas a choisir une passphrase plus longue ou utilisez un mot de passe aleatoire conserve dans un coffre fort numerique.

#### Passphrase VS Mot de passe aleatoire
Les passephrase sont plus facile a retenir, et souvent aussi rapide a entrer car elle contient des mots qui ont un sens pour vous (mais pas forcement des mots du dictionnaire, c'est d'ailleurs toujours mieux s'il ne s'y trouvent pas) contrairement aux mots de passe aleatoire ou beaucoup de gens hesitent/dechiffrent/se trompent a chaque charactere. Leur longueurs les rendent exponentiellement plus difficile a casser et leur ponctuations et majuscules permet d'ajouter de l'entropie naturellement (N'hesitez pas a en mettre, pensez egalement aux chiffres).
 
 Les passphrase sont donc souvent plus surs **et** plus faciles.
 
#### Choisir sa passphrase
Ne vous compliquer pas necessairement  la vie, surtout si vous utilisez beaucoup de passphrases. **La plus part des passphrase de plus de 3 mots devrait faire l'affaire.** Neanmoins plus vous respecterez ces quelque points, plus votre passphrase sera forte:

  * Absolu minimum de **3 mots** *et* **10 characteres** au total
  * Au moins une majuscule *et* une ponctuation *et* un chiffre.
  * N'hesitez pas a utilisez des "vocabulaire personnel", moins les mots sont courrant mieux c'est, mais **pas** de noms personnels (enfants, **animaux de compagnie** etc...)
  * Moins la phrase a de sens (commun) mieux c'est
  * Vous avez le droit de faire des f0tes d'orthographe! Plus la phrase a de fautes de grammaires et d'orthographe mieux c'est. Sans oublier de garder une phrase simple a retenir.

<!-- See http://www.bu.edu/infosec/howtos/how-to-choose-a-password/ for article on passwords 
Have another article with a calculator of cracking time and exponential plots-->


#### Exemples 

Soyez creatif! N'utilisez surtout pas les exemples ci-dessous! (Ou tout autre texte qu'un attaquant pourrait s'attendre a etre utilise)

Bon: "L<b class="ctgreen">'ecureil</b> fait <b class="ctgreen">10</b> brasses<b class="ctgreen">. D</b>ans le <b class="ctgreen">chocolat chaud!</b>"
Moins bon: "La <b class="ctred">loutre</b> fait <b class="ctred">dix</b> brasses dans la <b class="ctred">riviere</b>"

Bon: "<b class="ctgreen">1 velo</b> grimpe<b class="ctgreen">,</b> dans le Grand Cedre." 
Moins bon: "<b class="ctred">Marion</b> grimpe dans le Grand Cedre."



<!-- data-height="1050" -->
<iframe data-interface >
  "src": "castlenet/wireless_security.html",
  "fitElsX": "td:has(> [name=WpaPreSharedKey])",
  "scroll": 320
</iframe>



#### Changez votre passphrase

* Cliquez <b data-interface-selector="[name=ShowWpaKey]" data-layout="push" data-color="ctgreen">afficher la clé</b>
* Saisissez votre passphrase dans <b data-interface-selector="[name=WpaPreSharedKey]" data-layout="push" data-color="ctorange">Cle pre-partage WPA</b>
* **Verifiez que votre cle correspond bien a celle que vous avez choisie.** Vous allez devoir l'utiliser maintenant pour reconnecter vos appareils.
* Cliquez <b data-interface-selector="[value=Appliquer]" data-layout="push" data-color="ctyellow">Appliquer</b>




## Changement des identifiants de l'interface
Le modem Castlenet va a l'encontre de toute les bases de la sécurité en ayant des identifiants par défaut qui sont de plus **les mêmes chez chaque abonné**.

Choisissez une passphrase de la meme maniere que pour votre PSK dans la rubrique *Pre Shared Key Forte*. Vous pouvez également utiliser un coffre fort numérique pour stocker et générer aléatoirement ce genre de mot de passe que vous utilisez peu souvent.

<iframe data-interface >
  "src": "castlenet/status_security.html",
  "width": 680,
  "height": 400
</iframe>

#### Etape 1: Se rendre sur la page *Sécurité* du modem

 * Menu <b data-interface-selector="[src='./assets/btn_status_y.gif']" data-color="ctyellow">Status</b>
 * Sous-menu <b data-interface-selector="[src='./assets/btn_security_y_g.gif']" data-color="ctorange">Sécurité</b>
 

<iframe data-interface >
  "src": "castlenet/status_security.html",
  "width": 680,
  "height": 450
</iframe>


#### Etape 2: Changer le mot de passe de l'interface
  * utilisateur: <b data-interface-selector="[name=UserId]" data-layout="push" data-color="ctyellow">admin</b>
  * Entrez votre mot de passe dans <b data-interface-selector="[name=Password]" data-layout="push" data-color="ctorange">Nouveau mot de passe</b> **et** <b data-interface-selector="[name=PasswordReEnter]" data-layout="push" data-color="ctorange">Re-entrer le nouveau mot de passe</b>
  * Mot de passe actuel de l'utilisateur: <b data-interface-selector="[name=OldPassword]" data-layout="push" data-color="ctviolet">password</b>
  
 *N'oubliez pas de valider vos changement ci-dessous! (ou cliquez maintenant sur* ***Appliquer***
 
 
## Désactiver l’accès WAN a l'interface

*L’accès WAN et WPS sont désactivé par défaut. Vérifiez: on est jamais trop prudent!*

L'access par WAN vous permet d'acceder a l'interface de votre modem en dehors de chez vous. C'est une porte ouverte aux personnes mal intentionnées, surtout si par malheur vous avez les identifiants par défaut... A désactiver absolument sauf si vous en avez besoin dans un cas particulier (très rare).
 

<iframe data-interface >
  "src": "castlenet/status_security.html",
  "width": 680
</iframe>

#### Désactivation de l’accès WAN

 * Décochez <b data-interface-selector="[name=RemoteManagement]" data-color="ctorange">Controle a distance de la configuration du modem</b>
 * Cliquez <b data-interface-selector="[value=Appliquer]" data-color="ctyellow">Appliquer</b>
 
 
 
## Désactiver WPS

WPS permet de se connecter un nouvel appareil (ou un appareil ayant "oublier" les parametres Wi-Fi) avec un simple PIN (code) ou un appuyant un boutton reserver a cet usage sur le routeur.

La sécurité du mode PIN a toujours été casse depuis le début de sont existence avec des attaques pratiques des 2011.

Le mode *boutton* n'a pas les meme probleme mais il est preferable de se connecter avec votre passphrase. De plus, la plupart des routeurs ne dissocie malheureusement pas les deux modes, obligeant l'utilisateur a se passer de WPS.




#### Etape 1: Se rendre sur la page des options de Sécurité Wi-Fi

 * Menu <b class="darkorange">.</b>
 * Sous-menu <b class="darkyellow">...</b>
 







#### Etape 2: Choisir le chiffrement WPA2

 * ... Choisir *Active* pour <b class="violet">WPA2-PSK</b> (et pour aucun autre chiffrement)
 * ... Choisir *Active* pour <b class="darkgreen">Chiffrement WPA/WPA2</b>
