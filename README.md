# LEC030301 - Bornier de distribution sécable mini – 2 x 4 plots
Fichiers sources pour le produit LEC030301

## Description du produit

- **DISTRIBUTION** Les 4 borniers verts sont tous connectés ensemble, tout comme les 4 borniers bleus. Courant max = 10 A. Tension max = 250 V.
- **SÉCABLE** Coupez les barrettes sur les pointillés pour les séparer en 2 barrettes indépendantes.
- **MARQUEUR** Le module dispose d’une zone blanche dans laquelle il est possible d’indiquer à l’aide d’un feutre la polarité, la tension, ou bien un numéro d’identification propre à vous.
- **APPLICATIONS** Utilisez ces barrettes de distribution pour connecter facilement une alimentation à plusieurs dispositifs (éclairage, modules, …).

## Utiliser les fichiers sources pour fabriquer le produit

Il n'est **pas nécessaire de savoir souder ou d'être bon en électronique** pour se procurer ce produit. Grâce aux fichiers sources publiés ici, vous pouvez être en mesure de faire fabriquer ce produit par un sous traitant.

### Faire fabriquer chez un sous traitant

Il est aujourd'hui possible de faire fabriquer à moindre cout des cartes électroniques. Nous recommendons [JLCPCB](https://jlcpcb.com/) si vous voulez aller au moins cher. Si vous préférez un acteur européen, [eurocircuits](https://www.eurocircuits.com/) est un des acteurs reconnus.

[![IMAGE ALT TEXT](https://user-images.githubusercontent.com/21155051/227790488-3d505f7f-50a5-4423-a540-14bc276046c1.png)](http://www.youtube.com/watch?v=RXGGvsUtz0c "TUTO : faire fabriquer un produit LECTIX")

1. Télécherger les sources de ce produit en cliquant sur le bouton `Code`, puis `Download ZIP`.
1. Décompresser le dossier.
1. Les fichiers pour la fabrication se trouvent dans le répertoire `hardware/prod`.
1. Se connecter sur [https://cart.jlcpcb.com/quote](https://cart.jlcpcb.com/quote)
1. Cliquer sur le bouton `Add gerber file` et sélectionner le fichier `gerbers.zip`.
1. Sélectionnez la quantité de cartes que vous souhaitez dans le champs `PCB Qty`.
1. Laisser toutes les autres options par défaut, puis cliquez sur le toggle switch en face de `PCB Assembly`, et enfin sur le bouton `confirm`.
1. Une preview de la carte électronique sans les composants doit apparaitre. Cliquez sur `NEXT`.
1. Cliquez sur le bouton `Add BOM File`, puis sélectionnez le fichier `bom.csv`
1. Cliquez sur le bouton `Add CPL File`, puis sélectionnez le fichier `pos.csv`
1. **Vérifier que tous les composants sont en stock** et bien sélectionnés, puis cliquez sur `NEXT`.
1. Une preview de la carte avec ses composants apparait. Continuer le chemin en cliquant sur `NEXT`.
1. Le prix final apparait. Sélectionnez la catégorie du produit, puis cliquez sur `SAVE TO CART`.
1. Une fois sauvegardé dans votre panier, vous pouvez valider votre commande et choisir le moyen d'acheminement. Afin de ne pas avoir à se préoccuper des frais de douane, nous vous conseillons de choisir une méthode d'expédition DDP.

Vous receverez vos cartes sous 1 à 3 semaines. 

**Nous ne sommes en aucun cas responsables des cartes qui arriveraient défectueuses ou non fonctionnelles.**

### Modifications des fichiers sources

Installez kicad 6 (ou version supérieure), et ouvrez le fichier LEC030301.kicad_pro

### Regénérer les fichiers gerber, BOM, et position (Optionnel)

Peut se faire simplement en utilisant kikit :

```
cd hardware

# generate assembly files
docker run --rm -w /kikit -v $PWD:/kikit yaqwsx/kikit kikit fab jlcpcb --assembly --no-drc --schematic LEC030301.kicad_sch --field LCSC --corrections JLCPCB_CORRECTION --nametemplate LEC030301_{} LEC030301.kicad_pcb prod/

```

## License
Tous nos fichiers sont plubliés sous la license CERN Open Hardware Licence Version 2 - Strongly Reciprocal