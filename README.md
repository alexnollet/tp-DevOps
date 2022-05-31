# Documentation devOps

Cette documentation indique toutes les bonnes pratiques afin de réaliser du code maintenable.

## Linter

En terme de Linter il faut que chaque personnes aient le même afin d'éviter des changements inutile selon le développeur qui va modifier le code.

Pour respecter ceci l'utilisation de la suite JetBrains ou de VSCode avec des extensions le tout étant de s'accorder sur quoi utiliser. (IntelliCode par exemple)

## Design pattern

Il est recommandé d'utiliser des desgin pattern dans le code permettant une meilleur organisation de celui-ci.

Vous pouvez par exemple utiliser *Factory*, ce modèle consiste à créer une fonction permettant de créer les classes correspondante 

### exemple

``` javascript
import Motorvehicle from './Motorvehicle';
import Aircraft from './Aircraf';
import Railvehicle from './Railvehicle';

const VehicleFactory = (type, make, model, year) => {
  if (type === car) {
    return new Motorvehicle('car', make, model, year);
  } else if (type === airplane) {
    return new Aircraft('airplane', make, model, year);
  } else if (type === helicopter) {
    return new Aircraft('helicopter', make, model, year);
  } else {
    return new Railvehicle('train', make, model, year);
  }
}

module.exports = VehicleFactory;
```

## Documentation

Chaque feature devra être documenté afin que chaque développeur puisse comprendre facilement le fonctionnement de celle-ci.

Cette documentation devra contenir ces éléments :
- où se trouve cette fonctionnalité dans le code
- à quoi elle sert
- les inputs et output des fonctions
- comment les tester
- le comportement souhaité en fonction des entrées.

## Definition of Done

La definition of done permet de définir ce qu'il faut avoir effectué pour déclarer une tâche comme étant terminée.

### exemple
- Les tests d’acceptance associés à la story passent
- Le code est mergé sur develop
- Le nouveau code s’intègre correctement et les tests de non-régression passent
- La version incluant cette évolution a été déployée en environnement de qualification
- Le gestionnaire de suivi a été mis à jour (demande close)