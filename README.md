import random

player_health = 100
enemy_health = 100

def player_attack():
    damage = random.randint(10, 20)
    return damage

def enemy_attack():
    damage = random.randint(5, 15)
    return damage

def display_health():
    print("Player Health:", player_health)
    print("Enemy Health:", enemy_health)

def game_over():
    if player_health <= 0:
        print("Game Over. You lost the battle.")
        return True
    elif enemy_health <= 0:
        print("Congratulations! You won the battle.")
        return True
    else:
        return False

def battle():
    while not game_over():
        display_health()
        print("1. Attack")
        print("2. Run")
        choice = input("Enter your choice (1 or 2): ")
        
        if choice == "1":
            player_damage = player_attack()
            enemy_damage = enemy_attack()
            
            print("You attacked the enemy and dealt", player_damage, "damage.")
            print("The enemy attacked you and dealt", enemy_damage, "damage.")
            
            player_health -= enemy_damage
            enemy_health -= player_damage
        elif choice == "2":
            print("You ran away from the battle.")
            break
        else:
            print("Invalid choice. Try again.")

# Start the game
print("Welcome to Battle Arena!")
print("You have encountered an enemy. Get ready to fight!")

battle()
