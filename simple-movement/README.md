<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Simple Movement

<sub>[home](../README.md#user-content-gms2-npc-movement) • [next](../)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

Lets move a non playable character in the most basic way possible using GML.

<br>

---


##### `Step 1.`\|`NPCM`|:small_blue_diamond:

Now what is an NPC?  It is a <i>Non Playable Character</i> in game that moves through logic and a script and not by the controlle, mouse or keyboard.  Lets start by right clicking on **Rooms** and selecting **Create | Room** and call this room `rm_npc_movement`. *Move* it to the top of the list in **Room Order**.   

![create new room called rm_npc_movement and move to top](images/RoomMovement.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

Right click on **Objects** in the Resources menu and select **Create | Object**.  Call this new object `obj_movement_controller`. Left click on the <kbd>Add Event</kbd> button and select a **Draw | Draw** event.

![add obj_movement_controller and add draw event](images/ObjMovementController.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`NPCM`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now lets create two boxes that the square will start and end at. We have a new function to look at: `draw_rectangle(x1, y1, x2, y2, outline)`. In this case x1,y1 are the top left corner in room pixels and x2, y2 are the bottom right.  **Outline** if `true` means there is only an outline and if `false` it will be filled in. We will just need the outline so we will make it false.

![illustration of draw rectangle](images/DrawSquareIllustration.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`NPCM`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Copy and paste the following into the **Draw Event** in **obj_movement_controller**.  This will draw a title and make two different colored boxes on the top left and bottom right of hte screen.

```gml
/// @description Draw Title and Target

// Center text alignment
draw_set_halign(fa_center);

// Set the color to yellow
draw_set_color(c_yellow);

// Draw start rectangle
draw_rectangle(44, 44, 148, 148, true);

// Set color to green
draw_set_color(c_green);

// Draw target rectangle
draw_rectangle(1176, 620, 1280, 724, true);

// set color for title font
draw_set_color(c_white);

// Titel top center of hte room
draw_text(room_width * .5, 20, "Movement Room");

// Reset draw color
draw_set_color(c_white);

// Reset alignment
draw_set_halign(fa_left);

```
![copy and paste above script](images/copyPasteScript.png)


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`NPCM`| :small_orange_diamond:

Open up **rm_npc_movement** and drag a copy of **obj_movement_controller** into the scene.

![draw obj_movement_controller into rm_npc_movement](images/drageObjectInRoom.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`NPCM`| :small_orange_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. You will see a yellow box that the NPC will start in and a green box for it to trabvel to.

![level running with begining and end point](images/EmptyLevel.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`NPCM`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Right click on **Objects** and select **Create | Object**, call the file `obj_npc`.  Right click on **Sprites** and click on **Create | Sprite** and call it `spr_npc`. Press the <kbd>Edit Image</kbd> button and select the **Yellow** color and the **Fill Tool**. Click in the sprite to fill it to a yellow square.  Go back to **obj_npc** and assign the new **spr_sprite**.

![add obj_npc and spr_npc as a yellow cube](images/AddObjSprNPC.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`NPCM`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

*Drag* `obj_npc` into **rm_npc_movement**.

![drag obj_npc into room](images/dragnpctoroom.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`NPCM`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Woops, it is positioned in the wrong spot.  This is not where we wanted it.  We have made a square that starts at 64 pixels on the x and 64 pixels on the y. We want to pin the sprite to the top left corner of the target which is 64 by 64 (as it is at 44 by 44 but have created a 20 pixel margin).

![Run game but square is in wrong position](images/placeSquare.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`NPCM`| :large_blue_diamond:

Double click **obj_npc** in the room and change the **x** and **y** to `64`.

![change position of obj_jpc to 64 and 64 in room](images/positionNPCinRoom.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 11.`\|`NPCM`| :large_blue_diamond: :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>


##### `Step 12.`\|`NPCM`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 13.`\|`NPCM`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 14.`\|`NPCM`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 15.`\|`NPCM`| :large_blue_diamond: :small_orange_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 16.`\|`NPCM`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 17.`\|`NPCM`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 18.`\|`NPCM`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 19.`\|`NPCM`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 20.`\|`NPCM`| :large_blue_diamond: :large_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 21.`\|`NPCM`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

___


<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - ADD NEXT TNPCME">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

| [home](../README.md#user-content-gms2-npc-movement) | [next](../)|
|---|---|
