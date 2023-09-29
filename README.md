# _A venir prochainement_
[![Top Web Framework](/docs/top_web_framework.png)]()

## Cucumber BDD Framework with Selenium, TestNG and Java

### Sommaire:

🏷️ [Architecture et Présentation du framework](#Architecture-et-Présentation-du-framework)<br/>
🏷️ [Fonctionnalités](#fonctionnalités)<br/>
🏷️ [Prérequis avant installation](#prérequis-avant-installation)<br/>
🏷️ [Comment installer le framework](#comment-installer-le-framework)<br/>
🏷️ [Comment exécuter le framework](#comment-exécuter-le-framework)<br/>
🏷️ [Comment consulter les rapports](#comment-consulter-les-rapports)<br/>
🏷️ [Comment étendre le framework](#comment-étendre-le-framework)<br/>
🏷️ [Comment maintenir le framework](#comment-maintenir-le-framework)<br/>
🏷️ [Comment déboguer le framework](#comment-déboguer-le-framework)<br/>

### 🎯Architecture et Présentation du framework

[![framework-architecture](/docs/framework-architecture.png)]()

### 🎯Structure du framework

```
📦MediumWebFramework
┣ 📂docs
┣ 📂logs
┃  ┗ 🗒️applog.log
┣ 📂src
┃ ┣ 📂test
┃ ┃ ┣ 📂java
┃ ┃ ┃ ┗ 📂bdd
┃ ┃ ┃ ┃ ┗ 📂automation
┃ ┃ ┃ ┃ ┃ ┣ 📂apis
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜ApiRequest.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜CartApi.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜SpecBuilder.java
┃ ┃ ┃ ┃ ┃ ┣ 📂constants
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜EndPoint.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜EnvType.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜MyConstants.java
┃ ┃ ┃ ┃ ┃ ┣ 📂context
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜TestContext.java
┃ ┃ ┃ ┃ ┃ ┣ 📂customtype
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜CustomDataTableType.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜CustomParameterType.java
┃ ┃ ┃ ┃ ┃ ┣ 📂domainObjects
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜BillingDetails.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜Cookies.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜Product.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜ProductList.java
┃ ┃ ┃ ┃ ┃ ┣ 📂factory
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜DriverFactory.java
┃ ┃ ┃ ┃ ┃ ┣ 📂hooks
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜MyHooks.java
┃ ┃ ┃ ┃ ┃ ┣ 📂pages
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜BasePage.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜CartPage.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜CheckoutPage.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜PageFactoryManager.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜ProductPage.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜StorePage.java
┃ ┃ ┃ ┃ ┃ ┣ 📂runners
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜Main.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜FailedRunnerTest.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜TestNGRunnerTest.java
┃ ┃ ┃ ┃ ┃ ┣ 📂steps
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜BaseStep.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜CartSteps.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜CheckoutSteps.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜CustomerSteps.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜ProdutSteps.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜StoreSteps.java
┃ ┃ ┃ ┃ ┃ ┣ 📂utils
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜ConfigLoader.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜CookieUtils.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜JacksonUtils.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜LogUtils.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜PropertyUtils.java
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜ScreenRecordUtils.java
┃ ┃ ┣ 📂resources
┃ ┃ ┃ ┗ 📂bdd
┃ ┃ ┃ ┃ ┗ 📂automation
┃ ┃ ┃ ┃ ┃ ┣ 📂features
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📒add_to_cart.feature
┃ ┃ ┃ ┃ ┃ ┃ ┗ 📒guest_place_an_order.feature
┃ ┃ ┃ ┗ 📂test-data
┃ ┃ ┃ ┃ ┣🧾billingDetails.json
┃ ┃ ┃ ┃ ┣🧾products.json
┃ ┃ ┣ 📑allure.properties
┃ ┃ ┣ 📑cucumber.properties
┃ ┃ ┣ 📑extent.properties
┃ ┃ ┣ 📑log4j2.properties
┃ ┃ ┣ 📑prod_config.properties
┃ ┃ ┣ 📑stage_config.properties
┣ 💼target
┃ ┣ 📂cucumber-reports
┃ ┃ ┣📄cucumber.html
┃ ┃ ┣🧾cucumber.json
┃ ┃ ┣📃️cucumber.xml
┣🧰test-output
┃ ┣ 📂ExtentReport
┃ ┃ ┣ 📂SparkReport
┃ ┃ ┃ ┣📄ExtentSpark.html
┃ ┃ ┃ ┣ 📂screenshot
┃ ┃ ┃ ┃ ┣ 📑embedded1.png
┣🧰test-recordings
┃ ┣ 📄main-2023-06-01 06.42.13.avi
┣🧰test-suites
┃ ┣📃smoke-tests.xml
┣ 📑pom.xml
┣ 📑README.md
```

Si vous souhaitez tester une application web de préférence (un ecommerce).</br>
🌟Si vous êtes `TESTEUR AUTOMATICIEN` et que vous voulez apprendre à automatiser des tests fonctionnels.</br>
🌟Si vous êtes un  `RECRUTEUR` pour évaluer les compétences de nos testeurs automaticiens talentueux.</br>
🌟 Ou encore si vous êtes un `PARTICULIER`ou une `ENTREPRISE` à la recherche de solution
répondant à vos besoins d'automatisation en test alors ce framework est fait pour vous!</br></br>

🎁 Ce framework permet d'exécuter vos tests en séquentiel sur le navigateur de votre choix,
soit `Chrome`, `Firefox`, `Opera`, `Edge` ou `Safari`.</br>
🎁 Il s'exécute également sur plusieurs plateformes comme : `Windows 10` et `Mac`.</br>
🎁Il contient aussi du reporting avec des `rapports (au format : Html, Json et xml)` et de l'Extent Report `(au format : Html)`
pour vous permettre d'avoir une visibilité de la couverture des tests effectués avec succès et des tests qui ont échoués,
il capture une image d'erreur lors de l'échec des tests pour un meilleur débogage des tests.</br>
🎁Il contient plusieurs modèles et bonnes pratiques comme le `Page Object Model`, le `page Factory`
qui vous permettent d'avoir un framework assez `Robuste`, `Réutisable`, `Maintenable` et `Rapide`.</br>
🎁Il offre également des `Logs` qui vous fournissent une traçabilité, des informations pertinentes
sur l'exécution de vos tests et aident à déboguer le framework en cas d'échec des tests.</br>
🎁Il offre aussi le `Screen Record` qui enregistre des vidéos d'exécution des tests effectués pour vous offrir une meilleure expérience de test.</br>
🎁 Et enfin, ce framework permet d'exécuter les tests en `CROSS BROWSER TESTING`, ici vos tests sont exécutés sur différents navigateurs
en parallèle.</br></br>

### 🎯Fonctionnalités
✅ Java<br/>
✅ Selenium 4<br/>
✅Cucumber BDD (Features + Step Definitions)<br/>
✅ Data Driven Testing (Cucumber DataTables + Json)<br/>
✅ Page Object Model +  Page Factory<br/>
✅ Cucumber Report (Html, Json, Xml)<br/>
✅ Spark Extent Report<br/>
✅ Screenshot<br/>
✅ Logs<br/>
✅ REST API (Rest Assured)<br/>
✅ Allure Report<br/>
✅ Screen record<br/>
✅ Cross Browser Execution (Chrome, Firefox & Edge)<br/><br/>

### 🎯Prérequis avant installation

####  🔴 Sur PC Mac

```  bash
💊 HOMEBREW [Mac]
🔹Télécharger et installer homebrew (si pas déjà installé): 
♾️ /bin/bash -c “$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)”
♾️ brew update
```

```
  💊 JAVA 11 [Mac]
  🔹Télécharger et installer Java 11 (openJdk11): 
   ♾️ brew install java11
   ♾️ sudo ln -sfn /usr/local/opt/openjdk@11/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-11.jdk
  🔹Configurer java home: 
   ♾️ export JAVA_HOME = /Library/Java/Home
  🔹Vérifier la version de java: 
   ♾️ java --version
```
⚓Installez [Java via HomeBrew sur Mac](https://medium.com/@kirebyte/using-homebrew-to-install-java-jdk11-on-macos-2021-4a90aa276f1c)

```
  💊MAVEN 3.8.6 [Mac]
  🔹 Installer sur Mac à partir du terminal: 
   ♾️ brew install maven
  🔹Configurer les variables d'environment:
      export M2_HOME=/usr/local/apache-maven/apache-maven-3.8.4 
      export M2 = $M2_HOME/bin
      export MAVEN_OPTS = -Xms256m -Xmx512m
```

```
    💊Allure 2 [Mac - Terminal]  
    ♾️ brew install allure
```
⚓ Installer [Allure via Homebrew](https://brew.sh/)

##### 📮 NAVIGATEURS [A installer]<br/>
🔹[Mac] ➡️ [Safari](https://support.apple.com/downloads/safari), [Chrome](https://setapp.com/how-to/install-google-chrome-for-mac-quickly), [Firefox](https://support.mozilla.org/en-US/kb/how-download-and-install-firefox-mac), [Opera](https://www.opera.com/fr/browsers/opera) et [Edge](https://www.youtube.com/watch?v=FgbXQbBQc_Q).<br/>
🔹[Windows] ➡️ [Chrome](https://www.google.com/chrome/?brand=BNSD&gclid=CjwKCAjw-IWkBhBTEiwA2exyOzIzlgqqwM5oXGEipBtJ4uaCy-J6hSEMkv4jsP27bwUwqfQGxbkBiRoCs8oQAvD_BwE&gclsrc=aw.ds), [Firefox](https://support.mozilla.org/en-US/kb/how-install-firefox-windows), [Opera](https://www.opera.com/fr/browsers/opera) et Edge (Installé par défaut).

####  🔴 PC WINDOWS

#### Liens de téléchargement :<br/>
⚓[Téléchargez](https://maven.apache.org/download.cgi) et [Installez](https://maven.apache.org/install.html) Maven<br/>
⚓[Téléchargez](https://www.oracle.com/eg/java/technologies/javase/jdk11-archive-downloads.html) et [Installez](https://www.youtube.com/watch?v=SQykK40fFds) Java 11<br/>

```
  💊Allure 2 [Windows - Terminal]  
   ♾️ scoop install allure
```
⚓ Installer [Allure via Windows](https://scoop.sh/)

### 🎯Comment installer le framework

📌Téléchargez le repo zip du projet sur gitlab :
[![download-zip](/docs/download-zip.png "download-zip")]()

📌Ouvrez le projet dans votre IDE :</br>
+ Faîtes un `mvn clean` </br></br>
  [![mvn_clean](/docs/mvn_clean.png "mvn_clean")]()

* Faîtes un ⚠️`build project` et exécutez-le.</br></br>
  [![build-project](/docs/build-project.png "build project")]()

### Comment exécuter le framework
🔶Exécution Cross Browser </br>
+ Ce framework peut être exécuté de plusieurs manières:<br/>
    ``` bash
     📌Fichier smoke-testng.xml 
     ➡️test-suites/smoke-tests.xml
     ```

    ``` bash
     📌Fichier Main.java
     ➡️src/test/java/bdd/automation/runners/Main.java
     ```

    ``` bash
     📌[terminal] 
     ➡️ mvn clean install -D"parallel=tests" -D"scenariosInParallel=true" -PSmoke
    ```
  + exécute les tests en parallèle sur les navigateurs chrome, firefox et edge mais les scénarios sont exécutés en parallel.<br/>
  
🟥 NB: POUR EXÉCUTER CE FRAMEWORK, VOUS DEVEZ AVOIR UNE BONNE CONNEXION INTERNET !

``` 
⛔ Si toute fois, après avoir suivi les étapes d'installation et d'exécution de ce framework,
   vous rencontrez des erreurs, cela est sûrement dû à un faible débit de votre connexion internet ! 
   Et pour résoudre ce problème, suivez les étapes de débogages dans l'étape [Comment déboguer le framework] ⬇️.
```

### 🎯Comment consulter les rapports

📌Dans le ⚠️terminal après l'exécution des tests (sur le lien ci-dessous): ⬇️ </br>
[![cucumber-report](/docs/cucumber-report.png "Cucumber-report")]()</br>

📌 Dans le repertoire ⚠️target/Cucumber Report : </br>
[![reports](/docs/reports.png "reports")]()</br>

📌 Dans le repertoire⚠️test-output/ExtentReport_date_du_report : </br>
[![extent_report](/docs/extent_report.png "extent_report")]()</br>

📌 Faîtes un click droit sur le repertoire `target` du framework puis ouvrir dans le terminal
 ```
    🔸cd target
    🔸Entrez la commande: allure serve allure-results
  ```
* Lancer Allure report:
  [![allure-report](/docs/allure-report.png "allure-report")]()</br>
  
* Allure report dans le navigateur
[![allure-report](/docs/alure-serv.png "allure-report")]()</br>


### 🎯Comment étendre le framework
+ Ce framework vous permet d'effectuer des tests d'interface Utilisateurs (UI) sur une application web d'e-commerce [AskOmDch](https://askomdch.com/store/), les scenarios exécutés ici sont les suivants: <br/><br/>
  ✴️ Ajouter un produit au panier
   ```
   je veux accéder à la page web `https://askomdch.com/store
   Je veux ajouter un produit (Blue Shoes) au panier
   Puis je vois le produit ajouté dans le panier
   ```
  ✴️ Commander un produit
  ```
  En tant qu'un visiteur du site
  J'ajoute un produit au panier
  Je vais à la page de vérification
  je saisis mes données de carte bancaire
  Je passe la commande de mon produit
  Ma commande est effectuée avec succès
  ```
<br/>

#### 🛠️Création d'un test

🪙 Ajout de nouveaux scénarios de test

* Dans le repertoire ⚠️Features, ouvrir le feature file où l'on souhaite ajouter des scénarios.
 ```
  📌features
   🔸add_to_cart: rajouter des scénarios pour l'ajout d'un produit au panier
   🔸guest_place_an_order: rajouter des scénarios pour procéder au paiement d'un produit
 ```

🪙 Rédiger le scénario ajouté en Gherkin, comme suit :
``` 
  📌Example
    🔸Scenario: Add one quantity from Store
        Given I'm on the Store Page
        When I add a "Blue Shoes" to the cart
        Then I should see 1 "Blue Shoes" in the cart
```

🪙Création des `steps definitions`
```
  📌steps :  
    Lancer un run du feature file crée :  
    🔸un squelette des étapes manquantes s'affichera dans la console, ajoutez ces fonctions au fichier "StepDef".
```

🪙Rédaction des fonctions objets `Page Objects`

* Dans ce framework, nous utilisons le modèle ⚠️Page Object et ⚠️ Page Factory. </br>
* vous pouvez soit ajouter vos scripts de tests dans les pages objects déjà présentes
  ou en créer des nouvelles selon la page concernée par le scénario à exécuter.</br>
    * ex : Si vous voulez ajouter au panier un produit qui se trouve sur la page `Men`
      de l'[ecommerce](https://askomdch.com/product-category/men/), alors vous devrez ajouter
      un `Page Object` pour cette page et les autres et pour toutes les autres pages concernées par le scénario en question.

    * Et définir les `locators` des éléments d'interface utilisateurs (IU) présents sur cette page ou les autres concernant le scénario à exécuter
    * puis définir les actions à effectuer sur ces éléments.
```
 🔸 BasePage.java
    ➡️ /src/test/java/bdd/automation/pages/BasePage.java
    
 🔸 CartPage.java 
    ➡️ /src/test/java/bdd/automation/pages/CartPage.java
    
 🔸 CheckoutPage.java
    ➡️ /src/test/java/bdd/automation/pages/CheckoutPage.java
    
 🔸 ProductPage.java
    ➡️ /src/test/java/bdd/automation/pages/ProductPage.java    
            
 🔸 StorePage.java 
    ➡️ /src/test/java/bdd/automation/pages/StorePage.java
```

🪙Intégration des fonctions objets aux steps definitions
+ Écrivez vos scripts de test java dans les steps definitions `{@Given, @When, @Then ou @And}`
  des fichiers `CartSteps.java`, `CheckoutSteps.java`, `Customers.java`, `ProductSteps.java` et `StoreSteps.java`
  (selon les steps impliqués dans votre scénario de test) qui vont permettre de lier les pages objects aux steps des scénarios gherkin
  rédigés dans les features files ce qui permettra d'exécuter les différents scénarios.
```
 📌Ouvrir les fichier "CartSteps.java"
 ➡️ src/test/java/bdd/automation/steps/CartSteps.java
 
 📌Ouvrir les fichier "CheckoutSteps.java"
 ➡️ src/test/java/bdd/automation/steps/CheckoutSteps.java
 
 📌Ouvrir les fichier "Customers.java"
 ➡️ src/test/java/bdd/automation/steps/Customers.java
 
 📌Ouvrir les fichier "ProductSteps.java"
 ➡️ src/test/java/bdd/automation/steps/ProductSteps.java
 
 📌Ouvrir les fichier "StoreSteps.java"
 ➡️ src/test/java/bdd/automation/steps/StoreSteps.java
```

🟥 NB : Pour ajouter un nouveau scénario correspondant à l'une
de nos fonctionnalités déjà développées dans ce framework,
vous pouvez ajouter le tag du scénario en question dans le `tag` de
`@CucumberOptions`, `ex: @smoke` et lancer les tests pour voir le
scénario s'exécuter !</br></br>
[![smoke-test](/docs/smokTest.png "smoke-test")]()</br></br>

* voici un example de scénario gherkin (dans les features) à ajouter: </br>
  [![smoke](/docs/smok.png "smoke")]()</br>


### 🎯Comment maintenir le framework

🪙 Ajout d'un nouveau navigateur
```
 📛 Vous pouvez ⚠️ajouter le navigateur de votre choix pour lancer vos tests (Firefox ou Edge, ...).
     ➡️ src/test/java/bdd/automation/factory/DriverFactory.java.
     
 📛 Ajoutez les lignes suivantes dans le fichier pour ajouter navigateur de votre choix:
    🔆Opera:
      🔸WebDriverManager.operadriver().setup();
      🔸driver = new OperaDriver();
    🔆Edge:
      🔸WebDriverManager.edgedriver().setup();
      🔸driver = new EdgeDriver();
    🔆Firefox:
      🔸WebDriverManager.firefoxdriver().setup();
      🔸driver = new FirefoxDriver();
    🔆Safari:
      🔸WebDriverManager.safaridriver().setup();
      🔸driver = new SafariDriver();

 📛 Vous pouvez aussi ajouter des scénarios {en suivant les étapes de ⚠️création d'un test}:
    ➡️ src/test/resources/bdd.automation/features
```

### 🎯Comment déboguer le framework
```
💡 Si vous rencontrez une erreur de ⚠️build Failed❌ 
```
* Pour résoudre tous ces problèmes, relancez de nouveau les tests !
```
 ➡️ Puis faîtes un [build project] {Dans l'onglet Build d'Intellij}
```
