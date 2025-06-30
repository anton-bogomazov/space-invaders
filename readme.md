Entities

Invader
- Position
- Velocity
- Descent Step
- Health Points
- Sprite
- Bullet Sprite
- Bullet Velocity
- Shot cooldown (random)

Spaceship
- Position
- X Speed/Step
- Healths
- Sprite
- Bullet Sprite
- Bullet Velocity
- Shot cooldown (fixed)

Space:
- Spaceship
- Spaceship Bullets
- Invaders
- Invader Bullets

Rules:
- When S bullet collides with invader, destroy invader (if invaders hp 0 - do not render it and do not calculate collisions)
- When Inv bullet collides with S - reduce Health (if 0 - end game)
- When Inv collides S - end game
- When Inv collides space 'edge' - descend it
- Invs shoot randomly

Program Structure:
- Game Loop
  - Handle left, right and space to control spaceship
  - Check collisions/rules/etc and update positions on tick
  - Render space by placing sprites on the empty scene
- Cons initial space
  - Place N Invaders evenly in the top of the scene
  - Place Spaceship in the bottom
- Operators:
  - Reconstruct spaceship/invader in the new position
  - Destroy spaceship/invader
  - Spawn bullet by ss/inv