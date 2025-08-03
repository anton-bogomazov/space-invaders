# Space Invaders

I did this project to challenge my design tools in conditions of high uncertainty. I had never written in LISP-like languages before and studied Racket for about a week while working on this project. It’s also only my second game (the first was Wolfenstein, which I made at École 42), so I’m not very familiar with game development patterns and best practices.

Overall, it turned out pretty well!
I’d work on generalizing the components and making the configuration cleaner. Right now, all variables are global - which is acceptable - but introducing difficulty levels or game levels in general would require dynamic gameplay configuration.

I’d also like to modularize the project. Managing code in a single file without proper refactoring tools is cognitively very difficult.

P.S. I’d love to add more features, but working with DrRacket has been a very frustrating experience!

![Gameplay](./demo.gif)

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
