

## Vue d'ensemble

<!-- 

TODO: deactivate guest network

TODO: Page on Reset 
TODO: Page on hiding SSID
TODO: Page on strong password / safes / yubikey


Optionally: deactivate interface?
What does "WAN Blocking" (Advanced | Options) do? fully block incoming packets? (check with remote web interface enabled, port forwarding) 

-->

Si vous êtes sûr de n'avoir changé aucun paramètre sur votre box ou après un reset (Effectuer un reset est grandement conseillé dans la mesure du possible):

* Changez votre SSID (*Numericable-0000* le *nom* public de votre réseau Wi-Fi)
* Passez du chiffrement Wi-Fi WEP par défaut au chiffrement WPA2
* Utilisez une Pre Shared Key (mot de passe Wi-Fi) forte
* Changez le mot de passe par défaut de l'interface routeur

Si vous n'effectuez pas de reset, soyez sûr, **en plus** des étapes ci-dessus:

* Que l’accès WAN à l'interface routeur est désactivé
* Que WPS est désactivé



## Connexion à l'interface

L'interface de votre box est disponible à l’adresse [192.168.0.1](http://192.168.0.1) (cliquez ce lien ou entrez l’adresse dans votre navigateur manuellement)


<iframe data-interface >
  "src": "castlenet/login.html",
  "width": 775,
  "height": 600
</iframe>


#### Entrez le nom d'utilisateur et le mot de passe:

* Nom d'utilisateur: <b data-interface-selector="[name=loginUsername]" data-layout="push" data-color="ctyellow">admin</b>
* Mot de passe: <b data-interface-selector="[name=loginPassword]" data-layout="push" data-color="ctorange">password</b>

(À changer impérativement dans la rubrique *Changement des identifiants de l'interface* ci-dessous, si ce n'est déjà fait)


## Changer votre SSID
Le SSID est public. Toute personne à proximité de votre habitation peut facilement l'obtenir. Évitez donc toute information personnelle, comme le nom de votre fournisseur Internet! Ce dernier est également source de confusion en ville où l'on trouve une forte concentration de réseau Wi-Fi. Votre SSID est en revanche moins critique que votre PSK (mot de passe) et ne permet pas par lui--même la connexion à votre réseau, choisissez donc quelque chose de familier comme par exemple l’espèce des arbres de votre rue.

> Notez qu'une autre information publique, votre BSSID, continuera à renseigner le nom de votre fournisseur Internet. Si vous voulez aller plus loin, vous devrez donc désactiver le Wi-Fi de votre box et utiliser, au besoin, un autre routeur Wi-Fi.


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
 
Notez que l'option *Open* dans *Type du reseau* n'a rien à voir avec le chiffrement. C'est une maladresse constructeur. Il s'agit en fait d’émettre ou non (et donc de cacher) votre SSID. En général, nous déconseillons de cacher votre SSID: cela n'apporte qu'un semblant de sécurité au détriment de la simplicité. **L'option** ***Type de reseau "Open"*** **est sécurisée, et ne fait pas de votre réseau un réseau Ouvert.**


## Chiffrement fort avec WPA2

Le chiffrement WEP est obsolète depuis plus de 10 ans et ne devrait jamais être utilisé de nos jours. Ordinateurs et autres appareils mobiles supportent tous WPA depuis des années. Pas d'excuses.

<iframe data-interface >
  "src": "castlenet/wireless_security.html",
  "height": 450,
  "fitElsX": "td:has(> [name=WpaPreSharedKey])"
</iframe>



#### Choisir le chiffrement WPA2

 * Sous-menu <b data-interface-selector="[src='./assets/btn_security_y_g.gif']" data-color="ctorange">Sécurité</b>
 * Choisissez *Activé* pour <b data-interface-selector="[name=Wpa2PskAuth]" data-layout="push" data-color="ctviolet">WPA2-PSK</b> (et pour aucun autre chiffrement)
 * Choisissez *AES* pour <b data-interface-selector="[name=WpaEncryption]" data-layout="push" data-color="ctgreen">Chiffrement WPA/WPA2</b>
 
*N'oubliez pas, ci-dessous, de valider vos changements! (ou cliquez une première fois sur* ***Appliquer*** *dès maintenant)*
 

 
 
 
## Pre Shared Key forte

