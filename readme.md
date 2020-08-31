# FFXI Coalition Tracker

This one-page app allows you to easily track your Adoulin Coalition status and missions, as well as providing extra information on how which missions would cause you issues before you get your sweet sweet ergon weapon. Data is saved in localstorage under 2 different keys: state and extState.

## How to use

- **Changing current imprimatur count** : Click on the number next to the coalition name to get an input
- **Marking a quest as "active"** : Click on a quest (not its name). This will highlight the quest. Clicking it again will **complete it**
- **Marking a quest as "inactive"** : Right Click on a quest (not its name). This will remove the highlight from the quest without affecting imprimaturs.
- **Complete a quest** : Double clicking a quest will complete it, that is to say add 3 imprimaturs to the count and mark it as complete. Alternatively, clicking on the checkbox marks it as complete without changing imprimaturs or active state.
- **Open a quest on BG Wiki** : The names of each quest are links to their BG wiki counterpart. 
- **Import/Export data** : Double clicking on the title of the page will open a prompt that will show you the base save state. This can be used to move from one computer to another.
- **View changelog** : Clicking on the version number will open the changelog.
- **Toggle Fast Cooldowns (Bronze Shovel Cordon)** : Clicking on the shovel icon toggles between having faster (30 minutes) imprimatur cooldowns. This option only appears when all coalitions are at advisor or higher.

## Technical information

State is a flat `;`-separated list of tuples for each coalition. The first number in this tuple is the number of imprimaturs spent, and the second number is an arbitrarily sized bitmap for completed quests (the size of this number depends on the number of quests in the coalition). The reason for this format is to allow easy transfer of save data, as it is a simple list of numbers.

ExtState is an outright copy of the state of the app. The goal of this is to provide extended features that would be a bit more annoying to move around. Also because I thought of features too late.
