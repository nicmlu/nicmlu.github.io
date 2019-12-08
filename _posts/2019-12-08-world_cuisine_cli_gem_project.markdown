---
layout: post
title:      "World Cuisine CLI Gem Project "
date:       2019-12-08 18:29:33 +0000
permalink:  world_cuisine_cli_gem_project
---


![alt: table with food spread and hands passing dishes](https://eatforum.org/content/uploads/2018/05/table_with_food_top_view_900x700.jpg)

My first real coding project, the World Cuisine CLI Gem, was no easy feat! With a little determination, a clear vision and a looming deadline, I was able to complete the first assessment (of many) in my transition to tech journey. 

> "To execute successfully, it is essential to have a strong emotional stake in the outcome. Without a compelling vision, you will discover there is no reason to go through the pain of change."                                         -Moran, Brian P.. The 12 Week Year (p. 19). Wiley. 



While working through this project, I was inspired by a recent read, ["The 12 week year"](https://12weekyear.com/), by Brian P. Moran. The author explains that having a clear vision is essential to working as optimally as possible. With a clear vision, one is able to easily identify the disciplines and steps needed to do on a weekly and daily basis. This mindset helped me overcome some serious procrastination and imposter syndrome but also led me to change my api four times! However, I am proud of what I've been able to create. 


So let me tell you all about it.... 


What does it do?

My project extracts data from the [Meal DB API](http://) and displays it to the user. The program lists 24 countries from around the world, from which, the user can learn more information about the recipes from that area. After selecting a country, the user is provided with a list of meals and given the option to learn more a specific recipe. Once the recipe is selected, the program pulls up the recipe ingredients, ingredient measurements and cooking instructions. This is a must-have for any food lovers who are looking for their next meal inspiration from anywhere in the world! 


The process

This gem was built using Ruby. It consists of four main classes that interact with each other - the CLI class that the user interacts with, the API class that extracts data from the API, the Area class that creates instances of the available areas upon search and the Meal class that creates instances of all meal options and provides the information for them. 

One of the most difficult parts of the coding process was scraping and displaying the recipe ingredients and ingredient measurements. Because each meal had a different amount of ingredients, each object instance created would have "null" or empty values, which would need to be ignored by the scraper. We would not want to print "null" if there is no ingredient value in the key, value pair. 

In this case, the best option was to write a conditional statement that would only puts out the ingredient if one was listed. To code, I simply created an unless conditional statement that would interpolate the ingredient value and print it to the terminal unless it was "null" or empty. This worked perfectly! 

` puts "#{selected_meal_info[0]["strIngredient1"]}: #{selected_meal_info[0]["strMeasure1"]}" unless selected_meal_info[0]["strIngredient1"] == "null" || selected_meal_info[0]["strIngredient1"] == ""
`

Happy and content with my final code, I eagerly had my husband test it out. By doing this, I was reminded of the importance of letting others test your code. While the gem was fully funtional, during the test, I uncovered a glitch when the user entered yes to search for another reciepe. This glitch would rerun the code and would create new area objects. However, the new area objects would be duplicates of the original menu. This meant that upon second search, the users menu of areas and recipe options would double with a duplicate of each. 

To correct my this, the code was revised in the initialization process. The revision would include functionality to clear the initial area objects and in essence restart the search. Here was the final code solution: 

```
def self.clear_all
        @@all.clear
    end
```

This simple soultion allowed me to call the clear method on each the Area and Meal classes and delete previously created objects upon initialization of a new search. When learning to code, you learn quickly that often times the most difficult bugs to fix require the simpliest code. 


Future Versions

While I am proud of the first version, this gem has many potential areas where functionality can be built out to expand on its features. One such area could be in the Meal class, where functionality can be added to allow the user to save favorite recipes into a recipe box to reference later. 
 


