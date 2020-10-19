# monster-fighter
work
class BasicMonster:
	def __init__(self,monster_name, strength, agility, health):
		self.monster_name = monster_name
		self.strength = strength
		self.health = health
		self.agility = agility
		
class DireRat(BasicMonster,'Dire Rat', 3, 8, 3):
	pass
