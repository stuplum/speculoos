#SpeculOOs ?

SpeculOOs is just a very simple Javascript Class notation, but ... CoffeeScript compliant ! 

You do not want to learn to coffeescript today, but it's interesting that your codes are compatible with coffeescript, if you finally decide to take the plunge. For example, your coffeescript classes will be able to inherit from your javascript classes

##Use

1- declare `speculoos.js` (`see index.html`)
2- write a class(es) : 

```javascript

	var Thing = Class({
		constructor : function Thing (kind) {
			this.kind = kind;
		}
	})

	var Human = Class({
		extends : Thing, /* inheritance */
		constructor : function Human (name) {
			this.name = name;
			/* Call Parent constructor */
			Human.__super__.constructor.call(this, "I AM A HUMAN");
			Human.HumanCounter += 1;
		},

		toString : function() {
			return "Hello " + this.name;
		},
		/* Static Members */
		$HumanCounter : 0,
		$getHumanCounter : function() { return Human.HumanCounter; }
	});
	
```
###Use with Javascript

```javascript

	var bob = new Human('Bob');
	console.log(bob, bob.toString(), Human.getHumanCounter(), Human.HumanCounter);

```
###Use with Coffeescript

```coffeescript

	class SuperHeroe extends Human
		constructor:(name)->
			super name

	superMan = new SuperHeroe 'Clark Kent'

	console.log superMan, superMan.toString(), SuperHeroe.getHumanCounter(), Human.HumanCounter

```

... so simple ! No ?