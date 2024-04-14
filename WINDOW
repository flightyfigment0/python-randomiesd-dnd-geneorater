import tkinter as tk
import random

window = tk.Tk()
window.title("Fantasy Adventure Game")

# Variables
number_players = tk.StringVar()


land_monsters = ['dragon', 'goblin', 'space marine', 'skeleton']
sea_monsters = ['kraken', 'mutant fish', 'siren']


D20 = [i for i in range(1, 21)]
D6 = [i for i in range(1, 7)]
D4 = [i for i in range(1, 5)]
D8 = [i for i in range(1, 9)]
D10 = [i for i in range(1, 11)]
D12 = [i for i in range(1, 13)]


lv1chest = ["old sword", "health potion", "10SP", "10 ten arrows", "short bow", "leather armour", "rope", "camel", "travler clothes", 'thieves tools', 'horse', 'a baked bean', "alastair bennet's nintendo switch"]
lv2chest = ["10gp", "longbow", "long sword", "chainmail armour", "battle axe", "fine clothes", "2 health potions", 'ring of invisablity']
lv3chest = ['great club', 'great sword', 'great axe', 'breast plate', 'bomb', '10 PP', 'can o beans']


dock_merchant_food = ['bread', 'steak', 'pork']
dock_merchant_armour = ['leather pads', 'breastplate', 'chainmail']
dock_merchant_weapons = ['shortbow', 'longbow', 'crossbow', 'shortsword', 'longsword']
dock_merchant_healing_items = ['health potion', 'antidote']
dock_merchant_weapon_extras = ['10 arrows', '10 crossbow bolts']
dock_merchant_food_price = [1]
dock_merchant_armour_price = [5, 10, 15, 20]
dock_merchant_weapons_price = [5, 10, 15, 20]
dock_merchant_healing_items_price = [5, 10]


cap_merchant_food = ['bread', 'steak', 'pork']
cap_merchant_clothes = ['fine clothes', 'travller clothes']
cap_merchant_weapons = ['shortsword', 'longsword']
cap_merchant_healing_items = ['health potion', 'antidote']
cap_merchant_food_price = ['1SP', '1']
cap_merchant_armour_price = ['5', '10', "15", '20']
cap_merchant_weapons_price = ['5', '10', '15', '20']
cap_merchant_healing_items_price = ['5', '10']


wand_merchant_food = ['bread', 'steak', 'pork']
wand_merchant_armour = ['leather pads', 'breastplate', 'chainmail']
wand_merchant_weapons = ['shortbow', 'longbow', 'crossbow', 'shortsword', 'longsword']
wand_merchant_healing_items = ['health potion', 'antidote']
wand_merchant_weapon_extras = ['10 arrows', '10 crossbow bolt']
wand_merchant_food_price = ['1SP', '1']
wand_merchant_armour_price = ['5', '10', "15", '20']
wand_merchant_weapons_price = ['5', '10', '15', '20']
wand_merchant_healing_items_price = ['5', '10']

# Function to start the game
def start_game():
    num_players = int(number_players.get())
    land_mob_spawn_button.config(state=tk.NORMAL)
    for button in dice_buttons:
        button.config(state=tk.NORMAL)
    for button in chest_buttons:
        button.config(state=tk.NORMAL)

# Functions for button actions
def land_mob_spawn(num):
    monsters = random.choices(land_monsters, k=num)
    result_text.set(" ".join(["A hostile " + m + " has appeared" for m in monsters]))

def roll_dice(dice_type):
    result = random.choice(dice_type)
    result_text.set(str(result))

def chest_loot(level):
    if level == "lv1":
        items = random.choices(lv1chest, k=random.randint(1, 3))
    elif level == "lv2":
        items = random.choices(lv2chest, k=random.randint(1, 4))
    elif level == "lv3":
        items = random.choices(lv3chest, k=random.randint(1, 2))
    result_text.set(", ".join(items))

# Number of players entry field
players_label = tk.Label(window, text="Enter number of players:")
players_label.pack()
players_entry = tk.Entry(window, textvariable=number_players)
players_entry.pack()

# Start game button
start_button = tk.Button(window, text="Start Game", command=start_game)
start_button.pack()

# Land mob spawn button
land_mob_spawn_button = tk.Button(window, text="Spawn Land Mob", state=tk.DISABLED, command=lambda: land_mob_spawn(int(number_players.get())))
land_mob_spawn_button.pack()

# Dice roll buttons
dice_buttons_frame = tk.Frame(window)
dice_buttons_frame.pack()
dice_buttons = []
for dice_type in [D20, D6, D4, D8, D10, D12]:
    button = tk.Button(dice_buttons_frame, text="Roll D" + str(dice_type[-1]), state=tk.DISABLED, command=lambda d=dice_type: roll_dice(d))
    button.pack(side=tk.LEFT)
    dice_buttons.append(button)

# Chest loot buttons
chest_buttons_frame = tk.Frame(window)
chest_buttons_frame.pack()
chest_buttons = []
for level in ["lv1", "lv2", "lv3"]:
    button = tk.Button(chest_buttons_frame, text="Open " + level + " Chest", state=tk.DISABLED, command=lambda l=level: chest_loot(l))
    button.pack(side=tk.LEFT)
    chest_buttons.append(button)

# Result display
result_text = tk.StringVar()
result_label = tk.Label(window, textvariable=result_text)
result_label.pack()

window.mainloop()
