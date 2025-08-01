### Documentation README.md

**Objectif** : Rendre le projet facilement exécutable par d'autres développeurs.

Rédigez un fichier README.md qui contient des instructions claires et détaillées pour :


- **Prérequis** : L'installation de Scala, Spark et SBT (optionnel).
- **Compilation** : Les commandes pour compiler le projet et générer le JAR.

- **Exécution locale** : Les commandes pour lancer l'application avec SBT en mode
local.
- **Déploiement** : La commande spark-submit pour exécuter l'application sur un
cluster.


# 📊 EcommerceAnalytics

Une application analytique Spark en Scala pour explorer les comportements d'achat, les utilisateurs, les produits et les transactions d'un site e-commerce.

---

## ✅ Prérequis

Avant de démarrer, assurez-vous d’avoir installé les composants suivants :

### 🔧 Environnement local

- [Java JDK 11](https://adoptium.net/) ✅
- [Scala 2.12.x](https://www.scala-lang.org/download/)
- [SBT (Scala Build Tool)](https://www.scala-sbt.org/download.html)
- [Apache Spark 3.5.1](https://spark.apache.org/downloads.html) (recommandé pour `spark-submit`)

### 🧪 Vérifier les versions

```bash
java -version          # Doit indiquer Java 11
scala -version         # Doit indiquer Scala 2.12.x
sbt sbtVersion         # SBT  1.11.3
spark-shell --version  # Spark 3.5.1

```

###  Commande sbt 

**Exécution locale** : Les commandes pour lancer l'application avec SBT en mode
local.

`sbt compile`  pour la Compilation

`sbt run` pour  Execution en locale 

 Dans le repertoire contenant built.sbt   lancer `sbt package`  pour générer le fichier  jar dans target [scala-2.12](target/scala-2.12)

### Commande  Lancement avec spark-submit  

**Déploiement** : La commande spark-submit pour exécuter l'application en local.

// Écrire la commande spark-submit pour lancer ce job en local avec 4 coeurs et en mode client:

```bash
spark-submit \
--class com.ecommerce.analytics \
--master local[4] \
--deploy-mode client \
target/scala-2.12/ecommerceanalytics_2.12-0.1.0-SNAPSHOT.jar 
```

**Déploiement** : La commande spark-submit pour exécuter l'application sur un
  cluster.


//Modifier cette commande pour un lancement sur un cluster YARN, en mode cluster, avec :

```bash
spark-submit \
--class com.ecommerce.analytics \
--master yarn \
--deploy-mode cluster \
--executor-memory 4G \
--executor-cores 2 \
target/scala-2.12/ecommerceanalytics_2.12-0.1.0-SNAPSHOT.jar 
```