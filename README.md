# monster-fighter
work
import random
import DMGuide.monster_manuel
import DMGuide.dicebag
import main 

fighter_turn = True
monster_health = DMGuide.monster_maunal.DireRat.health
fighter_health = main.fighter.health

def player_turn(monster_health):
	print(f'you take a swipe at {DMGuide.monster_manual.DireRat.monster_name}')
	fighter_roll = DMGuide.dicebag.d20 + main.fighter1.strength
	monster_roll = DMGuide.dicebag.d20 + DMGuide.monster_manual.DireRat.agility
	outcome = (fighter_roll - monster_roll)
	print(f"fighter's strangh and attack roll: { fighter_roll}'")
	print(f" the {DMGuide.monster_manual.DireRat.monster_name} agility roll: {monster_roll}")
	if outcome >= 1:
		print(f" the dameg{DMGuide.monster_manual.DireRat.monster_name} for {outcome} points of dameg")
		monster_health = outcome
		if monster_health >= 1:
			print(f"the {DMGuide.monster_manual.DireRat.monster_name}'s you health is: {monster_health}'")
		elif monster_health <= 0:
			print(f" you struck a killing blow to the {DMGuide.monster_manual.DireRat.monster_name} is dies ")
			return (monster_health)
		else:
			print(f"the{DMGuide.monster_manual.DireRat.monster_name} barlye missed")
			
def monster_turn(fighter_health):
	monster_roll = DMGuide.dicebag.d20 + DMGuide.monster_manual.DireRat.strength
	ftghter_roll = DMGuide.dicebag.d20 + main.fighter1.agility
	outcome = monster_roll - fighter_roll
	print(f"{DMGuide.monster_manual.DireRat.monster_name} strength roll: {monster_roll}")
	print(f"{main.fighter1.char_name} agility roll: {fighter_roll}")
	if outcome >=1:
		print(f" the {DMGuide.monster_manual.DireRat.monster_name} for {outcome} points of damage")
		fighter_health = outcome
		if fighter_health >= 1:
			print(f"{DMGuide.monster_manual.DireRat.monster_name} the health is {monster_health}")
		elif fighter_health <= 0:
			print(f"the {DMGuide.monster_manual.DireRat.monster_name} hit hard.")
		elif outcome < 1:
			print(f" the  {DMGuide.monster_manual.DireRat.monster_name} attacked and missed ")
		


def room_description():
	print('''
	there's a room that  you can search or continue walking down the hall. type in (r) for room or(l) to walk down the hall
	
	''' )
	
	
def creature_encounter():
	creature = random.choices('rat')
	if creature == 'rat':
		print(""" a rat appars! """)
		print(f'''the {DMGuide.monster_manual.DireRat.monster_name} has 
			{DMGuide.monster_manual.DireRat.monster.agility} agility
			{DMGuide.monster_manual.DireRat.monster.health} health
			{DMGuide.monster_manual.DireRat.monster.strength} strength''')
		
		engage = input('''do you want to fight the Dire Rat or run 
		type  (f) for fight or (R) for run ''')
		while engage.lower() == 'f':
			if fighter_agilty >= DMGuide.monster_manual.DirRat.agility and fighter_turn == True:
				print(f' you are a little quicker than the {DMGuide.manuel.DirRat.monster_name}')
				player_turn()
				print(f"the{DMGuide.monster_manual.DireRat.monster_name} health dropped to {monster_health}")
			else:
				print(f"you find that the {DMGuide.monster_manual.DireRat.monster_name} is faster ")	
				monster_turn()
				
		if engage.lower() == 'r':
			print("you run ")
			leave()
