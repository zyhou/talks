# Communicating and documenting architectural decisions

Prendre, documenter et communiquer des décisions architecturales est l'une des choses les plus difficiles à faire, en particulier dans cette nouvelle ère d'architecture "agile". L'époque où les architectures figé, basé sur des technologies approuvées est révolue. Au lieu de cela, nous avons des équipes agiles qui s'appuient sur des techniques d'architecture émergentes et les dernières langues à la mode. Comment maîtriser cet environnement et s'assurer que ce qui est fait est documenté et communiqué à l'ensemble de l'organisation?

## Le Problème

"Why did we decide this?" (Pourquoi on a mis ça en place déjà ?) Vous avez regardé un bout de code, de configuration ou autre choses et vous vous êtes dit: pourquoi avons-nous fait cela? Je sais que chaque développeur a dû faire au moins une fois dans sa vie. Vous regardez quelque chose qui a été fait (peut-être que vous l'avez fait!), Et vous ne savez pas pourquoi cela a été fait de cette façon.

Dans notre travail, nous prenons constamment des décisions sur importantes sur l'architecture. Ces décisions peuvent avoir un impact important comme choisir entre React vs Angular, Node vs PHP. Mais aussi des décisions banal comme pagination vs scroll infini. Ces décisions peut être prise par une seule personne ou par l'équipe.

Dans tous les cas, même les décisions qui paraissent simples au moment où elles sont prises peuvent ne plus l’être quelques mois voire quelques années plus tard. C’est particulièrement vrai lorsque les équipes changent rapidement. En effet, les nouveaux arrivés sur le projet auront accès au code qui donnera l’état actuel de l’architecture, mais le code ne permettra pas de donner tout le contexte des décisions prises sur le projet.

La plupart d'entre nous font un excellent travail et réfléchissent soigneusement à ces décisions: Prendre en compte tous les avantages et les inconvénients des nombreuses options. Discuter de ces options avec l'équipe. Et ensuite implémenter la solution. Peut-être que nous allons mettre à jour l'user story, la documentation avec certaines des informations qui ont conduit à la décision, généralement cette partie pose problème et surtout le contexte est perdu.

Pourquoi le contexte est important ? Sans ce contexte, les gens ont deux choix lorsqu'ils sont confrontés à prendre une decision:

- faire aveuglément confiance à la décision initiale
- ou faire des changements à l'aveugle sans comprendre la motivation et les conséquences (le contexte) de la décision initiale, cela peut endommager le projet et/ou l'équipe

Sur cette partie nous ne sommes pas bon, il faut

- Socialiser (partager) ces décisions à toute l'équipe (celui qui a participé à la discussion a le contexte, tout le monde n'a pas cette chance!)
- Enregistrer les décisions et encore plus important, avoir le contexte derrière les décisions de manière à ce que n'importe qui ou quelqu'un qui vient de rejoindre l'équipe puisse regarder en arrière et comprendre pourquoi la décision a été prise et quels sont les facteurs qui mené à prendre cette décision.

### Pas assez documenté

Trop souvent, les décisions ne sont pas assez documenté, si ils le sont elle se trouve dans la documentation actuel perdu dans un repertoire

## Et un wiki?

ou mal organisé dans un wiki. Beaucoup de gens utilisent des wikis pour essayer de documenter ces types de décisions, ce qui est mieux que rien. Mais, il y a un décalage (généralement) entre le code et le wiki, et dans la plupart des endroits, les wikis sont l'endroit où les documents vont mourir.

### C'est quoi une bonne documentation pour moi ?

- Facilité de rentrer dans la doc
- Un langage qu'on connait deja
- Que ca apporte de la valeur, que c'est utile
- Facile à mettre à jour
- Quelque chose que les septique vont accepté
- Directement dans le code source

La socialisation est une des meilleures pratiques pour prendre des décisions. Les mettre directement dans la base de code où les gens travaillent tous les jours peut le rendre très pertinent pour un projet particulier.

## Solution

[Proposé part Michael Nygard](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions) les ADR (Architectural Decision Records) sont une solution pour enregistrer et communiquer ces décisions.

### C'est quoi un ADR ?

- Légère basée sur du texte, généralement écrite en Markdown permet un rendu "joli" lorsqu'il est utilisé avec Github, Gitlab et autres.
- Les ADR sont enregistrés avec le projet, un dossier adr à la racine de votre projet
- Un ADR par fichier, enregistré, par exemple: 0001-git-for-version-control.md

### Que contient ce fichier ?

