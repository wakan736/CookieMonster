![ESLint](https://github.com/Aktanusa/CookieMonster/workflows/ESLint/badge.svg?event=push)
## Cookie Monster

**Cookie Monster** is an addon you can load into Cookie Clicker, that offers a wide range of tools and statistics to enhance the game. **It is not a cheat interface** – although it does offer helpers for golden cookies and such, everything can be toggled off at will to only leave how much information you want.
The mod helps you to *whichever* degree you want, if you only need some help shortening long numbers, it does that. If you need to be accompanied by hand to pick the best buildings to buy, it does that, but **everything is an option**.

### Current version
The `master` branch hosts the latest production version intended for general users. 
All development and pull requests should target the `dev` branch.
Github Pages is hosted from the 'gh-pages' branch

### What it does

At its core, Cookie Monster computes an index for both buildings and upgrades: the **Payback Period (PP)**. CM will take *everything* in consideration, meaning if buying a building also unlocks an achievement which boosts your income, which unlocks an achievement, CM will know and highlight that building's value. CM uses the following formula to calculate the PP: 

```
max(cost - cookies in bank, 0)/cps + cost/Δ cps
```

If the relevant option is enabled, CM will color-code each of them based on their value. CM compares the PP across all possible buy options: if a buy 10 option is better than any of the buy 1 options Cookie Monster will colour them accordingly. Note that sometimes it is better to buy 10 of a building than to buy only 1, CM will also indicate this!

The following standard colours are used:

* Light Blue: (upgrades) This item has a better PP than the best building to buy
* Green: This building has the best PP
* Yellow: This building is within the top 10 of best PP's
* Orange: This building is within the top 20 of best PP's
* Red: This building is within the top 30 of best PP's
* Purple: This building is worse than the top 10 of best PP's
* Gray: This item does not have a PP, often this means that there is no change to CPS

Note: For this index, **lower is better**, meaning a building with a PP of 1 is more interesting than one with a PP of 3.

## Using

### Bookmarklet

Copy this code and save it as a bookmark. Paste it in the URL section. To activate, click the bookmark when the game's open.

```javascript
javascript: (function () {
	Game.LoadMod('https://cookiemonsterteam.github.io/CookieMonster/dist/CookieMonster.js');
}());
```

If (for some reason) the above doesn't work, trying pasting everything after the <code>javascript:</code> bit into your browser's console.

### Userscript

If you'd rather use the addon as a [userscript](https://en.wikipedia.org/wiki/Userscript) to automatically load _Cookie Monster_ every time the original game loads, install the `CookieMonster.user.js` file. You can do this by clicking on the file in the file-list and clicking "raw".

**Note that to avoid conflicts Cookie Monster should ideally be loaded after any other content mods have been loaded**

## Bugs and suggestions

Any bug or suggestion should be **opened as an issue** [in the repository](https://github.com/CookieMonsterTeam/CookieMonster/issues) for easier tracking. This allows us to close issues once they're fixed.

Before submitting a bug, make sure to give a shot at the latest version of the addon on the `dev` branch. This version can be tested by copying the `CookieMonsterDev.js` file of the dev branch into your console. You can also load the dev-version by using `https://cookiemonsterteam.github.io/CookieMonster/dist/CookieMonsterDev.js` to load the mod. If the bug is still here, you can submit an issue for it. Please do so by using the bug report template.

All suggestions are welcome, even the smallest ones.

## Contributing

To contribute you can fork and clone the repository and run `npm install`.

Please also remember to run `npm run build` after saving all your changes to build the final `CookieMonsterDev.js` file.

Before pushing a new version to master and Github pages copy the `Dev` files into the normal files.

## Contributors

* **[Raving_Kumquat](https://cookieclicker.wikia.com/wiki/User:Raving_Kumquat)**: Original author
* **[Maxime Fabre](https://github.com/Anahkiasen)**: Previous maintainer
* **[BlackenedGem](https://github.com/BlackenedGem)**: Golden/Wrath Cookie Favicons
* **[Sandworm](https://github.com/svschouw)**: Modified PP calculation
* **[Aktanusa](https://github.com/Aktanusa)**: Current maintainer
* **[DanielNoord](https://github.com/DanielNoord)**: Current maintainer
* **[bitsandbytes1708](https://github.com/bitsandbytes1708)**: Current maintainer
