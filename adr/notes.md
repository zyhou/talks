# Communicating and documenting architectural decisions

Documenter, communiquer et prendre, des décisions architecturales est l'une des choses les plus difficiles à faire, en particulier dans cette nouvelle ère d'architecture "agile". L'époque où les architectures figé, basé sur des technologies approuvées est révolue. Au lieu de cela, nous avons des équipes agiles qui s'appuient sur des techniques d'architecture émergentes et les dernières langages à la mode. Comment maîtriser cet environnement et s'assurer que ce qui est fait est documenté et communiqué à l'ensemble de l'organisation?

## Le Problème

Vous avez regardé un bout de code, de configuration ou autre choses et vous vous êtes dit: pourquoi avons-nous fait cela? Je sais que chaque développeur a dû se poser au moins une fois dans sa vie cette question. Vous regardez quelque chose qui a été fait (peut-être que vous l'avez fait!), Et vous ne savez pas pourquoi cela a été fait de cette façon.

Dans notre travail, nous prenons constamment des décisions qui impacte l'architecture. Ces décisions peuvent avoir un impact important comme choisir entre React vs Angular, grafana vs kibana. Mais aussi des décisions banal comme est-ce qu'on met une pagination ou un scroll infini sur cette page. De plus ces décisions peut être prise par une seule personne ou par l'équipe.

Dans tous les cas, même les décisions qui paraissent simples au moment où elles sont prises peuvent ne plus l’être quelques mois voire quelques années plus tard. C’est particulièrement vrai lorsque les équipes changent rapidement. En effet, les nouveaux arrivés sur le projet auront accès au code qui donnera l’état actuel de l’architecture, mais le code ne permettra pas de donner tout le contexte des décisions prises sur le projet.

La plupart d'entre nous font un excellent travail et réfléchissent soigneusement à ces décisions: Prendre en compte tous les avantages et les inconvénients des nombreuses options. Discuter de ces options avec l'équipe. Et ensuite implémenter la solution. Peut-être que nous allons mettre à jour l'user story, la documentation avec certaines des informations qui ont conduit à la décision, généralement cette partie pose problème parce qu'on perd le contexte de la décision.

Sur cette partie nous ne sommes pas bon, il faut

-   Socialiser (partager) ces décisions à toute l'équipe (celui qui a participé à la discussion a le contexte, tout le monde n'a pas cette chance!)
-   Enregistrer les décisions et encore plus important, avoir le contexte derrière les décisions de manière à ce que n'importe qui ou quelqu'un qui vient de rejoindre l'équipe puisse regarder en arrière et comprendre pourquoi la décision a été prise et quels sont les facteurs qui mené à prendre cette décision.
-   On perd le contexte

### Pas assez documenté

Trop souvent, les décisions ne sont pas assez documenté, si elles le sont elle se trouve dans la documentation actuel perdu dans un repertoire partagé

## Et un wiki?

Beaucoup de gens utilisent des wikis pour essayer de documenter ces types de décisions, ce qui est mieux que rien. Mais, il y a un décalage (généralement) entre le code et le wiki, et dans la plupart des entreprises, les wikis sont l'endroit où les documents vont mourir.

### Pour moi une bonne documentation?

-   Une information facile à trouver
-   Apporte de la valeur, utile
-   Facile à maintenir
-   Directement dans le code source

La sociabilisation est l'une des meilleures pratiques à avoir, il faut partager. Mettre la documentation directement dans la base de code où les gens travaillent tous les jours, cela la rend très pertinente.

## Solution

(http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions)
Les ADR sont une solution pour enregistrer et communiquer ces décisions.

### C'est quoi un ADR ?

-   Léger basée sur du texte, généralement écrite en Markdown permet un rendu "joli" lorsqu'il est utilisé avec Github, Gitlab et autres.
-   Les ADR sont enregistrés avec le projet, un dossier adr à la racine de votre projet
-   Une décision par fichier, enregistré, par exemple: 0001-git-for-version-control.md

### Que contient ce fichier ?

