# ThatBastardKilledMyFamilySoIWantRevenge

Welcome! This contains brief documentation of the project.

The game logic is extremely simple. The player controls an aircraft and is supposed to kill all the barriers and enemies to pass each level. There will be pickups and boosts and weapon upgrades. 

This game contains no saving/loading mechanism and it is intended to be played like an arcade game.

## Level Loading
A scaffold of folder structure and some initial loading and setup logic is templated but not yet filled in with details.

Levels are dynamically loaded into main scene (main.collection) by gamemanager.script.

This design uses a MVVM-like development model (which I am not sure what it actually means; but we are not doing MVC anyway), separating views from controls from objects.

The inputs we are dealing with are mainly keyboard buttons and touch and click.

--- Below are some cool Markdown syntaxes put here for reference purpose
1. [build and run](defold://build) the game to try it. (You can also select <kbd>Project ▸ Build</kbd> in the menu to build and run)
2. Image: <img src="doc/run_game.jpg" width="800">

3. File ["spaceship.script"](defold://open?path=/spaceship/spaceship.script) with the menu item <kbd>File ▸ Open Asset...</kbd>
4. More images  <img src="doc/open_asset.png" srcset="doc/open_asset@2x.png 2x">
5. Type the word "space" to searching among all the available assets and select the file ["spaceship.script"](defold://open?path=/spaceship/spaceship.script). Click the button <kbd>Open</kbd> to open the file in the Lua code editor.

 <img src="doc/code_editor.png" srcset="doc/code_editor@2x.png 2x">

Code: 

   ```lua
   local max_speed = 60
   ```

   Reload the script file into the running game with <kbd>File ▸ Hot Reload</kbd>.

   1. Open the file "star.script". Either use <kbd>File ▸ Open Asset...</kbd> or find the file in the *Assets* browser in the leftmost editor pane and double click it. The file is in the folder named "star".


3. Reload the script file into the running game with <kbd>File ▸ Hot Reload</kbd>.


1. Add a new game object file. Right-click the "stars" folder in the *Assets* view and select <kbd>New... ▸ Game Object</kbd>. Name the new file "bonus_star". (The editor will automaticaly append a file type suffix so the full name will be "bonus_star.go".)

   <img src="doc/new_game_object.png" srcset="doc/new_game_object@2x.png 2x">


3. Add a *Sprite* component to the game object. Right-click the root of the *Outline* view and select <kbd>Add Component ▸ Sprite</kbd>. This allows you to attach graphics to the bonus star.

   ![](doc/add_component.png)

In the Outline view, you will see a new item called "sprite". When it is clicked, its properties are displayed in the *Properties* view below. The sprite currently has no graphics attached so you need to do that:

1. Set the *Image* property to "stars.atlas" by using the browse-button (<kbd>...</kbd>) The atlas contains the graphics for the bonus star.

2. Set *Default Animation* to "bonus_star". "bonus_star" is an animation defined in the atlas.

   ![](doc/sprite_properties.jpg)

3. A green star should now appear in the editor. Hit the <kbd>F</kbd> key or select <kbd>View ▸ Frame Selection</kbd> if the view of the star is not very good.

4. Add a *Collision Object* component to the game object. Right click the root "Game Object" item in the *Outline* view and select <kbd>Add Component ▸ Collision Object</kbd>. This lets the bonus stars collide with other game objects, like the player's space ship. This is necessary so the player can gather the bonus stars as well as ordinary stars.

5. Click on the "collisionobject" item in the *Outline* view to show its properties.

6. In the *Properties* view, set the *Type* property to "Kinematic". This means that the collision object will follow the game object it belongs to.

7. Right click "collisionobject" in the *Outline* view and select <kbd>Add Shape ▸ Sphere</kbd>. Any shape(s) you add to the collision object defines its boundary as far as collisions are concerned.

8. Select the *Scale Tool* in the toolbar and use the scale handle to resize the sphere in the scene view until it reasonably covers the star. You can also edit the *Diameter* property directly in the *Properties* view.

   ![](doc/sphere_size.jpg)

9. Right click the root "Game Object" item in the *Outline* view again and select <kbd>Add Component File</kbd>, then select the script file "bonus_star.script". This script moves the bonus stars and make sure the player gets the right amount of points for catching them.

The bonus star game object file that you have now created contains the blueprint for a game object containing graphics (the sprite), collision shapes (the collision object) and logic that moves the star and reacts to collisions (the script).

## Creating the bonus star factory

Factory Components are responsible for making sure game objects of various kind appear in the game. For your new bonus stars, you need to create a factory:

1. Open the file "factory.go" with <kbd>File ▸ Open Assets...</kbd>. This game object file contains a script and a factory.

2. Add a secondary factory component to it. Right click the root "Game Object" item in the *Outline* view and select <kbd>Add Component ▸ Factory</kbd>.

3. Set the new factory component's *Id* property to "bonus_factory".

4. Set its *Prototype* property to "bonus_star.go" with the browse-button (<kbd>...</kbd>)

   ![](doc/factory.jpg)

## Modify the factory script

The last step is to make sure the factory game object starts creating the bonus stars by modifying its script.

1. Open "factory.script" with <kbd>File ▸ Open Assets...</kbd>

2. Near the bottom of the file, change:

   ```lua
   -- component = "#bonus_factory"
   ```

   to:

   ```lua
   component = "#bonus_factory"
   ```

   This causes the bonus stars to appear roughly 20% of the time.

3. Restart the game by closing the window (or press <kbd>Escape</kbd>) to exit, then select <kbd>Project ▸ Build</kbd> from the editor menu.

   The new bonus stars will start to appear!

![](doc/run_final.jpg)

*You Win!*

Now go ahead and create more games in Defold!

Check out [the documentation pages](https://defold.com/learn) for examples, tutorials, manuals and API docs.

If you run into trouble, help is available in [our forum](https://forum.defold.com).

Happy Defolding!

----