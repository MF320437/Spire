
Formula:
`levelScaling = Battler.CharacterInfo.Level * LEVEL_SCALING_FACTOR `
`bonusDamage = weaponBonus+RaceBonus+OriginBonus`
`statContribution = (partyMember.Stats.Strength * strengthWeight) +` 
				`(partyMember.Stats.Dexterity * dexterityWeight) +` 
				`(partyMember.Stats.Intelligence * intelligenceWeight) +`
				`(partyMember.Stats.Endurance * enduranceWeight)`

`TotalDamage = levelScaling + statContribution + bonusDamage`



**How this system works?**
All players have a "**Total Damage**" value, this value **increases** as the **player progresses**, **gains stats** and **utilizes new weapons or items**, It is **not reliant on any one move** and is all encompassing, taking into account every player stat and damage bonus.

**How does stat Contribution work?**
Every stat has a "weight" value, this value determines the worth of a single point towards damage, 
in simple terms strength, dex, int, and endurance are not weighted equally rather stats that are more "combat-oriented" will have a higher impact on total damage as compared to other stats, though all stats increase total damage by some amount.
Example:
`Str = 10, Weight = 2 -> This will result in a totalDamage bonus of` $10*2= 20$
`Dex = 20 Weight = 1 -> This will result in a totalDamage bonus of` $20*1= 20$
*These are just examples and are not the actual weight values*

**What about moves?**
With that being said **moves do not have a damage value**, rather they have a coefficient, which is a multiplier to the total damage, so a move with a coefficient of 1 will do 100% of the total damage, whilst a move with a coefficient of .5 would be 50% of total damage. This does mean that no move "Scales" of any specific stat, though you will still need to reach a moves required stats in order to utilize said move.

**What about move scaling?**
This system does not allow any move to scale of any specific stat, i understand this might be controversial but this system allows for bar better balancing and does not remove the ability to 
create unique builds as stat requirements are still present. Nor does this decrease the value of using for example magic moves over physical because of lower totalDamage, coefficients are adjusted to balance moves, whilst a mage build might lead to a lower totalDamage value, they tend to have higher coefficients on moves to reciprocate this.

**What does this allow me to do?**
Well for one damage calculations are way easier, the damage of any move at its simplest is TotalDamage * Coefficient, in the future i can then easily add new elements for example, introducing amour.
Lets say for example the player has 5% amour, this would look like 
`MoveDamage = totaldamage * coefficient, `
`MoveDamageAfterArmour = MoveDamage * .95` or  `MoveDamage * (1-ArmourPercent)`, 
easily adding a new element to damage calculations that doesn't require a bunch of additional checks.