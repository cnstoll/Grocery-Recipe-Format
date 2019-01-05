[Grocery](https://itunes.apple.com/us/app/grocery-smart-sorting-grocery-list/id1195676848?mt=8) uses [Markdown](https://daringfireball.net/projects/markdown/syntax) to create and store recipes. This is obviously different from several structured Recipe formats that rely on JSON or XML, but it is very close in spirit to the recipes we hope to emulate: hand-written or printed recipes that have been passed down generation to generation.

# Philosophy

We want the recipes created in Grocery to stand the test of time. In the digital age that means the recipes themselves should always be accessible even if our app stops working in the future. Recipes created by Grocery and stored in Markdown can be opened and used by any text editor. Markdown has the great advantage of being human readable while providing the important structure we need to call something a recipe and not just a plain text file. Markdown was intended to make writing for the web easier, and we believe it makes writing recipes for a digital cook book easier as well.

# Characters and Content

Grocery uses the following Markdown characters for the content of a recipe:

```
# Title
## Header
- Ingredient
Step
> Note
```

The first line of the recipe should always be the title, denoted with the # character. The recipe title is also the name of the recipe file on disk.

The rest of the lines can be any type of content that fits the way the author wants to write the recipe.

# Writing a Recipe

Starting with a title, let's write a recipe for baking chocolate chip cookies. A recipe like this one includes lots of ingredients that need to be added and used at different times in a specific stages. Markdown helps us group those ingredients with the steps they're used in, and those collections of ingredients and steps into sections. Notes are pretty handy too; think of those as the handwritten notes in the margins of a cookbook.

```
# Chocolate Chip Cookies

> This is an example of a simple chocolate chip cookie recipe provided for the purpose of explaining how to write a recipe in Markdown. Some things that make sense in notes like this one are #hashtags for categorizing recipes and website URLs for pointing to where a recipe came from.

## Wet Ingredients

- Butter | 2 sticks | Softened
- Brown Sugar | 1 cup | 
- Sugar | 1/2 cup white | 

Mix together butter and sugar in a large bowl.

- Eggs | 2 | 
- Vanilla | 2 tsp | 

Mix the other wet ingredients into the butter and sugar mixture.

## Dry Ingredients

- Flour | 3 cups | 
- Baking Soda | 1 tsp | 
- Salt | 1/2 tsp | 

Sift together dry ingredients in a separate bowl.

## Cookie Dough

Mix together dry ingredients with wet ingredients slowly.

- Chocolate Chips | 1 Cup | 

> Usually I add 2 cups...just because.

Stir in ~1 cup or more of chocolate chips.

Bake at 350 for 12 minutes [Baking Cookies].

> Could be up to 15 min, or until lightly brown.

```

If you want to see how this recipe looks when its Markdown is fully rendered, check it out [here](https://github.com/cnstoll/Grocery-Recipe-Format/blob/master/Examples%20as%20Markdown%20Files/Chocolate%20Chip%20Cookies.md).

# Items

An item is an ingredient that you're going to use while cooking. It is also something you would potentially shop for in Grocery. Grocery distinguishes the title of an item from notes that describe it. We use the same pattern for ingredients in a recipe for the title of the ingredient, and notes that describe the type or amount of that ingredient.

Lines that include items are denoted with the - character. We chose the - because it's the easiest to type list character, and to simplify the number of ways a recipe can be defined.

Items are followed by two | characters. The text after the first is the item note that describes how much of an item or what type. The text after the second is the prep note that describes anything you need to do to prepare the item.

```
- Butter | 2 sticks | Softened
```

Butter is the item we're using. We need to use 2 sticks. And when we're preparing to cook we need to let the butter soften.

# Timers

Grocery can detect timers that are written as a number of seconds, minutes, hours. Some examples are:

```
30 seconds
15 mins
2 hours
1 hour and 30 minutes
```

Sometimes it's helpful to name a timer. We use the [] characters after a timer to designate its name. Here's an example from above with a name:

```
15 mins [Baking Cookies]
```

# Photos

Markdown provides support for photos with an easy to write syntax:

```
[Photo Caption](photo.jpg)
```

Grocery uses this syntax for adding photos to a recipe, but it needs a place to keep those image files. That place is provided by file "packages" that have existed on macOS and iOS since the beginning. You'll be familiar with packages (otherwise known as [NSFileWrapper](https://developer.apple.com/documentation/foundation/nsfilewrapper)'s) from things like the .app files in macOS.

A Grocery .recipepackage includes the markdown file alongside a /Photos folder containing the image files. The path component for each photo in the recipe markdown file is the name of the image in that /Photos folder.

# File Extensions

Grocery uses a .recipe file extension to designate a file as a recipe. The reason for that is that all recipes are markdown files but not all markdown files are recipes. Even though Grocery could open any markdown file, they wouldn't all make sense as recipes.

Grocery also uses a .recipepackage file extension to identify a recipe that includes images.

# Examples

We're providing a [list of example .recipe and .recipepackage files](https://github.com/cnstoll/Grocery-Recipe-Format/tree/master/Examples%20as%20Recipes) as they would be created by Grocery. Hopefully that gives you an idea of how the app creates these recipes and how you can write your own.

We're also providing a [list of these recipes as .md files](https://github.com/cnstoll/Grocery-Recipe-Format/tree/master/Examples%20as%20Markdown%20Files) that GitHub will preview with its built in Markdown renderer. This is a great way to see how useful Markdown is for viewing these recipes because of how easy they are to read even outside of the Grocery app.

# Contributors

- Designer: [Ryan Gray](https://twitter.com/ryanjagray)
- Developer: [Conrad Stoll](https://twitter.com/conradstoll)