# Blender Hands On:

Download this repository and unzip blender to start with this Blender hands on.

**If you don't have a windows machine:**

MAC: https://builder.blender.org/download/blender-2.80-e78770039397-OSX-10.9-x86_64.zip

Linux: https://builder.blender.org/download/blender-2.80-e78770039397-linux-glibc224-i686.tar.bz2

## Content:
- [1. Setting Blender Up](#1-setting-blender-up)
- [2. Camera Movement](#2-camera-movement)
- [3. Starting Our Project](#3-starting-our-project)
- [4. Creating Our Toast Model](#4-creating-our-toast-model)
- [5. UV-Wrapping Our Toast](#5-uv-wrapping-our-toast)
- [6. Animating Our Toast](#6-animating-our-toast)
- [7. Rendering Our Toast](#7-rendering-our-toast)

# 1. Setting Blender Up
Extract Blender from the zip file provided in this repository and run it.

You should be greeted by this screen:

![Blender Splashscreen](Images/blender_splash.png)

Dismiss the version information by pressing escape or clicking into the viewport

Now delete all the objects in the viewport by selecting them with **Left Click** and pressing **X** or **DEL** (ENTF)

![Delete Objects](Images/delete.png)

# 2. Camera Movement
To **zoom** the viewport, simply **scroll** the **Mouse Wheel** up or down while the cursor is over the viewport. Alternatively, you could hold down Ctrl + Mouse Wheel Button while moving your cursor up or down on the screen.

To **orbit** the viewport, hold down the **Middle Mouse Button** while moving your cursor around the viewport. Be sure to start holding down the middle mouse button while your cursor is inside the viewport.

To pan, hold down **Shift + Middle Mouse Button** while moving your mouse across the viewport. Just like orbiting, panning requires that your cursor be inside the viewport before you hold down the keys.

**Touchpad Controls** instead of using the middle mouse button, **use 2 Fingers**.

**Zoom**: swipe with 2 fingers up and down

**Orbit**: swipe with 2 fingers left and right

**Pan**: hold Ctrl and swipe with 2 fingers in any direction

You can also click and drag the axis visualizer in the top right of the viewport to **orbit**,
or click on any axis to **move the view** to that axis. (For that you can also use NUMPAD 1,3,7,9 if you have one)

![Axis](Images/axis.png)

# 3. Starting Our Project
First of all, let's switch to the correct **Workspace** by clicking on **Modeling** (Top Left Corner)

![Blender Workspace](Images/workspace.png)

Now, while having your cursor inside the viewport press **Shift + A** to open the "add" menu.

Select **Mesh** and then **Plane**

![Blender Add Mesh](Images/add_mesh.png)

This should add a **Plane** to your project

![New Plane](Images/plane.png)

# 4. Creating Our Toast Model

## I like to move it move it
Let's start by **moving** our **Plane** to a better position.

If the Plane is **not highlighted** (orange border) **Left Click** on it

Then press **Tab** to switch **from Object Mode to Edit Mode**

**IMPORTANT: if you happen to click somewhere in the viewport and your model becomes unselected, press A to select it again**

And finally click on the **Move Tool** in the left **Toolbar**

![Edit Mode](Images/edit_mode.png)

Now we are ready to actually **move the Plane**

Click on the little **blue Square** to move the Plane around on the **X and Y coordinates**

Then **Hold CTRL** and move the Plane **one step towards the X and Y direction**

![Move Plane](Images/move.png)

Your plane then should have **one corner** in the **origin** of the viewport

![Correct Move](Images/moved.png)

## Mirror it
Once verified, find the **Modifiers Tab** on the **Properties Panel** (right side)

Then click on **Add Modifier** and select **Mirror**

![Mirror](Images/mirror.png)

If done correctly, your toast should look like this:

![Mirrored](Images/mirrored.png)

## Make it look like Toast

Start by selecting the **vertex** (little black dot) furthest from the center and **delete** it

Like last time, press **X** and then select **Vertecies**

![Delete Vertex](Images/del_vert.png)

It now should look like the model is gone, but if you press **A** there should still be 3 **highlighted Vertecies**

now to edit your toast first press **NUMPAD 7**, or if you don't have a numpad press **The Z Axis** in the top right corner of your viewport

![Select Top View](Images/top_view.png)

**If you accidentally rotate your Camera (Middle Mouse Button) simply repeat the last step**

Now it's time to make some toast!

Select the vertecies and move them with the arrows or the blue square
To make a **new** vertex that is connected to another one, press **E**. The new vertex is now snapped to your cursor so you can move it to the desired position and apply it with **Left Click**

**IMPORTANT:**
- You're modeling only the right half of the toast (remember that mirror modifier)
- If you want to delete a vertex, use **X** like before
- **WHEN YOU'RE DONE, SELECT THE LAST 2 VERTECIES OF THE LOOP AND PRESS F**
![Finish Outline](Images/finish_outline.png)

Now that our outline is done, let's put a face into it, so we can see it again.

For that press **A** to select all vertecies

Then press **ALT + F**

![Make Face](Images/make_face.png)

We can now **apply** that **Mirror Modifier**

Press **tab** in the viewport to get back to **object mode** and then click **Apply** in the **Modifier Tab** (Property Panel)

![Apply Mirror](Images/apply_mirror.png)

You can now **TAB** back to **Edit Mode** to thicken that thin slice of toast.

To do that make sure all vertecies are selected by pressing **A** and then Press **E** and move your **Mouse down** and accept with **Left Click** on your desired thickness of toast

![Extrude Face](Images/extrude.png)

# 5. UV-Wrapping Our Toast

To begin **UV-Wrapping** switch to the **UV Editing Workspace**

![Switch Workspace](Images/uv_workspace.png)

Then, in the left window, find the **Open Button** and select the **toast_texture.png** from the repository

![Load Texture](Images/texture.png)

Next, we have to give the uv unwrapper a hint where he should cut the texture of our toast

Press **2** (not numpad) to switch to **Edge Select** mode. Now select the edge in the center of your toasts bottom,
press **U** and select **Mark Seam**.

This edge should now have a red highlight.

![Mark Seam](Images/mark_seam.png)

Now press **3** (not numpad) to switch to **Face Select** mode.

Hold the **ALT** key for **Loop Select** and click on your **Seam**

This should select the outer ring of your toast.

Then press **U** and select **Unwrap**.

To move the faces to the correct spot, press **A** (int the UV editor) to select all and then use the UV editors tools to move it.

![Unwrap Loop](Images/unwrap_loop.png)

Without removing your selection in your **Viewport**, press **CTRL + I** to **Invert** your selection,
and once again, press **U** and select **Unwrap** and move the selection to the correct spot on the left window.

To actually see your work, change your **Viewport Shading** to **Display in LookDev Mode** in the top right of your viewport

Now click on **Material** in the right toolbar, add a **New** material, click the little circle next to **Base Color**
and select **Image Texture**.

Below the base color your can now **Open** an image file, which will be the **toast_texture**.

![Render](Images/render.png)

# 6. Animating Our Toast

We can now **TAB** back to **Object Mode** and proceed to the **Animation Workspace**

If your toast is white again, select **Display in LookDev Mode** in the top right of your viewport.

From there, select the **Rotate Tool** (Toolbar on the left) and make your Toast stand upright

Finally press **I** (not l, big i for **Insert Keyframe**) and click on **Rotation**

![Keyframe](Images/keyframe.png)

To make our toast fall over, move the **Cursor** of the **Timeline** to **20 Frames**,

**Rotate** your toast to lay flat on the floor and then again press **I** and click on **Rotation**

Finally set the **End** of the animation to **30 frames** in the **bottom right** and press **Spacebar** to run the animation.

![Falling Toast](Images/fall.png)

To make the flop look more physically accurate than linear movement, select **both keyframes** with **SHIFT** pressed,

**Right Click** on the **Timeline**, go to **Interpolation Mode** and select **Quartic** (^4)

![Interpolation](Images/interpolation.png)

# 7. Rendering Our Toast

We will now make this falling toast into an actual video file that you can send everyone to tell them how great you are at modeling toast!

For that head back to the **Modeling** workspace and **add (Shift+A)** a **Camera** and move it to a spot that you like. you can check what the camera sees by pressing **Numpad 0** or clicking on the **Camera Symbol** in the top right of the viewport.

if you now switch your **Viewport Shading** to **Rendered**, your toast will become quite dark.

to add some light, **add (Shift+A)** a **Light->Sun** (or something else if you want to have some fun)

then move that little yellow dot to change the direction the sun is coming from.

![Camera](Images/camera.png)

Even in the modeling workspace you can have a look at your animation (start/stop with **Spacebar**),
have a look through your camera to see if it looks like you want it to.

Then head to the **Rendering Workspace** for your final task.

Don't worry, it's normal that you're not seeing anything in your main window, as it is called "Render Result" and we haven't rendered anything yet.

In the Properties window, head to the **Output** tab.

Change the **Output Directory** to somewhere you'd like,

change the **File Format** to **AVI JPEG**

and set **Color** to **RGB**

![Render Options](Images/render_options.png)

Your final step will be to start the **Rendering** by pressing **Ctrl+F12** or clicking **Render Animation** in the render toolbar (top left

![Render Menu](Images/render_menu.png)

This should open a new Window with the active rendering process showing. Once it's done, there should appear a **.avi** file in your chosen destination.

![Final](Images/final.png)
