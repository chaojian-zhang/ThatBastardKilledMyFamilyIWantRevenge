# That Bastard Killed My Family I Want Revenge

Welcome! This contains brief documentation of the project.

The game logic is extremely simple. The player controls an aircraft and is supposed to kill all the barriers and enemies to pass each level. There will be pickups and boosts and weapon upgrades. 

This game contains no saving/loading mechanism and it is intended to be played like an arcade game.

## Level Loading

A scaffold of folder structure and some initial loading and setup logic is templated but not yet filled in with details.

Levels are dynamically loaded into main scene (main.collection) by gamemanager.script.

This design uses a MVVM-like development model (which I am not sure what it actually means; but we are not doing MVC anyway), separating views from controls from objects.

The inputs we are dealing with are mainly keyboard buttons and touch and click.

## Player Movement

Players control their aircraft moving within viewable screen area. The aircrafts physical location doesn't exceed viewable boundary. Instead, the whole level scrolls down along with everything in it. Thus **levels need to have a blank root object** so it's parent of everything else in the level when it's loaded.

## Enemies

Enemies are defined by movement patterns and attack modes, each controlled by a separate script (defined separate properties; being as light-weight as possible); For more advanced enemies they might be controlled by one dedicated script.

# Git Workflow

This folder will be shared among programmers and artists. For efficient and conflict free team development, follow below guidalines:

1. Pull before you starting editing
2. Make file updates using git commands (or use Github Desktop), especially when **renaming files**
3. Make minor changes and commit often; Don't commit extremely large temporary files (e.g. PSD files); Do write git **messages** summarizing your changes
4. Resolve all conflicts and make sure everything runs before you commit (otherwise use `git stash` to temporarily save unusable parts locally before committing changes)
5. Notice current repository is around 2Mb, let's making it less than 40Mb for the final executable (excluding .git history)

I will post weekly release updates on Github, along with a brief summary in our communication group.

## Cool Git Syntax to use with Defold

--- Below are some cool Markdown syntaxes put here for reference purpose
1. [build and run](defold://build) the game. (You can also select <kbd>Project ▸ Build</kbd> in the menu)
2. Image: <img src="doc/local_inage.jpg" width="800">
3. File ["player.script"](defold://open?path=/scripts/player.script) with the menu item <kbd>File ▸ Open Asset...</kbd>
4. More images  <img src="doc/open_asset.png" srcset="doc/open_asset@2x.png 2x">
5. Type the word "enemy" to searching among all the available assets and select the file ["spaceship.script"](defold://open?path=/spaceship/spaceship.script). Click the button <kbd>Open</kbd> to open the file in the Lua code editor.
6. Code: 
   ```lua
   local max_speed = 60
   ```
7. Reload the script file into the running game with <kbd>File ▸ Hot Reload</kbd>.
8. Add a new game object file. Right-click the "stars" folder in the *Assets* view and select <kbd>New... ▸ Game Object</kbd>. Name the new file "bonus_star". (The editor will automaticaly append a file type suffix so the full name will be "bonus_star.go".)
8. ![](doc/add_component.png)
9. Set the *Image* property to "stars.atlas" by using the browse-button (<kbd>...</kbd>) The atlas contains the graphics for the bonus star.

4. Add a *Collision Object* component to the game object. Right click the root "Game Object" item in the *Outline* view and select <kbd>Add Component ▸ Collision Object</kbd>. This lets the bonus stars collide with other game objects, like the player's space ship. This is necessary so the player can gather the bonus stars as well as ordinary stars.

5. Click on the "collisionobject" item in the *Outline* view to show its properties.

6. In the *Properties* view, set the *Type* property to "Kinematic". This means that the collision object will follow the game object it belongs to.

7. Right click "collisionobject" in the *Outline* view and select <kbd>Add Shape ▸ Sphere</kbd>. Any shape(s) you add to the collision object defines its boundary as far as collisions are concerned.

8. Select the *Scale Tool* in the toolbar and use the scale handle to resize the sphere in the scene view until it reasonably covers the star. You can also edit the *Diameter* property directly in the *Properties* view.

   ![](doc/sphere_size.jpg)

9. Right click the root "Game Object" item in the *Outline* view again and select <kbd>Add Component File</kbd>, then select the script file "bonus_star.script". This script moves the bonus stars and make sure the player gets the right amount of points for catching them.
10. Check out [the documentation pages](https://defold.com/learn) for examples, tutorials, manuals and API docs.
11. Happy Defolding!

# Logistics

The game's full name is ***That Bastard Killed My Family I Want Revenge***, which will be too long for display and publishing, in which case we will use ***I, Revenge*** instead. Other recognizable names for this title are: *That Bastard*, and *My Family*

# Attributes

This game is powered by Defold game engine. Some assets are taken from tutorial and examples files.

Gratitudes to those individuals without whom this work will never be completed.
- Kenney Vleugels (www.kenney.nl) License (CC0): Space Shooter (Redux, plus fonts and sounds)

And those platforms:
- https://www.vecteezy.com Airplanes Silhouettes