# GraphQL Queries

You have learned the basics of GraphQL. Now it time to test your querying ability.

[Graphql-Pokemon](https://graphqlpokemon.favware.tech/) will be your one stop shop to answer the following questions about select pokemon. It uses [GraphiQL](https://medium.com/the-graphqlhub/graphiql-graphql-s-killer-app-9896242b2125), a tool that helps developers structure their GraphQL queries. Nitro uses GraphiQL too.

Utilize the "Docs" tab on the far right of the page to figure out the query you need to find each answer.

### Questions

1. What is the height of Nidoqueen? "height": 1.3,
{
	getPokemon(pokemon: nidoqueen reverseFlavorTexts: true takeFlavorTexts: 1) {
		height
	}
}
1. What are the weaknesses of Machop? "fairy","flying","psychic"

{
	getTypeMatchup(types: [fighting]) {
		defending{
     effectiveTypes
    }
	}
}

1. What is Ditto's special attack stat? specialattack": 48
{
	getPokemon(pokemon: ditto reverseFlavorTexts: true takeFlavorTexts: 1) {
		num
		species
		baseStats { specialattack }
	}
}
1. What is the official classification of Snorlax? (egg group is fine) "Monster"

	getPokemon(pokemon: snorlax reverseFlavorTexts: true takeFlavorTexts: 1) {
	eggGroups
	}
}

1. What is Dragonite resitant to? (bonus points for double resistance as well!)
Answer: "doubleResistedTypes": [
          "grass"
        ],
        "resistedTypes": [
          "bug",
          "fighting",
          "fire",
          "water"

Code:{
	getTypeMatchup(types: [dragon flying]) {
		defending{
     doubleResistedTypes
      resistedTypes
    }
	}
}


1. What is the catch rate of Pidgeot? base:45
   {
	getPokemon(pokemon: pidgeot reverseFlavorTexts: true takeFlavorTexts: 1){
    catchRate {
       base
    }
  }
}

1. What is Pikachu's weight AFTER they evolve? "weight": 30
{
	getPokemon(pokemon: raichu reverseFlavorTexts: true takeFlavorTexts: 1) {
		height
		weight
	}
}


1. What is Pikachu's hidden ability? "lightening Rod"
{
	getPokemon(pokemon: pikachu reverseFlavorTexts: true takeFlavorTexts: 1) {
		abilities { hidden }
	}
}
1. Where can an image of Jigglepuff be found? See below query code for result
{
	getPokemon(pokemon: jigglypuff reverseFlavorTexts: true takeFlavorTexts: 1) {
	
		sprite
		shinySprite
		backSprite
		shinyBackSprite

	}
}

answer: 
{
  "data": {
    "getPokemon": {
      "sprite": "https://play.pokemonshowdown.com/sprites/ani/jigglypuff.gif",
      "shinySprite": "https://play.pokemonshowdown.com/sprites/ani-shiny/jigglypuff.gif",
      "backSprite": "https://play.pokemonshowdown.com/sprites/ani-back/jigglypuff.gif",
      "shinyBackSprite": "https://play.pokemonshowdown.com/sprites/ani-back-shiny/jigglypuff.gif"
    }
  }
}