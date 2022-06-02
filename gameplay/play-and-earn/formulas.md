# Formulas

**Congratulations gamers, you’ve made it to the formulas section!** We previously discussed how NFTs have rarity levels that correspond to their advantage for energy, health, rewards, and game mechanics. The question now is, how do we convert these levels into actual formulas? In this section, we will review the utility and basic formulas for each attribute. However, there are secret formulas and/or coefficients associated with each game that can be uncovered by the community. We encourage the community to use statistics and experience to find the optimal value for your attributes, and then use our marketplace to acquire your dream NFTs.

When developing a Play and Earn ecosystem, the functions that distribute rewards and govern NFT advantages are crucial. Linear rewards do not properly incentivize higher levels and better gameplay. Exponential rewards do a great job incentivizing higher levels, but won’t benefit the new and improving players as much. To reconcile this, we are basing our main in-game functions off an intuitive, yet powerful function.

![Main Formula for DeFi Land Game Mechanics](<../../.gitbook/assets/image (12).png>)

![Advantage (y) vs. Level (x)](<../../.gitbook/assets/image (8).png>)

This is the main formula for the in-game mechanics, so _x_ can be thought of as your level, and _y_ is your advantage. The _y_-value output is plugged into many of the formulas we use to determine rewards and NFT advantages. This is a linear function between each 5-level interval. After each 5-level interval, the slope of the line increases. The basis of this formula is that it will strongly incentivize players to make high scores and use their legendary NFTs, but still makes it meaningful to play with common NFTs and lower scores. As it’s the combination of linear functions, it’s easy to calculate your next reward as well as works as exponential graph. The simplest application of this formula in action is your NFT energy level. A minimum energy level (1) will let you play 2 games before needing a cooldown, while a maximum energy level (100) will let you play 25 games. In other instances, we will incorporate additional coefficients and formulas alongside our base formula to calculate the advantages and costs of different mechanics. If you are trying to do some detective work on how to optimize your attributes and gameplay, it would be smart to start with this formula and then reinforce your theories with statistics and gameplay experience. But that’s all we will say on that. Throughout this section, we will refer to any instance of this function as F(_x_), where _x_ can represent any attribute level or game value.

Here are a few public formulas to show how this equation is incorporated into various gameplay mechanics. Let’s start with **energy**, which is calculated from your `energy attribute level` using the main formula:&#x20;

```python
energy = F(energy_attribute_level)
# if energy_attribute_level = 100, energy = 25
# if energy_attribute_level = 60, energy = 11
```

Your `energy attribute level` is also used to calculate your energy restoration rate. A higher energy attribute level correlates with a faster energy restoration rate, as seen below:

```python
energy_restoration_rate = F(energy_attribute_level) / (24* (1 + 0.005 * energy_attribute_level))
```

**NFT upgrades** allow you to increase the potential of your NFT attributes. After paying a fee and locking your NFT up for a set period of time, we will return to you an upgraded NFT. This will not change the visuals or rarity of the NFT, but it will increase the in-game advantages. You can upgrade your attributes by 1 level at a time, and you can upgrade all of your attributes at once without stacking the upgrade time. Every 5 levels, you will have to pay $DFL on top of the $GOLDY cost. The equations for upgrade time and upgrade cost are shown below:&#x20;

```python
upgrade_time_in_hours = target_level * C * (1 - 0.005 * target_level)
# C being a constant that will be changed periodically to balance the game.
# Starting value of C will be 1/2.
```

```python
upgrade_cost_in_goldy = 10 * C * F(attribute_level)^1.5
upgrade_cost_5_in_goldy = 10 * C * F(attribute_level)^1.5 + 10 DFL * attribute_level
# C being a constant that will be changed periodically to balance the game.
# Starting value of C will be 1.
```

**Repairing** will be a feature that is highly strategized in the game. This is because your rewards depend on your both your `reward attribute level` and a `health multiplier`. The health multiplier diminishes every 10% your health points go down on your NFT. Therefore, players may not want to wait until their health points go to 0 before repairing their item. Here are the equations for the rewards and repair cost:

```python
reward = your_score/max_game_score * F(reward_attribute_lvl) * health_multiplier * balancing_reward_constant
# health_multiplier decreases by 10% each 10 levels
```

While we always aim for complete transparency on our platform, we would be remiss if we didn’t give you the opportunity to have fun discovering gameplay mechanics. Remember, it is not all about the numbers. Gameplay is subjective, and you might find your special niche within the game that gives you the advantage over the NFT attributes.
