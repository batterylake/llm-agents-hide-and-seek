# LLM-based Agent Hide-and-Seek Game
## Overview
Evaluate the capabilities of LLMs to devise strategies in a game of hide-and-seek through iterative play.

## Environment Structure
The environment.yaml file provides a hierarchical representation of the hide-and-seek environment. Each level in the hierarchy represents a potential hiding spot or an area containing other hiding spots.

For example:

    house:
        living_room:
            couch: 
            bookshelf:
        bedroom:
            bed:
            wardrobe:
In the example above, the house has a living room and a bedroom. The living room contains a couch and a bookshelf, while the bedroom has a bed and a wardrobe. Each innermost item (couch, bookshelf, bed, wardrobe) represents potential hiding spots.

## Search Strategies
1. Quick Search:
A quick search is a fast search method, but it doesn't guarantee finding the hider. The likelihood of discovering the hider during a quick search is less than one, and it can be set based on the game's requirements.

2. Thorough Search:
A thorough search is a detailed search method that guarantees finding the hider. However, it is more time-consuming than a quick search.

Quick Search has a default cost of 1, and Thorough Search has a default cost of 2. The default max total spend a seeker can use when devising a strategy is 4 (for example, search two locations thoroughly, search two locations quickly and one thoroughly, etc.)

## Playing the Game
1. The hider selects a spot from the environment to hide.
2. The seeker then devises a strategy using some combination of quick and thorough searches.
3. The search outcome is then determined based on the hider location, the chosen method, and the probability of success in the case of the quick search.
4. The results, including seeker strategy, hier_location, and outcome, are stored in the agent's memory

## Visualization
The results can be visualized using `viz_results`
![results viz](./images/Screenshot%202023-10-11%20133706.png)
