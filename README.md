# Upgrading an existing Medieval MC 1.20.1 Forge world to v27
*Why do I have to do this?*

Unfortunately, due to worldgen incompatibilities causing corruption over time, some worldgen mods had to be removed in this version. 

This means existing worlds won't load by default. 

While I recommend starting a new world anyway to see any newly added content, I understand some people want to keep playing their old worlds. 

Thankfully, this is something you can do fairly simply.

## So how do I convert my old world?
To start, you'll need some software to view and edit data files. I recommend NBT Studio: [https://github.com/tryashtar/nbt-studio](https://github.com/tryashtar/nbt-studio/releases/download/v1.15.3/NbtStudio.exe)

**Make a copy of your existing world before proceeding. Put it somewhere safe in case you make a mistake, so you can start over.**

It's also worth mentioning that *EveryCompat has been removed*, which means all of its blocks will be deleted in the update - this includes any EveryCompat chests!

### 1. First, we need to get the seed from your old world. 
(If you already have this for some reason, skip to the next step.)
- To find this easily if your v26.5 (or older) world is still running, you can use the `/seed` command in-game if you have cheats enabled or Op permissions.
- Otherwise, inside the world folder, open up the **level.dat** file using NBT Studio, and you can find the seed as one of the values in **Data\WorldGenSettings**
  
![image](https://github.com/muon-rw/mmc-upgrade-guide/assets/128171313/3dd6b224-3314-4d20-a0bb-4cc92c79b612)


### 2. Generate a new world for a new level.dat
- Using Medieval MC Forge 1.20.1 v27, start up the game and generate a new world using your old seed, with the same settings.
(To do this with a server, add the seed to server.properties, and start.) 
![image](https://github.com/muon-rw/mmc-upgrade-guide/assets/128171313/129858f9-b103-4bad-95d8-d132dda780bb)
- Create the world and wait for it to generate. 

### 3. Open the new level.dat 
- Open the **level.dat** for this *new world* in NBT Studio. *If your old level.dat was open to get the seed, leave both windows open.*

### 4. Copy the new "generator"
- In the *new* **level.dat**, go to **Data\WorldGenSettings\dimensions\minecraft:the_end**, select the block that says "**generator:** [3 entries]", and **copy**.

![image](https://github.com/muon-rw/mmc-upgrade-guide/assets/128171313/7ffefc68-cc4e-434b-a616-8bc308e3c9b5)

### 5. Delete your old world's "generator"
- Now open your *old world's* **level.dat** (or just go back to it, if it's already open).
- Navigate to **Data\WorldGenSettings\dimensions\minecraft:the_end**, and select its existing "**generator:** [3 entries]", and **delete**. 

It should now look like this:
![image](https://github.com/muon-rw/mmc-upgrade-guide/assets/128171313/161ba5ae-db5b-49fd-a9fb-01565c4cc9bd)


### 6. Paste the new "generator" into the old level.dat
- Still in the old world, select "**minecraft:the_end:** [2 entries]", and **paste** the **generator** (that we copied earlier) inside. 

When you're done, it should look like this!
![image](https://github.com/muon-rw/mmc-upgrade-guide/assets/128171313/45337715-665a-4138-bb7d-3266e209a4e5)


### 7. Repeat steps 4-6, but with **minecraft:overworld**, and **minecraft:the_nether**
- This is important! Make sure all 3 vanilla dimensions (**minecraft:overworld**, **minecraft:the_nether**, and **minecraft:the_end** have been replaced before trying to start your world.

### 8. Change your old world's version number to v27
- In **Data\modPackinfo:** [3 entries], change modPackVersion to v27

![image](https://github.com/muon-rw/mmc-upgrade-guide/assets/128171313/e9a80378-d3e5-46de-91df-c919c3f15bc7)

![image](https://github.com/muon-rw/mmc-upgrade-guide/assets/128171313/f62198b1-8f9a-4da1-9235-8fd7cebc31b7)
- Click Ok

### 9. **Save**. 
![image](https://github.com/muon-rw/mmc-upgrade-guide/assets/128171313/2226fb65-5144-4269-942a-8c19633976c5)

- You should now be able to use your v26.5 world on v27! Just copy the world folder into the **saves** folder of a v27 installation, and play! 

Happy crafting! If you have issues, please join our Discord https://discord.gg/lunapixel and head to the **#medieval-mc-forge** channel. 


*Note: You may end up with some "hard lines" of sheer cliffs where the old generation connects with the new in some cases. This is an unfortunate potential side effect of changing generators, and not a sign of corruption*