- Le titre est exprimé sous forme de phrases nominales simple "Git pour le controle de version", "LDAP pour l'authentification" "React pour le développement web"
- Décideurs, qui était impliqué dans la prise de décision
- Avec un status (proposé, acceptés, deprecated)
- Le contexte, d'écrit les forces en jeu. Ces forces peuvent être technologiques, politiques, culturelles, basées sur des projets, etc. Il existe probablement des tensions et le contexte devrait refléter ces tensions de manière non biaisée.
- Une décisions, le plus souvent il commence part "Nous allons ..." et ensuite la décision, ou un simplement un énoncé de la décision elle même
- Une concéquences, chaque décision a des conséquences, bonne ou mauvaises. Encore une fois, faites attention à la langue utilisée; ce ne sont pas des jugements de valeur, ce sont des déclarations de fait, il faut être aussi proches que possible de la réalité.

### Processus de validations

- Utiliser les PR (pull request) comme workflow, vous devez déjà surement utilisé des PR. Le code review permet de validre un PR et d'apporter un débat.
- Les nouveaux ADR peuvent être proposé en soumettant une PR ou vient d'une discussion qui fait lieu au besoin de créer un ADR

## Conseil

- Il doit être court et précis, pas plus d'une ou deux pages.
- Chaque ADR doit concerner une seule décisions
- Un nouvel ADR peut remplacer un ADR précédent, ils sont immutable.
- Ne faite pas attention aux détails - si vous ne savez pas si vous devez créer un ADR, créez-en un.
- Quelques avantages d'en écrire un:
  - Faire une proposition sans avoir le concensus de tout le monde, la décision sera prise lors de review
  - Se souvenir d'une idée pour le future

### Les outils

- Outils en ligne de commandes, https://adr.github.io/
- Les templates
  - https://github.com/joelparkerhenderson/architecture_decision_record/blob/master/adr_template_by_michael_nygard.md
  - https://github.com/joelparkerhenderson/architecture_decision_record/blob/master/adr_template_by_jeff_tyree_and_art_akerman.md

## Les avantages

- Facile à review
- Cela à un impacte sur la qualité global du projet, ca pousse tout le monde vers le haut
- Les nouvelles personnes qui se joignent à l'équipe peuvent mieux comprendre les processus de réflexion qui mènent à l'état actuel du projet
- Empêche les gens de répéter les péchés du passé. Combien de fois avons-nous dit "Je suis sur que nous avons regardé cela, mais je ne me souviens pas vraiment"
- En examinant toutes les décisions qui ont été prises dans un projet, on peut avoir une idée des types de décisions qui sont prises, ce qui en soi est informatif et fournit un contexte
- Ainsi toute l’équipe est au courant du changement qui va être fait, ce qui permet de ne pas être surpris plus tard en voyant le code.
- La solution retenue est celle qui a fait consensus au sein de l’équipe, elle a donc acquis une plus grande légitimité.
- Prendre des décisions sans un architecte
- Une apportunité pour s'améliorer avec peer review, pair, coach

## ADRs = Goodness!

### ADRs are awesome but not new

- Dans un livre de 1997, architecture in practice et surtout 2011 avec documenting architecture decisions

Pourquoi c'est populaire maintenn?

- La culture des nouveaux développeur, ils attendent a être inclu dans les process de design de l'architecture
- La complexité des systemes qui grandie, et la modularité que ca apporte
  - On a besoin de plus en plus à penser à tout l'archi au global
  - "Je ne peut pas réussir tout seule"
- Démocratisation des décisions de l'architecture, ce n'est plus forcement les archi ou des personnes au dessus qui prennent les décisions sur le sujet
- L'architecture s'oriente vers une transformation, avoir un coach ou un mentor et plus un poste séparé qui va prendre toutes les décisions

### convaincu

Je vous est convaincu. Quand est-ce que je commence ? **Maintenant**

- cree un template
- cree ton premier ADR
- demande à quelqu'un de la review

### Attention

- Ne soyons pas dogmatiques: L’adoption doit se baser sur la compréhension des principes. Ici comme partout, l’amélioration continue doit s’appliquer.
- La documentation ne remplace pas la communication: Validez les ADRs en tant qu’équipe pour faciliter l’appropriation des décisions, et ne vous servez pas de documents ou de process pour masquer les dysfonctionnements de l’équipe.

### Exemple de la premiere ADR sur Arte

- Ajout de Références externes
- Ce qu'on aime:
  - Toute le monde trouve ca utile ou tres utile
  - Super utile pour l'unboarding
  - Lecture rapide
- Notre principal reproche:
  - Avoir des bonnes habitutes pour écrire de la doc c'est dur
  - Architecture design vs Detailed design
- Ce qu'on aime le plus
  - L'historique du projet
  - Super entrainement pour améliorer ca connaissance général (nouveau pattern/outil/etc..)