Viigil recommande les **passphrases** pour tout mot de passe que vous devez retenir ou taper régulièrement. Votre PSK (Mot de passe Wi-Fi) sera rarement utilisée---par exemple lorsque vous avez un nouvel appareil qui n'est pas encore connecté à votre réseau Wi-Fi, et WPA, contrairement au chiffrement WEP (et autres sites Internet qui peuvent parfois avoir des problèmes avec les espaces) accepte des PSK longues (jusqu’à 63 caractères). N’hésitez donc pas à choisir une passphrase plus longue ou utilisez un mot de passe aléatoire conservé dans un coffre--fort numérique.

#### Passphrase VS Mot de passe aléatoire
Les passephrases sont plus faciles à retenir, et souvent même plus rapide à entrer car elles contiennent des mots qui ont un sens pour vous (mais pas forcément  des mots du dictionnaire, c'est d'ailleurs toujours mieux s'ils ne s'y trouvent pas) contrairement aux mots de passe aléatoires avec lesquels beaucoup de gens hésitent, déchiffrent et se trompent à chaque caractère. Leurs longueurs les rendent exponentiellement plus difficiles à casser et leur ponctuation et majuscules permettent d'ajouter de l'entropie naturellement (N’hésitez pas à en mettre, pensez également aux chiffres).
 
 Les passphrases sont donc souvent plus sures **et** plus faciles.
 
#### Choisir sa passphrase
Ne vous compliquez pas nécessairement  la vie, surtout si vous devez retenir beaucoup de passphrases.<!--TODO: safe--> **La plupart des passphrases de plus de 4 mots devrait faire l'affaire.** Néanmoins plus vous respecterez ces quelques points, plus votre passphrase sera forte:

  * Au minimum **5 mots**. Cette règle seule peut suffire si vous n’utilisez pas les 5 mots les plus utilisés du dictionnaire. Par contre, n'y dérogez que si vous êtes sur de ce que vous faites. <!--*et* **10 caractères** au total // Always the case-->
  * Au moins une majuscule *et* une ponctuation *et* un chiffre.
  * N’hésitez pas à utiliser des "langages *(vocabulaire, grammaire...)* personnels", moins les mots sont courants mieux c'est, mais **pas** de noms personnels (enfants, **animaux de compagnie** etc...)
  * Moins la phrase à de sens *commun* mieux c'est
  * Vous avez le droit de faire des f0tes d'orthogaphe! Faire des fautes syntaxiques, orthographiques ou de grammaire augmente grandement la sécurité de votre passphrase. Inventer des mots nouveaux (gardez les pour vous) et amusants, n'oubliez pas de garder une phrase simple à retenir---de manière générale plus la phrase est **atypique** plus elle **simple à retenir**.
<!-- length, number of items SPACE,NUMBER,WORD,PUNCTUATION is necessary
Add count to examples -->
<!-- See http://www.bu.edu/infosec/howtos/how-to-choose-a-password/ for article on passwords 
Have another article with a calculator of cracking time and exponential plots
TODO: how to choose something obscure 
TODO: count words in passphrase -->


#### Exemples 

Soyez créatif! N'utilisez surtout pas les exemples ci-dessous! (Ou tout autre texte qu'un attaquant pourrait s'attendre à voir utilisé)

Bon: "<b class="ctgreen">1 escalavelo</b> grimpe dans le <b class="ctgreen">G</b>rand <b class="ctgreen">C</b>edre." 
Moins bon: "<b class="ctred">Marion</b> grimpe dans le grand cedre."

Bon: "<b class="ctgreen">L'elephoque</b> fait <b class="ctgreen">10</b> brasses<b class="ctgreen">. D</b>ans la <b class="ctgreen">reserviere!</b>"
Moins bon: "La <b class="ctred">loutre</b> fait <b class="ctred">dix</b> brasses dans la <b class="ctred">riviere</b>"



<!-- data-height="1050" -->
<iframe data-interface >
  "src": "castlenet/wireless_security.html",
  "fitElsX": "td:has(> [name=WpaPreSharedKey])",
  "scroll": 320
</iframe>



#### Changez votre passphrase

* Cliquez <b data-interface-selector="[name=ShowWpaKey]" data-layout="push" data-color="ctgreen">afficher la clé</b>
* Saisissez votre passphrase dans <b data-interface-selector="[name=WpaPreSharedKey]" data-layout="push" data-color="ctorange">Clé pré-partagé WPA</b>
* **Vérifiez que votre clé correspond bien à celle que vous avez choisie.** Vous allez devoir l'utiliser maintenant pour reconnecter vos appareils.
* Cliquez <b data-interface-selector="[value=Appliquer]" data-layout="push" data-color="ctyellow">Appliquer</b>

