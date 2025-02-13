# Agrocam
L'Agrocam est une caméra connectée pour suivre l'évolution de vos cultures ! Elle permet de prendre une photo à intervalles réguliers !
Ici vous trouverez les étapes générales à suivre pour l'assemblage de votre Agrocam. Des informations plus détaillées sont présentes dans les Readme de chaque dossier ```Agrocam/Code``` et ```Agrocam/Fichiers 3D```



# Où installer une Agrocam
L'installation se fait facilement sur un piquet de palissage. Il faut que la parcelle soit couverte par le réseau 3G/4G.

# Présentation générale du fonctionnement
L'Agrocam se base sur une carte [raspberry pi zero](https://fr.aliexpress.com/item/32862749459.html?spm=a2g0o.productlist.0.0.2db345dfJ8qqIP&algo_pvid=d2d9674d-896a-4ba8-a8f7-3204eff93039&algo_exp_id=d2d9674d-896a-4ba8-a8f7-3204eff93039-56&pdp_ext_f=%7B%22sku_id%22%3A%2265489160780%22%7D&pdp_npi=2%40dis%21EUR%21%2194.15%21%21%21%21%21%400b0a050b16529547418287107e2ee8%2165489160780%21sea) et d'une [picam](https://fr.aliexpress.com/item/4000078355774.html?spm=a2g0o.productlist.0.0.3b0b78afgj07rV&algo_pvid=7b9f3a4e-c2a0-4328-92a0-ba677d3226c6&algo_exp_id=7b9f3a4e-c2a0-4328-92a0-ba677d3226c6-12&pdp_ext_f=%7B%22sku_id%22%3A%2210000000203526796%22%7D&pdp_npi=2%40dis%21EUR%21%219.19%21%21%21%21%21%400b0a050b16529546046245087e2ee8%2110000000203526796%21sea). Un script hybride (shell et python) est installé sur l'Agrocam et permet d'envoyer une photo sur un serveur FTP via internet. La photo est acquise et envoyée à chaque allumage du raspberry sui s'éteint une fois la tache accomplie. La communication réseau se fait à l'aide d'un [dongle 4G](https://fr.aliexpress.com/item/1005004055536615.html?spm=a2g0o.productlist.0.0.598076b34EWXMu&algo_pvid=d27b7dc1-f063-45e8-842d-b50b623dfcb6&algo_exp_id=d27b7dc1-f063-45e8-842d-b50b623dfcb6-6&pdp_ext_f=%7B%22sku_id%22%3A%2212000028196486635%22%7D&pdp_npi=1%40dis%7CEUR%7C%7C14.7%7C%7C%7C%7C%7C%400b0a187916512350350418464e6aef%7C12000028196486635%7Csea) branché au port mini usb de la carte Raspberry. Ce dongle 4G permet de diffuser un réseau wifi auquel se connecte le raspberry. 

Une carte [Witty Pi 4](https://www.gotronic.fr/art-carte-alim-et-rtc-witty-pi-4-35473.htm) permet de gérer l'allumage et l'exctinction à intervalle régulier du raspberry grâce à un paramétrage depuis le terminal du raspberry. L'alimentation par les batteries arrive donc d'abord dans la carte Witty Pi qui gère ensuite l'alimentation du raspberry.

# Liste du matériel à acheter

| Composant | Montant |
| ------------- | ------------- |
| [Raspberry Pi zero](https://fr.aliexpress.com/item/1005002762721660.html?_randl_currency=EUR&_randl_shipto=FR&src=google&aff_fcid=f2c9b3fef8f449de83d249fa6d53ca15-1657007543491-08844-UneMJZVf&aff_fsk=UneMJZVf&aff_platform=aaf&sk=UneMJZVf&aff_trace_key=f2c9b3fef8f449de83d249fa6d53ca15-1657007543491-08844-UneMJZVf&terminal_id=0e5bf68749b0416b9d7676273b58898a&afSmartRedirect=y)  | 20 €  |
| [Picam](https://www.gotronic.fr/art-camera-12-mpx-wide-sc0874-36590.htm) | 47 €  |
| [Witty Pi 4](https://www.gotronic.fr/art-carte-alim-et-rtc-witty-pi-4-35473.htm)  | 38 € |
| [Dongle 4G](https://fr.aliexpress.com/item/1005004055536615.html?spm=a2g0o.productlist.0.0.598076b34EWXMu&algo_pvid=d27b7dc1-f063-45e8-842d-b50b623dfcb6&algo_exp_id=d27b7dc1-f063-45e8-842d-b50b623dfcb6-6&pdp_ext_f=%7B%22sku_id%22%3A%2212000028196486635%22%7D&pdp_npi=1%40dis%7CEUR%7C%7C14.7%7C%7C%7C%7C%7C%400b0a187916512350350418464e6aef%7C12000028196486635%7Csea) | 15 €  |
| [Servomoteur](https://www.gotronic.fr/art-servomoteur-digital-miniature-ft90b-30604.htm) | 2 €  |
| [Cellules Li-ion 18650 x2](https://www.gotronic.fr/art-accu-li-ion-18650-2-5a-29250.htm) | 25€  |
| [Boitier 18650 double](https://www.gotronic.fr/art-coupleur-d-accus-bh12900-38664.htm) | 2 €  |
| [Cavalier](https://www.gotronic.fr/art-cavaliers-femelles-a-languette-cfp17n-35570.htms) | 0,3 €  |
| [Jumpers](https://fr.aliexpress.com/item/1005002118864496.html?spm=a2g0o.productlist.0.0.530740cfAR8qgh&algo_pvid=0429f2d3-4abb-4a2c-b8bd-1748949ab90c&algo_exp_id=0429f2d3-4abb-4a2c-b8bd-1748949ab90c-8&pdp_ext_f=%7B%22sku_id%22%3A%2212000023064345895%22%7D&pdp_npi=2%40dis%21EUR%21%213.29%21%21%214.03%21%21%402100bb5116570122092244505ed183%2112000023064345895%21sea) | 3 €  |
| [Kit JST](https://fr.aliexpress.com/item/1005003422202370.html?spm=a2g0o.productlist.0.0.2eb85a5duk04cJ&algo_pvid=41b3bc5e-84cd-4fbe-933e-c4d3120288d9&algo_exp_id=41b3bc5e-84cd-4fbe-933e-c4d3120288d9-7&pdp_ext_f=%7B%22sku_id%22%3A%2212000025716082488%22%7D&pdp_npi=2%40dis%21EUR%21%212.13%21%21%211.69%21%21%402100bdf016570105419446040ebdca%2112000025716082488%21sea) | 2 € |
| [Pince à sertir](https://fr.aliexpress.com/item/32868911434.html?spm=a2g0o.productlist.0.0.2f587e06bSnjd5&algo_pvid=04e6c361-f4e5-43c0-ad2c-eed0e5f49ecf&algo_exp_id=04e6c361-f4e5-43c0-ad2c-eed0e5f49ecf-47&pdp_ext_f=%7B%22sku_id%22%3A%2266131948288%22%7D&pdp_npi=2%40dis%21EUR%21%2114.12%21%21%217.56%21%21%402100bdf016570107144048375ebdca%2166131948288%21sea) | 15 €  |
| [Visserie support composant](https://fr.aliexpress.com/item/1005002324715062.html?spm=a2g0o.productlist.0.0.764c3f2b8lFqQH&algo_pvid=24349cd5-9301-41b6-af63-d6aa2ae00a2c&algo_exp_id=24349cd5-9301-41b6-af63-d6aa2ae00a2c-4&pdp_ext_f=%7B%22sku_id%22%3A%2212000020091507818%22%7D&pdp_npi=2%40dis%21EUR%21%213.8%21%21%21%21%21%400b0a0ae216570112948036065e4a01%2112000020091507818%21sea) | 1 €  |
| [Visserie boitier](https://fr.aliexpress.com/item/10000150053486.html?spm=a2g0o.productlist.0.0.14261206iFznJY&algo_pvid=ce94aece-006d-4237-84f0-6779d910fc02&algo_exp_id=ce94aece-006d-4237-84f0-6779d910fc02-1&pdp_ext_f=%7B%22sku_id%22%3A%2220000000127991024%22%7D&pdp_npi=2%40dis%21EUR%21%210.91%21%21%21%21%21%400b0a0ae216570113345626393e4a01%2120000000127991024%21sea) | 1 €  |