-   Le titre est exprimé sous forme de phrases nominales simple "Git pour le controle de version", "LDAP pour l'authentification" "React pour le développement web"
-   Avec un status avec la date (proposé, accepté, déprécié)
-   Le contexte qui d'écrit les forces en jeu. Ces forces peuvent être technologiques, politiques, culturelles, basées sur des projets, etc. Il existe probablement des tensions et le contexte devrait refléter ces tensions de manière non biaisée.
-   Une décisions, le plus souvent il commence part "Nous allons ..." et ensuite la décision, ou un simplement un énoncé de la décision elle même
-   Une concéquences, chaque décision a des conséquences, bonne ou mauvaises. Encore une fois, faites attention à la langue utilisée; ce ne sont pas des jugements de valeur, ce sont des déclarations de fait, il faut être aussi proches que possible de la réalité.
-   Décideurs, qui était impliqué dans la prise de décision
-   Ajout de Références externes sur arte

### Processus de validation

-   Utiliser les PR (pull request) comme workflow, vous devez déjà surement utilisé des PR. Le code review permet de validre un PR et d'apporter un débat.
-   Les nouveaux ADR peuvent être proposé en soumettant une PR ou vient d'une discussion qui fait lieu au besoin de créer un ADR

### Les outils

Outils en ligne de commandes, https://adr.github.io/

-   Les templates
-   Des exemples
-   des cli pour plein de langages
-   des liens vers plus d'information sur les ADR

## Conseil

-   Il doit être court et précis, pas plus d'une ou deux pages.
-   Chaque ADR doit concerner une seule décisions
-   Un nouvel ADR peut remplacer un ADR précédent, ils sont immutable.
-   Ne faite pas attention aux détails - si vous ne savez pas si vous devez créer un ADR, créez-en un. ca va ouvrir le débat

## Les avantages

-   Facile à review
-   Les nouvelles personnes qui se joignent à l'équipe peuvent mieux comprendre les processus de réflexion qui mènent à l'état actuel du projet
-   Empêche les gens de répéter les péchés du passé. Combien de fois avons-nous dit "Je suis sur que nous avons regardé cela, mais je ne me souviens pas vraiment"
-   Ainsi toute l’équipe est au courant du changement qui va être fait, ce qui permet de ne pas être surpris plus tard en voyant le code.
-   La solution retenue est celle qui a fait consensus au sein de l’équipe, elle a donc acquis une plus grande légitimité.
-   Prendre des décisions sans un architecte
-   Une apportunité pour s'améliorer avec peer review, pair, coach
-   Faire une proposition sans avoir le concensus de tout le monde, la décision sera prise lors de review
-   Se souvenir d'une idée pour le future
-   s'entrainer a faire preuve de proposition

## ADRs = Goodness!

J'y vois énormement d'avantage

### ADRs are awesome but not new

-   vraiment explosé en 2011

### Pourquoi c'est populaire maintenant?

-   La culture des nouveaux développeur, ils attendent a être inclu dans les process de design de l'architecture
-   La complexité des systemes qui grandie, et la modularité que ca apporte
    -   On a besoin de plus en plus à penser à tout l'archi au global
    -   "Je ne peut pas réussir tout seule"
-   Démocratisation des décisions de l'architecture, ce n'est plus forcement les archi ou des personnes au dessus qui prennent les décisions sur le sujet
-   L'architecture s'oriente vers une transformation, avoir un coach ou un mentor et plus un poste séparé qui va prendre toutes les décisions

### Convaincu

Je pense que je vous est convaincu, n'attend pas, commencer!

### Avertissement

-   Ne soyons pas dogmatiques: L’adoption doit se baser sur la compréhension des principes. Ici comme partout, l’amélioration continue doit s’appliquer.
-   La documentation ne remplace pas la communication: Validez les ADRs en tant qu’équipe pour faciliter l’appropriation des décisions, et ne vous servez pas de documents ou de process pour masquer les dysfonctionnements de l’équipe.

### Exemple de la premiere ADR sur Arte

-   Ce qu'on aime:
    -   Toute le monde trouve ca utile ou tres utile
    -   Super utile pour l'unboarding
    -   Lecture rapide
-   Notre principal reproche:
    -   Avoir des bonnes habitutes pour écrire de la doc c'est pas simple
    -   Architecture design vs Detailed design
-   Ce qu'on aime le plus
    -   L'historique du projet
    -   Super entrainement pour améliorer ca connaissance général (nouveau pattern/outil/etc..)