Reconnectez maintenant vos appareils Wi-Fi avec votre nouvelle clé.



## Changement des identifiants de l'interface
Le modem Castlenet va à l'encontre de toutes les bases de la sécurité en ayant des identifiants **par défaut**, qui sont de plus **les mêmes chez chaque abonné**.

Choisissez une passphrase de la même manière que pour votre PSK dans la rubrique *Pre Shared Key Forte*. Vous pouvez également utiliser un coffre--fort numérique pour stocker et générer aléatoirement ce genre de mot de passe que vous utilisez peu souvent.

<iframe data-interface >
  "src": "castlenet/status_security.html",
  "width": 680,
  "height": 400
</iframe>

#### Etape 1: Accès a la page des options de Sécurité du modem

 * Menu <b data-interface-selector="[src='./assets/btn_status_y.gif']" data-color="ctyellow">Status</b>
 * Sous-menu <b data-interface-selector="[src='./assets/btn_security_y_g.gif']" data-color="ctorange">Sécurité</b>
 

<iframe data-interface >
  "src": "castlenet/status_security.html",
  "vbreak": true,
  "width": 680,
  "height": 450
</iframe>


#### Etape 2: Changement du mot de passe de l'interface
  * Utilisateur: <b data-interface-selector="[name=UserId]" data-layout="push" data-color="ctgreen">admin</b>
  * Entrez votre mot de passe dans <b data-interface-selector="[name=Password]" data-layout="push" data-color="ctorange">Nouveau mot de passe</b> **et** <b data-interface-selector="[name=PasswordReEnter]" data-layout="push" data-color="ctorange">Re-entrer le nouveau mot de passe</b>
  * Mot de passe actuel de l'utilisateur: <b data-interface-selector="[name=OldPassword]" data-layout="push" data-color="ctviolet">password</b>

*N'oubliez pas, ci-dessous, de valider vos changements! (ou cliquez une première fois sur* ***Appliquer*** *dès maintenant)*
 
 
## Désactiver l’accès WAN a l'interface

*L’accès WAN et WPS sont désactivés par défaut. Vérifiez: on n'est jamais trop prudent!*

L’accès par WAN vous permet d’accéder à l'interface de votre modem en dehors de chez vous. C'est une porte ouverte aux personnes mal intentionnées, surtout si par malheur les identifiants par défaut sont utilisés... A désactiver absolument sauf si vous en aviez besoin dans un cas particulier (très rare).
 

<iframe data-interface >
  "src": "castlenet/status_security.html",
  "width": 680,
  "height": 600
</iframe>

#### Désactivation de l’accès WAN

 * Décochez <b data-interface-selector="[name=RemoteManagement]" data-color="ctorange">Controle a distance de la configuration du modem</b>
 * Cliquez <b data-interface-selector="[value=Appliquer]" data-color="ctyellow">Appliquer</b>
 
 
 
## Désactiver WPS

WPS permet de connecter un nouvel appareil (ou un appareil ayant "oublié" les paramètres Wi-Fi) avec un simple PIN (code) ou un appuyant sur un bouton réserver à cet usage sur le routeur.

La sécurité du mode PIN est cassée, depuis le début de son existence avec des attaques pratiques dès 2011.

Le mode *bouton* n'a pas les mêmes problèmes mais il est préférable de se connecter avec votre passphrase. De plus, la plupart des routeurs ne dissocient malheureusement pas les deux modes, obligeant l'utilisateur soucieux de sa sécurité à se passer de WPS.

<iframe data-interface >
  "src": "castlenet/wireless_security.html",
  "width": 700,
  "height": 450
</iframe>

#### Etape 1: Accès a la page des options de Sécurité Wi-Fi

 * Menu <b data-interface-selector="[src='./assets/btn_wireless_y.gif']" data-color="ctyellow">Sans fil</b>
 * Sous-menu <b data-interface-selector="[src='./assets/btn_security_y_g.gif']" data-color="ctorange">Sécurité</b>
 
 
<iframe data-interface >
  "src": "castlenet/wireless_security.html",
  "vbreak": true,
  "width": 1130,
  "height": 450
</iframe>

#### Etape 2: Désactivation de WPS

 * Choisissez *Désactivé* pour <b data-interface-selector="[name=WpsConfig]" data-layout="push" data-color="ctviolet">Config WPS</b>
 * Cliquez <b data-interface-selector="[value=Appliquer]:gt(0)" data-color="ctgreen">Appliquer</b>
