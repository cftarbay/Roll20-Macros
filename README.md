This file contains some macros I wrote for the popular tabletop site, roll20.net, for a game of Fate I'm involved with. First of all are simple ones, which just cut down on the amount of typing 

Name		Code				Function
#gm			/w gm ?{Message}	Opens up a dialog box for the user to type in. Upon entering, text is sent directly to the game master.

#roll		/roll 4df			Automatically randomly generates a '+' sign, a '-' sign, or a ' ' with equal probability 4 times. Totals them up into a number. For example, a roll of '+' '+' ' ' '-' would equal 1. Used for nearly everything in the Fate system.

The purpose of having these base macros is to apply them in a way that's a little more useful. In playing, I found it frustrating to have to keep switching tabs between dice rolling and checking my character sheet for bonuses added to rolls every time I did anything. To solve this issue, I coded an ability for each of my character's skills, which would auto roll dice and add my bonuses on before displaying the result. The format is as follows:

To call an ability, one would type %{"Character_name"|"skill_name"}, with no quotes, and Character_name and skill_name replaced with the actual name of your character and the skill to roll for. This doesn't seem like much of a shortcut, but since the text box has autocomplete, one usually only needs to type '%' and the first few characters of the skill name for it to show up as the only suggestion, and enter to use the ability. 

The format of the ability script itself is simply
#r + @{"skill_name"}
with no quotes, and skill_name replaced with the name of the skill you want an ability for. For example, if my character has a skill called Resources, I would create an ability called resources, and then enter #r + @{Resources} as the ability text. To use this ability for my character, in the chat box, I would type %{my character|resources}, or usually just '%res', so it would come up as an autocomplete suggestion. This is much shorter and easier than having to manually reference scores all the time, especially in the long term.

I discovered that abilities can be nested as well. My character has an ability that grants him a bonus to investigation in special situations, which I have called 'ward'. In the text of the ability, I have %{my character|investigation} + 2. So now if I type %ward in the chat box, it will roll, add my usual investigation bonus, and then my +2 bonus for the special situation.

In conclusion, I really enjoyed creating these simple scripts to make the game more simple and intuitive for me and other players in my game. I would love to explore this system more, but unfortunately developer accounts and API aren't free to use.

You will also find in this repo a pdf manual I wrote to aid in the creation of simple macros and abilities for other players in my game who may not know how to code at all. I found the documentation on roll20 and elsewhere on the internet to be lacking, so this was my solution, so others in my game could easily use these shortcuts.