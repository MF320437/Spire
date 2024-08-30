Due to the turn based nature of the game, there are only two states for weapons.
The visual "Holstered", that displays on the player while traversing the world, and the "Equipped", variation. 

Current Approach:
Normall we would want to use some manipulation of motor6ds to control the position and rotation in respect to the player, but this is because most games will have some complex interactions with there weapons. Having Equip and De-Equip animations, or being able to throw weapons, etc.

The current project or atleast for the **Minimal Viable Product**, an accessory approach is taken, there are two versions of the weapon that exists as an accessory for example.
**Greatsword_Acc_Holstered** -> Renamed **Weapon**
**Greatsword_Acc_Equipped** -> Renamed **Weapon**

This system does reduce the ability to easily do transitory animations, but its by no means a big hassle to chanage prior to the MVP, going into full development.

**Data**
Weapons are represented as a modulescsript with the following information
**WeaponName** -> self explanitory
**WeaponLore** -> Descripion
**WeaponType** -> Light, Medium, Heavy
**WeaponStats** -> This contains a list of any stat modification made from weilding a 
**WeaponCards** -> These are the attacks usable by the weapon, its cost or requirements

--Weapons can have additional information unique to that weapon, contained within **WeaponData**


****

