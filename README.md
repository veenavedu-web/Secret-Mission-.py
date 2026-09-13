import sys
import time


def print_slow(text, delay=0.015):
  """Prints text line by line for an awesome secret agent story feel."""
  for line in text.split('\n'):
    print(line)
    time.sleep(delay)


def get_choice(options):
  """Gets a valid choice A, B, or C from the player."""
  while True:
    choice = input('\n👉 Enter your choice (A, B, or C): ').strip().upper()
    if choice in options:
      return choice
    print('❌ Invalid entry! Please type A, B, or C.')


def play_game():
  print('=' * 70)
  print('  🕵️‍♂️ SECRET AGENT ISHAN: OPERATION GOLDEN CHIP 🕵️‍♂️')
  print('=' * 70)
  print('\nWelcome, Agent Ishan! Your secret agent mission is starting...\n')

  score = 0
  health = 100
  inventory = [
      '👓 X-Ray Specs',
      '⌚ Grappling Hook Watch',
      '💨 Smoke Bomb Capsule',
  ]

  # ------------------------------------------------------------------
  # LEVEL 1: THE VOLCANIC FORTRESS
  # ------------------------------------------------------------------
  print_slow('\n🌋 LEVEL 1: INFILTRATING THE VOLCANIC FORTRESS')
  print_slow(
      "Mission: Break into Dr. Shadow's volcano base and retrieve the Golden"
      ' Microchip!'
  )
  print_slow(f"🎒 Initial Gear: {', '.join(inventory)}\n")

  # Level 1 - Scene 1
  print_slow('--- Scene 1: The Fortress Gates ---')
  print_slow(
      'You arrive at the island. Heavy guard towers cover the front gate.'
  )
  print_slow(
      'Options:\n [A] Front Security Gate (Use Smoke Bomb)\n [B] Ventilation'
      ' Shaft (Use Grappling Hook Watch)\n [C] Sea Cave Entrance (Swim'
      ' underwater tunnel)'
  )

  choice = get_choice(['A', 'B', 'C'])
  if choice == 'C':
    print_slow(
        '\n✅ PERFECT MOVE! You swim silently through the dark sea cave and'
        ' surface inside the submarine dock unnoticed!'
    )
    score += 100
  elif choice == 'B':
    print_slow(
        '\n⚠️ You grapple up to the air vent! Sparks fly, but you manage to'
        ' squeeze inside and reach the dock!'
    )
    score += 75
  else:
    print_slow(
        '\n⚠️ The guards spot your smoke bomb! You dive into the sea cave just'
        ' in time to escape!'
    )
    score += 50
    health -= 10

  # Level 1 - Scene 2
  print_slow('\n--- Scene 2: The Blast Door ---')
  print_slow(
      'A heavy steel blast door blocks your path, guarded by floating robotic'
      ' drones.'
  )
  print_slow(
      'Options:\n [A] Use X-Ray Specs to scan key fingerprints\n [B] Use'
      ' Grappling Hook Watch to crawl over ceiling pipes\n [C] Drop a Smoke'
      ' Bomb Capsule to rush the door'
  )

  choice = get_choice(['A', 'B', 'C'])
  if choice == 'A':
    print_slow(
        '\n✅ EXCELLENT HACK! Your X-Ray Specs reveal glowing fingerprints'
        ' 4-7-9! The blast door slides open!'
    )
    score += 100
  elif choice == 'B':
    print_slow(
        '\n⚠️ You crawl over the pipes! A drone almost sees you, but you drop'
        ' down safely behind the door!'
    )
    score += 75
  else:
    print_slow(
        '\n⚠️ Smoke fills the hallway! Drones fire stun lasers, but you punch'
        ' the code and slip inside!'
    )
    score += 50
    health -= 15

  # Level 1 - Scene 3
  print_slow('\n--- Scene 3: The Secret Vault ---')
  print_slow('The Golden Microchip floats inside a laser-ringed glass case!')
  print_slow(
      'Options:\n [A] Sky Thief (Grappling hook to ceiling)\n [B] Smoke Screen'
      ' (Throw smoke bomb)\n [C] Laser Trick (Use X-Ray Specs to adjust optical'
      ' mirrors)'
  )

  choice = get_choice(['A', 'B', 'C'])
  if choice == 'C':
    print_slow(
        '\n✅ GENIUS MOVE! You align the mirrors to bend the lasers'
        ' harmlessly! You snatch the Golden Microchip!'
    )
    score += 100
  elif choice == 'A':
    print_slow(
        '\n⚠️ You snag the chip from above, but trigger a low-laser wire on'
        ' your way out!'
    )
    score += 75
  else:
    print_slow(
        '\n⚠️ Smoke triggers emergency sirens! You grab the chip and sprint for'
        ' the exit!'
    )
    score += 50
    health -= 15

  print_slow(
      f'\n🏆 LEVEL 1 COMPLETE! Score: {score}/300 | Health: {health}%'
  )

  # ------------------------------------------------------------------
  # LEVEL 2: THE SPACE STATION HEIST
  # ------------------------------------------------------------------
  new_gear = [
      '🧲 Magnetic Gravity Boots',
      '⚡ EMP Wrist Laser',
      '🚀 Space-Suit Thruster Pack',
  ]
  inventory.extend(new_gear)
  print_slow('\n🛰️ LEVEL 2: THE SPACE STATION HEIST')
  print_slow(
      'Mission: The chip is locked! Retrieve the Cosmic Activation Key from'
      ' Starlight Alpha!'
  )
  print_slow(f"🎒 Upgraded Gear: {', '.join(inventory)}\n")

  # Level 2 - Scene 1
  print_slow('--- Scene 1: The Airlock Entrance ---')
  print_slow('High-voltage energy shields block the shuttle airlock.')
  print_slow(
      'Options:\n [A] The Hull Walk (Magnetic Gravity Boots)\n [B] EMP Hack'
      ' (Fire EMP Wrist Laser at sensor panel)\n [C] Thruster Blast (Rocket'
      ' into ventilation)'
  )

  choice = get_choice(['A', 'B', 'C'])
  if choice == 'B':
    print_slow(
        '\n✅ BZZZZT! Your EMP laser short-circuits the shields, and you glide'
        ' smoothly into the station!'
    )
    score += 100
  elif choice == 'A':
    print_slow(
        '\n⚠️ Magnetic boots stick to the hull! You walk around to the hatch'
        ' and slip inside!'
    )
    score += 75
  else:
    print_slow(
        '\n⚠️ Thrusters blast loud! You rocket through the vent just as the'
        ' doors slam shut!'
    )
    score += 50
    health -= 10

  # Level 2 - Scene 2
  print_slow('\n--- Scene 2: The Zero-Gravity Reactor Core ---')
  print_slow(
      'The Activation Key floats surrounded by spinning red lasers in zero'
      ' gravity.'
  )
  print_slow(
      'Options:\n [A] Magnetic Wall-Walk\n [B] Thruster Slalom (Zero-G rocket'
      ' boost past lasers)\n [C] EMP System Reboot'
  )

  choice = get_choice(['A', 'B', 'C'])
  if choice == 'B':
    print_slow(
        '\n✅ WHOOSH! You slalom zero-g style past the spinning lasers and'
        ' snatch the Key!'
    )
    score += 100
  elif choice == 'C':
    print_slow(
        '\n⚠️ EMP temporarily freezes the lasers! You snatch the key right'
        ' before they restart!'
    )
    score += 75
  else:
    print_slow(
        '\n⚠️ Walking the wall takes extra time, but you reach over and grab'
        ' the Key!'
    )
    score += 50

  # Level 2 - Scene 3
  print_slow('\n--- Scene 3: Boss Battle vs MECHA-SHADOW ---')
  print_slow(
      'MECHA-SHADOW drops into the chamber as the self-destruct timer counts'
      ' down!'
  )
  print_slow(
      'Options:\n [A] EMP Overload (Blast chest reactor)\n [B] Magnetic Slam'
      ' (Pull metal crates)\n [C] Thruster Rocket Escape'
  )

  choice = get_choice(['A', 'B', 'C'])
  if choice == 'A':
    print_slow(
        "\n✅ CRITICAL HIT! BZZZZT! You overload MECHA-SHADOW's power core"
        ' and rocket out before explosion!'
    )
    score += 100
  elif choice == 'B':
    print_slow(
        '\n⚠️ Metal crates crush the robot! You ignite thrusters and escape'
        ' into space!'
    )
    score += 75
  else:
    print_slow(
        "\n⚠️ You rocket past the robot's laser cannons and barely make it to"
        ' your shuttle!'
    )
    score += 50
    health -= 10

  print_slow(
      f'\n🏆 LEVEL 2 COMPLETE! Score: {score}/600 | Health: {health}%'
  )

  # ------------------------------------------------------------------
  # LEVEL 3: ARCTIC SNOWMOBILE CHASE
  # ------------------------------------------------------------------
  inventory.append('🏎️ Rocket-Boosted Stealth Snowmobile')
  print_slow('\n🏔️ LEVEL 3: THE ARCTIC SNOWMOBILE CHASE')
  print_slow('Mission: Stop Dr. Shadow in a high-speed snowy mountain race!')
  print_slow(f"🎒 Final Gear: {', '.join(inventory)}\n")

  # Level 3 - Scene 1
  print_slow('--- Scene 1: The Avalanche Pass ---')
  print_slow('Enemy snowmobiles try to ram you off a steep mountain cliff!')
  print_slow(
      'Options:\n [A] Glacier Ramp Jump (Hit Nitro rocket booster)\n [B] Oil &'
      ' Ice Trap\n [C] Ice Cave Shortcut'
  )

  choice = get_choice(['A', 'B', 'C'])
  if choice == 'A':
    print_slow(
        '\n✅ VRRRROOOM! Your rocket boost launches you high over the canyon!'
    )
    score += 100
  elif choice == 'B':
    print_slow('\n⚠️ The oil slick sends 2 guards spinning out into snowdrifts!')
    score += 75
  else:
    print_slow(
        '\n⚠️ Icicles fall around you, but you blast out of the cave back onto'
        ' the trail!'
    )
    score += 50
    health -= 10

  # Level 3 - Scene 2
  print_slow("--- Scene 2: Dr. Shadow's Armored Ice Crusher ---")
  print_slow('Dr. Shadow fires his twin Freeze-Ray at you!')
  print_slow(
      'Options:\n [A] The Under-Slide\n [B] Avalanche Trigger\n [C] Frost-Ray'
      ' Hack (Reflect freeze beam back with EMP Wrist Laser)'
  )

  choice = get_choice(['A', 'B', 'C'])
  if choice == 'C':
    print_slow(
        "\n✅ BOOM! The reflected beam turns Dr. Shadow's Ice Crusher into a"
        ' solid block of blue ice!'
    )
    score += 100
  elif choice == 'B':
    print_slow(
        "\n⚠️ A huge avalanche buries Dr. Shadow's Ice Crusher under 10 feet"
        ' of snow!'
    )
    score += 75
  else:
    print_slow(
        '\n⚠️ You slide under the giant wheels and plant the sticky mine!'
        ' *KABOOM!*'
    )
    score += 75

  # VICTORY SCREEN
  print_slow('\n' + '=' * 70)
  print_slow('🎉 CONGRATULATIONS AGENT ISHAN! MISSION ACCOMPLISHED! 🎉')
  print_slow(
      'You saved the world, defeated Dr. Shadow, and recovered the Golden'
      ' Microchip!'
  )
  print_slow(f'🌟 FINAL AGENT SCORE: {score} / 800 POINTS')
  print_slow(f'❤️ FINAL AGENT HEALTH: {health}%')
  print_slow('=' * 70 + '\n')


if __name__ == '__main__':
  while True:
    play_game()
    again = (
        input('Do you want to play again, Agent Ishan? (YES / NO): ')
        .strip()
        .upper()
    )
    if again not in ['YES', 'Y']:
      print(
          '\nThanks for playing! Stand by for future missions, Agent Ishan!'
          ' 🕵️‍♂️🚀\n'
      )
      break
