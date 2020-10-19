# monster-fighter
work
from  DMGuide.room1 import room_description
from DMGuide.character_cration import creat_fighter

class BasicCharacter:
	def __init__(self,char_name, strength, agility, health):
		self.monster_name = char_name
		self.strength = strength
		self.agility = agility
		self.health = health

confirm_stats = True
head_in = True
re_roll_times = 1

def char_stats(self):
	print(f'''
	{self.char_name} is a fighter 
	Strength: {self.strength}
	gility: {self.agility}
	health: {self.health }
	''')
print('''
welcome Great adventuer!
 if you like to create a character hit M to start making your fighter 
''')
make_character = input(" > ")

if make_character.lower() == 'ok':
	strength, agility, health = creat_fighter()
print(f''' 
strength is: {strength}
agility is: {agility}
health is: {health}
''')
while confirm_stats == True and re_roll_times <=3:
	if re_roll_times >= 1 and re_roll_times < 3:
		print(f''' warinning, you have {4 - re_roll_times} re-roll left''' )
	elif re_roll_times >=3:
		print('this is your last re-roll. ')
	ok = input(f""" OK to conute. if you want to re-roll to see if you get better stats tpye in R. !!warnning!! once you re-roll you cannot use your previous roll """ )
	if ok.lower() == 'ok':
		confirm_stats = False 
	else:
		strength, agility, health = creat_fighter()
		print(f''' 
strength is: {strength}
agility is: {agility}
health is: {health}
''')	
		re_roll_times += 1

print("OK you are almost ready ")
Char_name = input('what name would you like to use for your fighter? > ')
print(f"{Char_name} is ready for the dungeon")
fighter1 = BasicCharacter(Char_name, strength, agility, health)
print(fighter1.char_stats())

while head_in:
	ready = input("ready to go  in Y or N ")
	if ready.lower() == 'y':
		DMGiude.room1.room_description()
