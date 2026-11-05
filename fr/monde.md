# Le monde

[Accueil](../README.md) · [Le guide](guide.md) · [Les animaux](animaux.md) · [Machines et objets](machines.md) · **Le monde** · [Les recettes](recettes.md)

## Les saisons

Il y a quatre saisons de 7 jours chacune, et cette durée se règle. Elles ne changent pas l'apparence du monde : elles comptent pour la température, la reproduction et le broutage.

| Saison | Écart de température |
|---|---|
| Printemps | 0 °C |
| Été | +8 °C |
| Automne | -1 °C |
| Hiver | -10 °C |

`/time set` ne change pas la saison, et dormir fait avancer le calendrier.

## La température

La température d'un endroit se calcule ainsi :

- le biome : environ 16 °C en plaine, 38 °C dans le désert et 2 °C dans la toundra
- la saison, selon le tableau ci-dessus
- l'heure : 3 °C de plus à midi et 4 °C de moins à minuit
- l'altitude : au-dessus de la couche 80, 0,08 °C de moins par bloc
- un abri : sans ciel au-dessus, la température se rapproche de 15 °C
- les blocs chauds ou froids dans un rayon de 6 blocs et 4 blocs de haut

Chaque source apporte toute sa puissance au contact, puis de moins en moins avec la distance. Les sources s'additionnent, jusqu'à +60 °C et -25 °C.

| Source | Puissance | Portée (blocs) |
|---|---|---|
| Lave, chaudron de lave | +30 °C | 6 |
| Feu | +20 °C | 4 |
| Feu de camp allumé | +16 °C | 5 |
| Feu de camp des âmes allumé | +11 °C | 5 |
| Fourneau, fumoir ou haut fourneau allumé | +8 °C | 3 |
| Bloc de magma | +8 °C | 3 |
| Torche | +3 °C | 2 |
| Lanterne | +2 °C | 2 |
| Glace bleue | -12 °C | 4 |
| Glace compactée | -8 °C | 3 |
| Glace | -6 °C | 3 |
| Bloc de neige, neige poudreuse | -4 °C | 2 |

## Les cultures

Une culture ne pousse que dans sa plage de température. En hiver, une serre chauffée peut donc être nécessaire.

| Culture | Plage de pousse |
|---|---|
| Blé | 4 à 32 °C |
| Carottes | 2 à 28 °C |
| Pommes de terre | 4 à 28 °C |
| Betteraves | 0 à 28 °C |
| Pastèque | 12 à 38 °C |
| Citrouille | 10 à 36 °C |
| Baies sucrées | 0 à 30 °C |
| Cacao | 18 à 40 °C |
| Torche-fleur, planturne | 10 à 32 °C |
| Autres cultures | 2 à 35 °C |

## La fatigue du sol

Récolter la même culture au même endroit fatigue la terre, à partir de la 3e récolte de suite. La fatigue va de 0 à 5. Chaque point retire 15 % de la récolte et donne 15 % de chances à la plante de ne pas pousser quand elle le devrait.

Récolter une autre culture fait repartir le compte de 1. La poudre d'os retire 1 récolte du compte.

## Les populations sauvages

Chaque espèce a une population à l'échelle du monde, donnée dans [le tableau des espèces](animaux.md). Les 17 plantes suivies partent de 300 : les petites fleurs, le buisson à baies sucrées et les champignons brun et rouge.

Une population baisse de 1 quand un joueur tue un animal sauvage, capturé ou relâché, et quand on casse une plante sauvage. Une plante posée par un joueur ne compte pas, et un animal d'élevage non plus. Une espèce regagne 2 % de son maximum par jour écoulé, sauf si elle est éteinte.

| Statut | Population |
|---|---|
| Commune | Plus de 50 % du maximum |
| Vulnérable | 50 % ou moins |
| Menacée | 25 % ou moins |
| Éteinte dans la nature | 0 |

Une espèce éteinte n'apparaît plus naturellement, et une plante éteinte n'est plus présente en surface dans les nouveaux chunks. Pour la sauver :

- relâchez un animal d'élevage avec le [carnet](machines.md) : +3 la première fois
- utilisez une [banque de semences](machines.md) : l'espèce revient à 10 % de son maximum

## Les enclos en détail

Un enclos est mesuré une fois par minute pour les animaux qui y vivent, et toutes les 2 minutes pour un animal libre. Si une mesure touche un chunk non chargé, elle ne conclut rien et rien ne change.

Portillons, portes et trappes comptent selon leur état réel, même quand la redstone les change. Au-delà de 16 384 cases, la zone est considérée comme ouverte.

## Réglages

Dans `config/faunaflora-common.toml` :

| Réglage | Par défaut | Limites |
|---|---|---|
| `seasonLengthDays` | 7 | 1 à 120 |
| `wildRegrowthPerDay` | 0,02 | 0 à 1 |

## Commandes

Elles sont réservées aux opérateurs (niveau 2), et servent surtout aux tests. Le jar contient encore ces outils de test.

| Commande | Effet |
|---|---|
| `/faunaflora info [cible]` | Fiche complète d'un animal |
| `/faunaflora pen [cible]` | Zone d'un animal : enclos, surface, installations |
| `/faunaflora housing` | Enclos en mémoire et coût des mesures |
| `/faunaflora clock` | Temps, jour, saison, nuits dormies |
| `/faunaflora calendar set <jour>` | Change le jour du calendrier |
| `/faunaflora calendar season <saison>` | Change la saison |
| `/faunaflora needs <cibles> <faim> <soif>` | Règle les besoins |
| `/faunaflora status <cibles> <origine> <statut>` | Règle l'origine et le statut |
| `/faunaflora spawn <espèce> male\|female` | Fait apparaître un animal |
| `/faunaflora population [espèce] [valeur]` | Lit ou règle une population |
| `/faunaflora population plant <plante> [valeur]` | Pareil pour une plante |
| `/faunaflora testfarm` | Construit une ferme de démonstration |
