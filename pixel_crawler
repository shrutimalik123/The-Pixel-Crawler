import random

def pixel_crawler():
    # 1. Player Stats
    hp = 100
    stamina = 50
    inventory = []
    rooms_cleared = 0
    
    print("--- 🗡️ THE PIXEL CRAWLER 🗡️ ---")
    print("Survival is the only goal. How deep can you go?")

    # 2. Game Loop
    while hp > 0:
        rooms_cleared += 1
        # Procedural Event Generation
        event = random.choice(["Monster", "Loot Chest", "Empty Hallway", "Trap"])
        
        print(f"\n📍 ROOM {rooms_cleared} | HP: {hp} | Stamina: {stamina}")
        print(f"Scenario: You encountered a {event}!")

        # 3. Decision Logic
        if event == "Monster":
            action = input("Do you [F]ight (-20 Stamina) or [R]un (-10 HP)? ").lower().strip()
            if action == 'f':
                if stamina >= 20:
                    stamina -= 20
                    print("⚔️ You defeated the monster!")
                else:
                    damage = random.randint(15, 30)
                    hp -= damage
                    print(f"😰 Out of stamina! The monster mauled you for {damage} HP.")
            else:
                hp -= 10
                print("🏃 You escaped, but took some scrap damage.")

        elif event == "Loot Chest":
            item = random.choice(["Health Potion", "Stamina Snack", "Rusty Key"])
            print(f"🎁 Found: {item}!")
            inventory.append(item)
            # Auto-use items for simplicity
            if item == "Health Potion": hp = min(100, hp + 20)
            if item == "Stamina Snack": stamina = min(50, stamina + 20)

        elif event == "Trap":
            damage = random.randint(5, 15)
            hp -= damage
            print(f"🪤 SNAP! You stepped on a pressure plate. -{damage} HP.")

        else:
            print("🕯️ A quiet moment. You recovered 5 Stamina.")
            stamina = min(50, stamina + 5)

        # 4. Death Check
        if hp <= 0:
            print(f"\n💀 YOU DIED. You cleared {rooms_cleared} rooms.")
            break
        
        # Choice to keep going
        cont = input("\n[Enter] to move to the next room, [Q] to retire: ").lower().strip()
        if cont == 'q':
            print(f"🏹 You retired to the village. Total rooms cleared: {rooms_cleared}")
            break

pixel_crawler()
