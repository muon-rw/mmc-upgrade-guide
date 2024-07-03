# Upgrading an existing Medieval MC 1.20.1 Forge world to v27
*Why do I have to do this?*

Unfortunately, due to worldgen incompatibilities causing corruption over time, some crucial worldgen mods had to be removed in this version. 

What this means is that existing worlds won't load by default. But thankfully, this is something you can fix if you really want to keep your existing world!

*Note: You may end up with some "hard lines" of sheer cliffs where the old generation connects with the new in some cases. This is an unfortunate potential side effect of changing generators, and not a sign of corruption*

## So how do I convert my old world?
To start, you'll need some software to view and edit data files. I recommend NBT Studio: [https://github.com/tryashtar/nbt-studio](https://github.com/tryashtar/nbt-studio/releases/download/v1.15.3/NbtStudio.exe)

**Make a copy of your existing world before proceeding. Put it somewhere safe in case you make a mistake, so you can start over.**

### 1. First, we need to get the seed from your old world. 
(If you already have this for some reason, skip to the next step.)
- To find this easily if your v26.5 world is still running, you can use the `/seed` command in-game if you have cheats enabled or Op permissions.
- Otherwise, inside the world folder, open up the **level.dat** file using NBT Studio, and you can find the seed as one of the values in **Data\WorldGenSettings**
  
[image]

### 2. Generate a new level.dat
- Using Medieval MC Forge 1.20.1 v27, start up the game and generate a new world using your old seed, with the same settings.
(To do this with a server, add the seed to server.properties, and start.) 

### 3. Open the new level.dat 
- Open the **level.dat** for this *new world* in NBT Studio. *If your old level.dat was open to get the seed, leave both windows open.*

### 4. Copy the new generator block
- In the *new* **level.dat**, go to **Data\WorldGenSettings\dimensions\minecraft:the_end**, select the block that says "**generator:** [3 entries]", and copy. 

[image]

### 5. Delete your old world's generator block
- Now open your *old world's* **level.dat** (or just go back to it, if it was already open from getting the seed).
- Navigate to **Data\WorldGenSettings\dimensions**, and select its existing "**generator:** [3 entries]" block, and **delete**. 

[image]

### 6. Paste the new generator block into the old level.dat
- Still in the old world, select "**minecraft:the_end:** [2 entries]", and **paste** the **generator** block (that we copied earlier from the new world) inside of it. It should look like this:

[image]

### 7. Repeat steps 4-6, but with **minecraft:overworld** instead of **minecraft:the_end** 

### 8. Click **save**. 
- You should now be able to use your v26.5 world on v27! Just copy the world folder into the **saves** folder, and join. 

Happy crafting! If you have issues, please join our Discord https://discord.gg/lunapixel and head to the **#medieval-mc-forge** channel. 
